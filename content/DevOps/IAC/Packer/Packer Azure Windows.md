# Packer: Creating a generalized IIS windows server in Azure
#cloud #hasicorp #IaC #terraform #windows 

This example uses the json format packer file to create a VM Image in [Azure](Cloud%20Computing/Azure/Azure.md) through [Packer](DevOps/IAC/Packer/Packer.md). This demo builds an [Windows](Windows) Image and installs IIS server.

1. Create a resource group
2. Create azure credentials and set it in your cli 
3. Create a file named packer.json
This one is done in json you can also use the newer hcl
```json
{
    "builders": [{
      "type": "azure-arm",
      
      "subscription_id": "2991547e-62b7-4ef8-8b12-78e8e3a9af3b",
      "use_interactive_auth" : "true",
  
      "managed_image_resource_group_name": "packer-artifacts-rg",
      "managed_image_name": "packerImage",

      "os_type": "Windows",
      "image_publisher": "MicrosoftWindowsServer",
      "image_offer": "WindowsServer",
      "image_sku": "2016-Datacenter",
  
      "communicator": "winrm",
      "winrm_use_ssl": true,
      "winrm_insecure": true,
      "winrm_timeout": "5m",
      "winrm_username": "packer",
  
      "azure_tags": {
          "dept": "DevOps",
          "task": "Image deployment"
      },
      "location": "UK South",
      "vm_size": "Standard_D2_v2"
    }],
    "provisioners": [{
      "type": "powershell",
      "inline": [
        "Add-WindowsFeature Web-Server",
        "while ((Get-Service RdAgent).Status -ne 'Running') { Start-Sleep -s 5 }",
        "while ((Get-Service WindowsAzureGuestAgent).Status -ne 'Running') { Start-Sleep -s 5 }",
        "& $env:SystemRoot\\System32\\Sysprep\\Sysprep.exe /oobe /generalize /quiet /quit",
        
        "while($true) { $imageState = Get-ItemProperty HKLM:\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\State | Select ImageState; if($imageState.ImageState -ne 'IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE') { Write-Output $imageState.ImageState; Start-Sleep -s 10  } else { break } }"
      ]
    }]
  }
```

4. Run the packer build command `packer build packer.json`

From: https://learn.microsoft.com/en-us/azure/virtual-machines/windows/build-image-with-packer
