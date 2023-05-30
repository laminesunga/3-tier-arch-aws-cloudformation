
# Deploy a 3-tier Architecture in AWS using CloudFormation.


![Alt text](Screenshot%20from%202023-05-29%2022-04-26.png)


### Resources created:

In the Web Tier

* Two public subnets and a public route table and associate it with the 2 public subnets
* Internet Gateway and NAT Gateway
* Application Load Balancer
* Lunch two instances with Auto Scaling Group
* Security Group for web tier and ALB

In the App tier

* Two Private subnets and a private route table and associate it with the 2 Private subnets.
* Application Load Balancer
* Lunch two App instances with Auto Scaling Group
* Security Group for App tier and ALB

Database Tier

* Two Private subnets and a private route table and associate it with the 2 Private subnets.
* MySql RDS Database with Multi-AZ standby instance.
* The Database Security Group allows inbound traffic for MySQL from the App Instances Security Group.

Deploy Bastion Host 

This is a special-purpose instance that is used to securely access and manage other instances within a private network. We could also using Ansible to sacale and automate.

* Deploy the EC2 Bastion Host in the third public subnet
* EC2 Securit Group allows SSH inbound from your local IP address.
* Public route table for Bastion Host.
* Grant the Bastion Host EC2 instance Security Group access to resources in the Web, App, and Database Tier.

