# Azure Virtual Desktop
#cloud #Azure #virtual-machines #compute 

Azure Virtual Desktop, (formerly known as Windows Virtual Desktop) is a Microsoft [Azure](-=%20Azure%20=-/Azure.md)-based system for [virtualizing](virtualizing) its Windows operating systems,  aimed at enterprise customers rather than at individual users.




## Demo
Setup of AVD with existing [AAD](-=%20Azure%20=-/AAD.md).

Steps:
1. Create a Resource Group
2. Create a [VNET](-=%20Azure%20=-/VNET.md) link it with the created [Resource Groups](-=%20Azure%20=-/Resource%20Groups.md) with a simple subnet
3. Create a Hostpool under the [AVD](-=%20Azure%20=-/AVD.md)
4. 

https://www.youtube.com/watch?v=jMAanEp-ugI

## AVD with custom windows 11 image

1. Install necessary program and do required changes
2. Generalize the VM (Remove specific names from VM) 
3. Stop the instance
4. Create an Image 