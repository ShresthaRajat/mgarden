# Auto Scaling Group (ASG)
#aws #cloud #compute 

A service from [AWS](Cloud%20Computing/AWS/AWS.md) to spin up [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instances as well as remove them automatically according to the situation. 

For example the [ASG](Cloud%20Computing/AWS/Compute/ASG.md) can be hooked up to an [Cloudwatch-Alarms](Cloud%20Computing/AWS/Monitoring/CloudWatch.md#Cloudwatch-Alarms) when the [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instance status check fails. Then [CloudWatch](Cloud%20Computing/AWS/Monitoring/CloudWatch.md) then notifies the [ASG](Cloud%20Computing/AWS/Compute/ASG.md) which spins up a new instance.

![](Attachments/Pasted%20image%2020230305211052.png)

## Scaling Processes
• **Launch** – Adds a new EC2 instance to an Auto Scaling group
• **Terminate** – Removes an EC2 instance from the group
• **AddToLoadBalancer** – Adds instances to an attached ELB or TG
• **AlarmNotification** – Accepts notifications from CloudWatch alarms that
are associated with the group's scaling policies
• **AZRebalance** – Balances the number of EC2 instances in the group
evenly across all of the specified Availability Zones
• **HealthCheck** – Checks the health of the instances and marks an instance as unhealthy if Amazon EC2 or Elastic Load Balancing tells Amazon EC2 Auto Scaling that the instance is unhealthy
• **ReplaceUnhealthy** – Terminates instances that are marked as unhealthy and then creates new instances to replace them
• **ScheduledActions** – Performs scheduled scaling actions
• **Cooldowns** – Used with simple scaling policy to prevent Auto
Scaling from launching or terminating before effects of previous
activities are visible. Default value is 300 seconds (5 minutes)
• **Termination Policy** – Controls which instances to terminate first
when a scale-in event occurs.
• **Termination Protection** – Prevents Auto Scaling from terminating
protected instances
• **Standby State** – Used to put an instance in the `InService` state into
the `Standby` state, update or troubleshoot the instance
• **Lifecycle Hooks** – Used to perform custom actions by pausing instances as the ASG launches or terminates them.

![](Attachments/Pasted%20image%2020230305212652.png)


## Dynamic Scaling
The ASG could be programmed to be certain metrics, or some conditions.

### Target Tracking
This method will use certain metrics to apply ASG actions. There are 4 metrics which are:
• **ASGAverageCPUUtilization**—Average CPU utilization of the Auto
Scaling group
• **ASGAverageNetworkIn**—Average number of bytes received on all
network interfaces by the Auto Scaling group
• **ASGAverageNetworkOut**—Average number of bytes sent out on all
network interfaces by the Auto Scaling group
• **ALBRequestCountPerTarget**—Number of requests completed per
target in an Application Load Balancer target group
![](Attachments/Pasted%20image%2020230305211452.png)

### Target Tracking with SQS
You can use SQS to emit a custom metric to cloudwatch to scale the asg ie. to provision more instances according to the pending messages.
![](Attachments/Pasted%20image%2020230305211657.png)


### Simple scaling
It scales according to the trigger if the alarm goes off after a simple metric set.
![](Attachments/Pasted%20image%2020230305211844.png)

### Step Scaling
Will scale instances with variable alarm trigger, ie. will launch more instance if the metric is higher. Ie the size of alarm breach.
![](Attachments/Pasted%20image%2020230305211858.png)


## Scheduled Scaling
We can also use scheduled scaling to roll out or roll down instances in certain times. 
![](Attachments/Pasted%20image%2020230305212140.png)