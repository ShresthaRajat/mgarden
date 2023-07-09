---
tags: [aws, cloud, snowball, storage, cloud-migration]
---
# Snowball Family
#aws #cloud #snowball #storage #cloud-migration

This service is for migrating large volume of data to [AWS](Cloud%20Computing/AWS/AWS.md) with Low Cost data transfer service (Petabyte Scale). Snowball can reduce the cost by 1/5th and eliminate the need for bandwidth changes. 

![](Attachments/Pasted%20image%2020230312221507.png)

![](Attachments/Pasted%20image%2020230312221629.png)

## Snowball 
Features:
- E-ink display (shipping information)
- Tamper and weather proof
- Data is encrypted end-to-end using 256 bit encryption
- users Trusted Platform Module (TPM)
- For security purposes, data transfers must be completed within 90 days of snowball being created
- Snowball can Import/Export from [S3](Cloud%20Computing/AWS/Storage/S3.md)
- Comes in 2 sizes 
	- (50 TB) 
	- (80 TB)

# Snowball Edge
similar to Snowball but more storage and local processing

Features:
- LCD Display
- Can undertake local processing and edge-computing workloads
- Can use in a groups of 5 to 10 devices.
- Three options for device configurations:
	- Storage Optimised (24 vCPUs)
	- Compute Optimised (54 vCPUs)
	- GPU Optimised (54 vCPUs)
- Comes in 2 Sizes:
	- 100TB (83 usable)
	- 100TB Clustered (45 TB per node)


# Snow Mobile#
Made for Exabyte size data migration

A 45-foot long ruggedized shipping container, pulled by a semi-trailer truck. transfer up to 100PB per Snowmobile.

AWS personnel will help you connect your network to the snowmobile and when data transfer is complete they'll drive it back to AWS to import into [S3](Cloud%20Computing/AWS/Storage/S3.md) or Glacier

*Security Features*
- GPS Tracking
- Alarm monitoring
- 24/7 video surveillance
- an escort security vehicle while in transit (optional)


![Pasted image 20220714014138](Attachments/Pasted%20image%2020220714014138.png)