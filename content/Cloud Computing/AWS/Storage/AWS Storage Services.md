# AWS Storage Services
#cloud #aws #storage 

## Block File and Object Storage Systems:

[Instance Store](Cloud%20Computing/AWS/Storage/Instance%20Store.md) is a ephemeral storage similar to EBS which exists on the same server rack as the [[EC2]] instance and can be mounted for a high performance Block Storage.

[[EBS]] is accessed as a drive mounted to [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instance usually multiple EBS attached to one [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instance.

[EFS](Cloud%20Computing/AWS/Storage/EFS.md) is mounted as a [NAS](Networking/NAS.md) in using [[Networking/NAS.md#NFS]] [Linux](Cyber%20Operations/Operation%20Tools/Linux.md) based [EC2](Cloud%20Computing/AWS/Compute/EC2.md) Instances.

[[S3]] meanwhile is used for Object storage System to store blobs of data, to be accessed through various mediums.

[S3 Gateway Endpoint](Cloud%20Computing/AWS/Storage/S3.md#S3%20Gateway%20Endpoint) is used to connect an [[EC2]] instance via a private ip instead of a public route.


![](Attachments/Pasted%20image%2020230309004811.png)