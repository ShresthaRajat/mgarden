# Bastion
#aws #ec2 #cloud #compute 
also known as Jump-box

Bastions are [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instances which are security harden. They are designed to help you gain access to your EC2 via SSH or RDP that are in private subnet which are not directly accessible from the internet.

They are also known as Jump Boxes.

NAT Gateways/ Instances are only intended for EC2 instances to gain outbound access to the internet for things such as security updates. NATs cannot/should not be used as bastions.

[AWS Systems manager](Cloud%20Computing/AWS/Application%20Integration/AWS%20Systems%20manager.md) provides a secure alternative to the bastion hosts.

A bastion host is a special-purpose computer on a network specifically designed and configured to withstand attacks, so named by analogy to the military fortification. The computer generally hosts a single application or process, for example, a proxy server or load balancer, and all other services are removed or limited to reduce the threat to the computer. It is hardened in this manner primarily due to its location and purpose, which is either on the outside of a firewall or inside of a demilitarized zone ([DMZ](Cyber%20Security/Cloud%20Security/DMZ.md)) and usually involves access from un-trusted networks or computers. These computers are also equipped with special networking interfaces to withstand high-bandwidth attacks through the internet.


Most often the [Security Groups](Cloud%20Computing/AWS/Networking/Security%20Groups.md) of the bastion is added to the security group of the instance to be accessed. This is the