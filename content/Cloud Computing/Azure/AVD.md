# Azure Virtual Desktop (AVD)
#cloud #Azure #virtual-machines #compute 

Azure Virtual Desktop, (formerly known as Windows Virtual Desktop) is a Microsoft [Azure](Cloud%20Computing/Azure/Azure.md)-based system for [virtualizing](virtualizing) its Windows operating systems,  aimed at enterprise customers rather than at individual users.




## Demo
Setup of AVD with existing [AAD](Cloud%20Computing/Azure/AAD.md).

Steps:
1. Create a Resource Group
2. Create a [VNET](Cloud%20Computing/Azure/VNET.md) link it with the created [Resource Groups](Cloud%20Computing/Azure/Resource%20Groups.md) with a simple subnet
3. Create a Hostpool under the [AVD](Cloud%20Computing/Azure/AVD.md)
4. 

https://www.youtube.com/watch?v=jMAanEp-ugI

## AVD with custom windows 11 image

1. Install necessary program and do required changes
2. Generalize the VM (Remove specific names from VM) 
3. Stop the instance
4. Create an Image 