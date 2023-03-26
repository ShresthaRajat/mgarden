# WAF

#aws #cloud 

AWS WAF is a web application firewall [WAF](Cyber%20Security/Cloud%20Security/WAF.md) by[AWS](Cloud%20Computing/AWS/AWS.md) that helps protect apps and APIs against bots and exploits that consume resources, skew metrics, or cause downtime.

- WAF lets you create rules to filter web traffic based on conditions  hat include IP addresses, HTTP headers and body, or custom URIs
- WAF makes it easy to create rules that block common web exploits like SQL injection and cross site scripting
![](Attachments/Pasted%20image%2020230322010416.png)


• Web ACLs – You use a web access control list (ACL) to protect a set of AWS resources
• Rules – Each rule contains a statement that defines the inspection criteria, and an action to take if a web request meets the criteria
• Rule groups – You can use rules individually or in reusable rule groups

• IP Sets - An IP set provides a collection of IP addresses and IP address ranges that you want to use together in a rule statement
• Regex pattern set - A regex pattern set provides a collection of regular expressions that you want to use together in a rule statement
A rule action tells AWS WAF what to do with a web request when it matches the criteria defined in the rule: 
• Count – AWS WAF counts the request but doesn't determine whether to allow it or block it. With this action, AWS WAF continues processing the remaining rules in the web ACL 
• Allow – AWS WAF allows the request to be forwarded to the AWS resource for processing and response 
• Block – AWS WAF blocks the request and the AWS resource responds with an HTTP 403 (Forbidden) status code

Match statements compare the web request or its origin against conditions that you provide.
![](Attachments/Pasted%20image%2020230322010733.png)