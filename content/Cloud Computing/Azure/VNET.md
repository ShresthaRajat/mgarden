---
tags: [Azure, cloud]
title: VNET (Virtual Network)
aliases: [VNET (Virtual Network)]
linter-yaml-title-alias: VNET (Virtual Network)
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# VNET (Virtual Network)
#Azure #cloud

-   An [Azure](Cloud%20Computing/Azure/Azure.md) Virtual Network (VNet) is a network or environment that can be used to run VMs and applications in the cloud.
-   When it is created, the services and Virtual Machines within the Azure network interact securely with each other.
- It is similar to the [VPC](Cloud%20Computing/AWS/Networking/VPC.md) service provided by AWS

Azure Virtual Network (VNet) is the fundamental building block for your private network in Azure. You can use a VNets to:

-   **Communicate between Azure resources**: You can deploy VMs, and several other types of Azure resources to a virtual network, such as Azure App Service Environments, the Azure Kubernetes Service (AKS), and Azure Virtual Machine Scale Sets.
    
-   **Communicate between each other**: You can connect virtual networks to each other, enabling resources in either virtual network to communicate with each other, using virtual network peering. The virtual networks you connect can be in the same, or different, Azure regions.
    
-   **Communicate to the internet**: All resources in a VNet can communicate outbound to the internet, by default. You can communicate inbound to a resource by assigning a public IP address or a public Load Balancer. You can also use [Public IP addresses](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-public-ip-address) or public [Load Balancer](https://learn.microsoft.com/en-us/azure/load-balancer/load-balancer-overview) to manage your outbound connections.
    
-   **Communicate with on-premises networks**: You can connect your on-premises computers and networks to a virtual network using [VPN Gateway](https://learn.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-about-vpngateways) or [ExpressRoute](https://learn.microsoft.com/en-us/azure/expressroute/expressroute-introduction).
    

When you design a network from bottom up, you gather some basic information. This information could be number of hosts, network devices, number of [Subnet](Cloud%20Computing/AWS/Networking/Subnet.md), routing between subnets, isolation domains such as VLANs. This information helps in sizing the network and security devices as well creating the architecture to support applications and services.

When you plan to deploy your applications and services in Azure, you will start by creating a logical boundary in Azure, which is called a virtual network. This virtual network is akin to a physical network boundary. As it is a virtual network, you don't need physical gear but still have to plan for the logical entities such as IP addresses, IP subnets, routing, and policies.

When you create a virtual network in Azure, it's pre-configured with an IP range (10.0.0.0/16). This range isn't fixed, you can define your own IP range. You can define both IPv4 and IPv6 address ranges. IP ranges defined for the virtual network are not advertised to Internet. You can create multiple subnets from your IP range. These subnets will be used to assign IP addresses to virtual network interfaces (vNICs). Azure reserves the first four and last IP address for a total of 5 IP addresses within each subnet. There is no concept of VLANs in a public cloud. However, you can create isolation within a virtual network based on your defined subnets.

You can create one large subnet encompassing all the virtual network address space or choose to create multiple subnets.

A virtual network is a virtual, isolated portion of the Azure public network. Each virtual network is dedicated to your subscription. Things to consider when deciding whether to create one virtual network, or multiple virtual networks in a subscription:

-   Do any organizational security requirements exist for isolating traffic into separate virtual networks? You can choose to connect virtual networks or not. If you connect virtual networks, you can implement a network virtual appliance, such as a firewall, to control the flow of traffic between the virtual networks. For more information, visit [security](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-vnet-plan-design-arm?toc=/azure/networking/fundamentals/toc.json) and [connectivity](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-vnet-plan-design-arm?toc=/azure/networking/fundamentals/toc.json).
    
-   Do any organizational requirements exist for isolating virtual networks into separate [subscriptions](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-vnet-plan-design-arm?toc=/azure/networking/fundamentals/toc.json) or [regions](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-vnet-plan-design-arm?toc=/azure/networking/fundamentals/toc.json)?
    
-   A [network interface](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-network-interface) enables a VM to communicate with other resources. Each network interface has one or more private IP addresses assigned to it. How many network interfaces and [private IP addresses](https://learn.microsoft.com/en-us/azure/virtual-network/private-ip-addresses) do you require in a virtual network? There are [limits](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits?toc=/azure/virtual-network/toc.json) to the number of network interfaces and private IP addresses that you can have within a virtual network.

[NSG](Cloud%20Computing/Azure/NSG.md)

[Azure NACL](Cloud%20Computing/Azure/Azure%20NACL.md)