---
tags: [cloud, aws, hasicorp, IaC, terraform, windows]
title: "Packer: Creating a base windows server in AWS"
aliases: ["Packer: Creating a base windows server in AWS"]
linter-yaml-title-alias: "Packer: Creating a base windows server in AWS"
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:42 am
---
# Packer: Creating a base windows server in AWS
#cloud #aws #hasicorp #IaC #terraform #windows 

This example uses the hcl format packer file to create a [AMI](AMI) in [AWS](Cloud%20Computing/AWS/AWS.md) through [Packer](DevOps/IAC/Packer/Packer.md). This demo builds an [Windows](Windows) AMI based on windows server 2016 with containers with custom applications (Datadog agent and dotnet framework, firefox, putty, devtools).

1. Set the aws credentials on the CLI
2. Create a VPC or just use a default VPC
3. Create a `packer.hcl` filewith the following:

```hcl
variable "ami_name" {
	type = string
	default = "Win-2016-Containers-Base-{{timestamp}}"
}

variable "region" {
	type = string
	default = "eu-west-1"
}
  
variable "var_instance_type" {
	type = string
	default = "c6i.large"
}

variable "var_vm_base_name" {
	type = string
	default = "WinServer-2016-English-Full-Containers" 
}

variable "var_vm_base_owner" {
	type = string
	default = "amazon"
}
  
data "amazon-ami" "server_win2016_con" {
	filters = {
		name = "${var.var_vm_base_name}*"
		root-device-type = "ebs"
		virtualization-type = "hvm"
	}
	most_recent = true
	owners = ["${var.var_vm_base_owner}"]
	region = var.region
}

source "amazon-ebs" "windows" {
	ami_name = var.ami_name
	instance_type = var.var_instance_type
	region = var.region
	source_ami = data.amazon-ami.server_win2016_con.id
	
	# Use these vars for custom vpc public sn
	# vpc_id = "vpc-03e5a79ba2cf55673"
	# subnet_id = "subnet-05aed32d3db86345c"
	# associate_public_ip_address = "true"
	
	communicator = "winrm"
	winrm_username = "Administrator"
	winrm_use_ssl = true
	winrm_insecure = true
	launch_block_device_mappings {
		delete_on_termination = true
		device_name = "/dev/sda1"
		volume_size = 50
		volume_type = "gp3"
	} 

	tags = {
		ApprovedEnvironments = "test"
		ApprovedInspector = "false"
		BuildDate = "{{ isotime }}"
		Name = "ebs-${var.ami_name}"
		stable = "false"
	}

	# user data file is required for packer to connect

	user_data_file = "winrm_bootstrap.txt"
	
}

build {
	sources = ["source.amazon-ebs.windows"]
	provisioner "powershell" {
		script = "install.ps1"
	}

	provisioner "powershell" {
		inline = [
			# Re-initialise the AWS instance on startup
			"C:/ProgramData/Amazon/EC2-Windows/Launch/Scripts/InitializeInstance.ps1 -Schedule",
			
			# Remove system specific information from this image
			"C:/ProgramData/Amazon/EC2-Windows/Launch/Scripts/SysprepInstance.ps1 -NoShutdown"
		]
	}

}
```


Then create a powershell script `install.ps1` with:

``` powershell
# Install Programs and updates

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls, [Net.SecurityProtocolType]::Tls11, [Net.SecurityProtocolType]::Tls12, [Net.SecurityProtocolType]::Ssl3
[Net.ServicePointManager]::SecurityProtocol = "Tls, Tls11, Tls12, Ssl3"

try {
	# Install Windows update PS cmdlet
	Write-Host "Installing Windows update PS cmdlet"
	Install-Module -Name PSWindowsUpdate -Force
	Write-Host "Getting windows update"
	Get-WindowsUpdate
	Write-Host "Downloading and Applying Windows Updates"
	Get-WUInstall -AcceptAll -AutoReboot | Out-File C:\PSWindowsUpdate.log
	Write-Host "Contents of the update log:"
	cat C:\PSWindowsUpdate.log
	Write-Host "Finished updating!"
  

	# Install Dotnet Framework
	Write-Host "Downloading dotnet_4.72"
	Invoke-WebRequest -Uri "https://download.visualstudio.microsoft.com/download/pr/158dce74-251c-4af3-b8cc-4608621341c8/9c1e178a11f55478e2112714a3897c1a/ndp472-devpack-enu.exe" -OutFile dotnet_4_72.exe
	Write-Host "Installing dotnet_4.72"
	$dotnet = (Start-Process .\dotnet_4_72.exe -ArgumentList "/SILENT","/NORESTART","/MERGETASKS=!runcode" -NoNewWindow -Wait -PassThru)
	if ($dotnet.ExitCode -ne 0) {
		Write-Error "Error installing Dotnet4.72"
		exit 1
	}

	# Install DataDog Agent
	Write-Host "Downloading Datadog"
	Invoke-WebRequest -Uri "https://s3.amazonaws.com/ddagent-windows-stable/datadog-agent-7-latest.amd64.msi" -OutFile DataDog.msi
	Write-Host "Installing Datadog"
	$datadog = (Start-Process msiexec.exe -ArgumentList "/qn", "/i","DataDog.msi","/passive" -NoNewWindow -Wait -PassThru)
	if ($datadog.ExitCode -ne 0) {
		Write-Error "Error installing Datadog"
		exit 1
	}
	Write-Host "Downloading Powershell"
	Invoke-WebRequest -Uri "https://objects.githubusercontent.com/github-production-release-asset-2e65be/49609581/e4df067c-213c-4418-9ce1-194abf2f3aec?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20230111%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20230111T122115Z&X-Amz-Expires=300&X-Amz-Signature=7ef9288ef60c2113631bc06610e60d62eaaf05bba399bd36a8e9b61d9dde8375&X-Amz-SignedHeaders=host&actor_id=107860829&key_id=0&repo_id=49609581&response-content-disposition=attachment%3B%20filename%3DPowerShell-7.4.0-preview.1-win-x64.msi&response-content-type=application%2Foctet-stream" -OutFile PowershellSetup.msi
	Write-Host "Installing Powershell"
	$Powershell = (Start-Process msiexec.exe -ArgumentList "/i","PowershellSetup.msi","/passive" -NoNewWindow -Wait -PassThru)
	if ($Powershell.ExitCode -ne 0) {
	Write-Error "Error installing Powershell"
	exit 1	
	}

	Write-Host "Downloading Firefox"
	
	Invoke-WebRequest -Uri "https://download.mozilla.org/?product=firefox-msi-latest-ssl&os=win64&lang=en-GB" -OutFile FirefoxSetup.msi
	Write-Host "Installing Firefox"
	$firefox = (Start-Process msiexec.exe -ArgumentList "/i","FirefoxSetup.msi","/passive" -NoNewWindow -Wait -PassThru)
	if ($firefox.ExitCode -ne 0) {
	Write-Error "Error installing Firefox"
	exit 1
	}	  
	
	Write-Host "Downloading Putty"
	Invoke-WebRequest -Uri "https://the.earth.li/~sgtatham/putty/0.74/w64/putty-64bit-0.74-installer.msi" -OutFile putty-installer.msi
	Write-Host "Installing Putty"
	$putty = (Start-Process msiexec.exe -ArgumentList "/i","putty-installer.msi","/passive" -NoNewWindow -Wait -PassThru)
	if ($putty.ExitCode -ne 0) {
		Write-Error "Error installing Putty"
		exit 1
	}
	Write-Host "Downloading VSCode"
	
	Invoke-WebRequest -Uri "https://code.visualstudio.com/sha/download?build=stable&os=win32-x64" -OutFile VSCodeSetup.exe
	Write-Host "Installing VSCode"
	$vscode = (Start-Process .\VSCodeSetup.exe -ArgumentList "/SILENT","/NORESTART","/MERGETASKS=!runcode" -NoNewWindow -Wait -PassThru)
	if ($vscode.ExitCode -ne 0) {
		Write-Error "Error installing VSCode"
		exit 1	
	}

	$vscode_extensions = @("ms-vscode-remote.remote-ssh")
	foreach ($vse in $vscode_extensions) {
		Write-Host "Installing VSCode extension $vse"
		
		# Unfortunately this always seems to return 0 even if there's an error
		$vscodeext = (Start-Process "C:\Program Files\Microsoft VS Code\bin\code.cmd" -ArgumentList "--install-extension",$vse,"--force" -NoNewWindow -Wait -PassThru)
		if ($vscodeext.ExitCode -ne 0) {
		Write-Error "Error installing VSCode extension"
		exit 1
		}
	}
}

catch
{
	Write-Error $_.Exception
	exit 1
}
```

Also create this file named `winrm_bootstrap.txt` with:
```powershell
<powershell>
write-output "Running User Data Script"
write-host "(host) Running User Data Script"
Set-ExecutionPolicy Unrestricted -Scope LocalMachine -Force -ErrorAction Ignore

# Don't set this before Set-ExecutionPolicy as it throws an error
$ErrorActionPreference = "stop"

# Remove HTTP listener
Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse

# Create a self-signed certificate to let ssl work
$Cert = New-SelfSignedCertificate -CertstoreLocation Cert:\LocalMachine\My -DnsName "packer"
New-Item -Path WSMan:\LocalHost\Listener -Transport HTTPS -Address * -CertificateThumbPrint $Cert.Thumbprint -Force

# WinRM
write-output "Setting up WinRM"
write-host "(host) setting up WinRM"

cmd.exe /c winrm quickconfig -q
cmd.exe /c winrm set "winrm/config" '@{MaxTimeoutms="1800000"}'
cmd.exe /c winrm set "winrm/config/winrs" '@{MaxMemoryPerShellMB="1024"}'
cmd.exe /c winrm set "winrm/config/service" '@{AllowUnencrypted="true"}'
cmd.exe /c winrm set "winrm/config/client" '@{AllowUnencrypted="true"}'
cmd.exe /c winrm set "winrm/config/service/auth" '@{Basic="true"}'
cmd.exe /c winrm set "winrm/config/client/auth" '@{Basic="true"}'
cmd.exe /c winrm set "winrm/config/service/auth" '@{CredSSP="true"}'
cmd.exe /c winrm set "winrm/config/listener?Address=*+Transport=HTTPS" "@{Port=`"5986`";Hostname=`"packer`";CertificateThumbprint=`"$($Cert.Thumbprint)`"}"
cmd.exe /c netsh advfirewall firewall set rule group="remote administration" new enable=yes
cmd.exe /c netsh firewall add portopening TCP 5986 "Port 5986"
cmd.exe /c net stop winrm
cmd.exe /c sc config winrm start= auto
cmd.exe /c net start winrm

</powershell>
```


At last just run `packer build packer.hcl to create the ami`

Note this will create a 