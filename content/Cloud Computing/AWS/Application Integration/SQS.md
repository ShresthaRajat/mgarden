# SQS
#aws #cloud #serverless #microservices  #decoupleing #queue

First-ever [AWS](Cloud%20Computing/AWS/AWS.md) service that was made publicly available. (Oldest service). 
Message Queue service enables web services applications to queue messages.
Acts like a buffer between the components between different components.
Can set up an Autoscaling group to SQS which is a great practice.
Pick up messages using a “poll”.
Mostly used for pull-based operations.


## Features
-   Allow us to decouple the components of an application so that they are independent
-   Pull based message store (Poll) (256 KB max size of the text in any format)
-   Retrieve the messages using SQS API
-   Text Data (XML, JSON and unformatted text)
-   Guarantees that message will be processed at least once
-   The default retention period is 4 days
-   Max message retention time is 14 days


## Visibility Timeout
-   Default is 30 seconds
-   If a message isn't processed within 30 seconds, the item will reappear
-   You can increase the visibility Timeout.    
-   Max timeout is 12 hours    

  

## Polling  
![](https://lh3.googleusercontent.com/kX3LN5a7jK4UmacSq5znYiNFZuQL8dXL4uz-QOqbGQ_UR_aUdyJ3WCAm3NDREirE23EQX7IrfiTQWRzDBKjCvALs7qcJpaqMdEjaOKreRbHWKxe2Q8H54O4qlwSczdLOqCMbl1eYSFWGJCEUcr_Kag)


SQS Delay Queue postpones delivery of new messages (makes them invisible)(0s-900s). It only affects standard queues but it will affect the whole FIFO Queue. (e.g. for confirming the order in E-commerce).

  

Using S3 for large SQS message (256KB-2GB) (Amazon SQS Extended Client Library for Java, AWS SDK for java)

**

Fully managed queing services that enables you to decouple a big complex architecture to a simpler one. It is primarily for Application integration.

pull based.

Messege size can be between 1 byte to 256 KB

Extended storage option is availabe on Java SDK which allows storage of message upto 2GB but will be required to be stored in S3.

Message retention by default is 4 days

from min of 60 seconds to max of 14 days


## Standard Queues
![Pasted image 20220724103848](Cloud%20Computing/AWS/Application%20Integration/Pasted%20image%2020220724103848.png)
Allows nearly-unlimited number of transactions per second
Guarantees that a message will be delivered at least once.
Which means more than one copy of message could be potentially delivered out of order.
Provides best-effort ordering that helps ensure a message is generally delivered in the same order that it was sent.


## FIFO Queue
![Pasted image 20220724104025](Cloud%20Computing/AWS/Application%20Integration/Pasted%20image%2020220724104025.png)

supports multiple ordered message groups within a single queue
Limited to 300 transactions per second
Have all of the capabilities of a standard queue.

## Visibility Timeout
To prevent another app from reading a message which is already being processed by another app. This help


## polling
![Pasted image 20220724104406](Cloud%20Computing/AWS/Application%20Integration/Pasted%20image%2020220724104406.png)



![Pasted image 20220724104428](Cloud%20Computing/AWS/Application%20Integration/Pasted%20image%2020220724104428.png)