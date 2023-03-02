# Storage Gateway
#aws #cloud #storage #networking

A networking service by [AWS](Cloud%20Computing/AWS/AWS.md) which provides a seamless and secure integration between your organization's on-premise IT environment and AWS's storage infrastructure.


## File Gateway (NFS) (store your files in S3)

To extend your local storage to S3



## Volume Gateway (iSCSI) (stores copies of your HDD in S3)

Presents your application with Internet Small Computer Systems Interface block protocol.

Data that is written to volumes can be asyncronously backed up as point-in-time snapshots of the volumes, and stored in the cloud as AWS EBS Snapshots.

Snapshots are incremental backups

Treats your local HDD as EBS.

Primary data is stored locally, while asyncronously backing up that data to AWS


- Stored Volumes (primary data is on onsite) (1GB - 16TB)
- Cached Volumes (primary data is in aws) (1GB - 32GB)

## Tape Gateway (VTL) (virtual tape library)

A durable, cost-effective solution to archive your data in the AWS Cloud

The VTL interface it provides let you leverage existing tape based backup application infrastructure.

Store data on virtual tape cartridges that you create on your 

![Pasted image 20220724155600](Cloud%20Computing/AWS/Migration%20&%20Transfer/Pasted%20image%2020220724155600.png)