# Amazon Inspector
#aws #cloud #security #cloud-security 
  

Amazon Inspector is an managed [AWS](Cloud%20Computing/AWS/AWS.md) service which provides an automated vulnerability management service that **continually scans AWS workloads for software vulnerabilities and unintended network exposure**.

• Runs assessments that check for security exposures and vulnerabilities in [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instances
• Can be configured to run on a schedule
• Agent must be installed on EC2 for host assessments (except for Network assessments)

## Network Assessments
• Assessments: Network configuration analysis to check for ports reachable from outside the [VPC](Cloud%20Computing/AWS/Networking/VPC.md)
• If the Inspector Agent is installed on your EC2 instances, the assessment also finds processes reachable on port
• Price based on the number of instance assessments

## Host Assessments
• Assessments: Vulnerable software ([CVE](CVE)), host hardening (CIS benchmarks), and security best practices
• Requires an agent (auto-install with [SSM](SSM) Run Command)
• Price based on the number of instance assessments