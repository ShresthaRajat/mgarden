# AWS Storage Gateway
#aws #cloud #networking #storage 

AWS Storage Gateway is a set of hybrid cloud storage services provided in [[AWS]] that provide on-premises access to virtually unlimited cloud storage.
![](Attachments/Pasted%20image%2020230309015050.png)

## File Gateway
• File gateway provides a virtual on-premises fileserver
• Store and retrieve files as objects in Amazon [S3](Cloud%20Computing/AWS/Storage/S3.md)
• Use with on-premises applications, and [EC2](Cloud%20Computing/AWS/Compute/EC2.md)-based applications that need file storage in S3 for objectbased workloads
• File gateway offers SMB or  [NFS](Networking/NAS.md#NFS)-based access to data in Amazon S3 with local caching
![](Attachments/Pasted%20image%2020230309015037.png)

## Volume Gateway

• The volume gateway supports block-based volumes
• Block storage – iSCSI protocol
• Cached Volume mode – the entire dataset is stored on S3 and a cache of the most frequently accessed data is cached on-site
• Stored Volume mode – the entire dataset is stored on-site and is asynchronously backed up to S3 ([EBS](Cloud%20Computing/AWS/Storage/EBS.md) point-in-time snapshots). Snapshots are incremental and compressed.
![](Attachments/Pasted%20image%2020230309015157.png)


# Tape Gateway
• Used for backup with popular backup software
• Each gateway is preconfigured with a media changer and tape drives. Supported by NetBackup, Backup Exec, Veeam etc.
• When creating virtual tapes, you select one of the following sizes: 100 GB, 200 GB, 400 GB, 800 GB, 1.5 TB, and 2.5 TB
• A tape gateway can have up to 1,500 virtual tapes with a maximum aggregate capacity of 1 PB
• All data transferred between the gateway and AWS storage is encrypted using SSL
• All data stored by tape gateway in S3 is encrypted server-side with Amazon S3-Managed Encryption Keys (SSE-S3)

![](Attachments/Pasted%20image%2020230309015301.png)