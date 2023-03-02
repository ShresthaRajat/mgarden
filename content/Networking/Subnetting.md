# Subnet
#networking

A subnet, or sub-network, is a [network](https://www.cloudflare.com/learning/network-layer/what-is-the-network-layer/) inside a network. Subnets make networks more efficient. Through subnetting, network traffic can travel a shorter distance without passing through unnecessary [routers](https://www.cloudflare.com/learning/network-layer/what-is-routing/) to reach its destination.

![zSubnet2.png](Networking/zSubnet2.png.png)
Like the postal service, networks are more efficient when messages travel as directly as possible. When a network receives data packets from another network, it will sort and route those packets by subnet so that the packets do not take an inefficient route to their destination.

## What is an IP address?

In order to understand subnets, we must quickly define [IP addresses](https://www.cloudflare.com/learning/dns/glossary/what-is-my-ip-address/). Every device that connects to the Internet is assigned a unique IP ([Internet Protocol](https://www.cloudflare.com/learning/ddos/glossary/internet-protocol/)) address, enabling data sent over the Internet to reach the right device out of the billions of devices connected to the Internet. While computers read IP addresses as binary code (a series of 1s and 0s), IP addresses are usually written as a series of alphanumeric characters.

## What do the different parts of an IP address mean?

This section focuses on IPv4 addresses, which are presented in the form of four decimal numbers separated by periods, like 203.0.113.112. (IPv6 addresses are longer and use letters as well as numbers.)

Every IP address has two parts. The first part indicates which network the address belongs to. The second part specifies the device within that network. However, the length of the "first part" changes depending on the network's class.

Networks are categorized into different classes, labeled A through E. Class A networks can connect millions of devices. Class B networks and Class C networks are progressively smaller in size. (Class D and Class E networks are not commonly used.)

Let's break down how these classes affect IP address construction:

**Class A network:** Everything before the first period indicates the network, and everything after it specifies the device within that network. Using 203.0.113.112 as an example, the network is indicated by "203" and the device by "0.113.112."

**Class B network:** Everything before the second period indicates the network. Again using 203.0.113.112 as an example, "203.0" indicates the network and "113.112" indicates the device within that network.

**Class C network:** For Class C networks, everything before the third period indicates the network. Using the same example, "203.0.113" indicates the Class C network, and "112" indicates the device.

## Why is subnetting necessary?

As the previous example illustrates, the way IP addresses are constructed makes it relatively simple for Internet routers to find the right network to route data into. However, in a Class A network (for instance), there could be millions of connected devices, and it could take some time for the data to find the right device. This is why subnetting comes in handy: subnetting narrows down the IP address to usage within a range of devices.

Because an IP address is limited to indicating the network and the device address, IP addresses cannot be used to indicate which subnet an IP packet should go to. Routers within a network use something called a subnet mask to sort data into subnetworks.

## What is a subnet mask?

A subnet mask is like an IP address, but for only internal usage within a network. Routers use subnet masks to route data packets to the right place. Subnet masks are not indicated within data packets traversing the Internet — those packets only indicate the destination IP address, which a router will match with a subnet.

Suppose Bob answers Alice's letter, but he sends his reply to Alice's place of employment rather than her home. Alice's office is quite large with many different departments. To ensure employees receive their correspondence quickly, the administrative team at Alice's workplace sorts mail by department rather than by individual employee. After receiving Bob's letter, they look up Alice's department and see she works in Customer Support. They send the letter to the Customer Support department instead of to Alice, and the customer support department gives it to Alice.

In this analogy, "Alice" is like an IP address and "Customer Support" is like a subnet mask. By matching Alice to her department, Bob's letter was quickly sorted into the right group of potential recipients. Without this step, office administrators would have to spend time laboriously looking for the exact location of Alice's desk, which could be anywhere in the building.

For a real-world example, suppose an IP packet is addressed to the IP address 192.0.2.15. This IP address is a Class C network, so the network is identified by "192.0.2" (or to be technically precise, 192.0.2.0/24). Network routers forward the packet to a host on the network indicated by "192.0.2."

Once the packet arrives at that network, a router within the network consults its routing table. It does some binary mathematics using its subnet mask of 255.255.255.0, sees the device address "15" (the rest of the IP address indicates the network), and calculates which subnet the packet should go to. It forwards the packet to the router or [switch](https://www.cloudflare.com/learning/network-layer/what-is-a-network-switch/) responsible for delivering packets within that subnet, and the packet arrives at IP address 192.0.2.15 (learn more about [routers](https://www.cloudflare.com/learning/network-layer/what-is-routing/) and [switches](https://www.cloudflare.com/learning/network-layer/what-is-a-network-switch/)).

# CIDR
**CIDR - Classless Inter-domain Routing**

**The first four IP addresses and the last IP address in each subnet CIDR block are not available for you to use, and cannot be assigned to an instance.**

i.e.

-   10.0.0.0: Network address.
-   10.0.0.1: Reserved by AWS for the VPC router.
-   10.0.0.2: Reserved by AWS for DNS.
-   10.0.0.3: Reserved by AWS for future use.
-   10.0.0.255: Network broadcast address. We do not support broadcast in a VPC, therefore we reserve this address.

Network masks:

-   /16 - supports up to 65,536 IP addresses. Best for large networks.
-   /24 - supports up to 256 IP addresses. Best for smaller networks.
-   /27 - supports up to 32 IP addresses
-   /28 - supports up to 16 IP addresses
-   /32 - an absolute IP address - matches exactly one

It’s possible to split a CIDR block into two subnets:

-   one subnet can use CIDR block 10.0.0.0/25 (for addresses 10.0.0.0 - 10.0.0.127)
-   and then the other subnet can use the CIDR block 10.0.0.128/ 25 (for addresses 10.0.0.128 - 10.0.0.255)

The allowed CIDR block size in a VPC is between a /16 and /28 subnetmask.

To enable ping, you need to allow ICMP traffic.

In order to ensure provisioned EC2 instances have a public IP address, enable “Auto-Assign Public IP” for the subnet.

0.0.0.0/0 is also known as default 
It represents all possible IP addresses>)
