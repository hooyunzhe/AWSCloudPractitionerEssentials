# Networking
Applications can't be used if they're fully isolated, which is why networking is an important aspect of building the IT infrastructure of businesses. </br>

## Connectivity to AWS
In the same way, AWS resources can't be accessed without connectivity. </br>
Here are some of the networking services AWS provides. </br>

### Amazon Virtual Private Cloud (Amazon VPC)
A service that lets companies provision a logically isolated section of the AWS Cloud where resources are launched in a self-defined virtual network. </br>
These resources can be public facing or private with no internet access, which are usually for backend services like databases or application servers. </br>
The public and private grouping of resources are known as subnets which are ranges of IP addresses in a VPC. </br>

### Internet gateway
In order to allow traffic from the public internet to flow into and out of public-facing VPCs, internet gateways (IGWs) must be attached. </br>
For VPCs with internal private resources, private gateways are needed to only allow traffic from approved networks. </br>

### Virtual private gateway
Virtual private gateways are used to create VPN connections between private networks, like on-premises data centers or internal corporate networks, to VPCs. </br>
The problem with VPN connections is that despite being private and encrypted, they still use a regular internet connection that has bandwidth which is shared by many people using the internet. </br>

### AWS Direct Connect
A service that lets companies establish a dedicated private connection between the data center and a VPC. </br>
This helps reduce network costs and increase the amount of bandwidth that can travel through the network. </br>

## Subnets and Network Access Control Lists
VPCs can be thought of as hardened fortresses where nothing goes in or out without explicit permission. </br>
AWS has a wide range of tools that cover every layer of security

- Network hardening
- Application security
- User identity
- Authentication and authorization
- Distributed denial-of-service (DDoS) prevention
- Data integrity
- Encryption

### Subnets
Sections of a VPC in which resources can be grouped based on security or operational needs. </br>
They can be public or private depending on the resources in them, they can also communicate with each other. </br>

### Network traffic in a VPC
When customers request data from applications hosted in the AWS Cloud, this request is sent as a packet, which is a unit of data sent over the internet or a network. </br>
Before a packet can enter into or exit from a subnet, it will be checked for permissions, which indicate who sent the packet and how it's trying to communicate with the resources in a subnet. </br>
The VPC component that checks packet permissions for subnets is a ***network access control list (ACL)***

### Network ACLs
Virtual firewalls that control inbound and outbound traffic at the subnet level. </br>
Each AWS account includes a default network ACL, which can be used to configure the VPC. By default, it allows all inbound and outbound traffic, but can be modified by adding rules. </br>
Custom network ACLs can also be created, they deny all inbound and outbound traffic until new rules are added. </br>
All network ACLs have an explicit deny rule, which ensures that packets are denied if they don't match any of the rules of the list. </br>

### Stateless packet filtering
Network ACLs don't remember any previous requests, they check every packet that crosses its border both ways. </br>
After a packet enters a subnet, its permissions must be evaluated for resources within the subnet, such as Amazon EC2 instances. </br>
The VPC component that checks packet permissions for an Amazon EC2 instance is a ***security group***. </br>

### Security groups
Virtual firewalls that control inbound and outbound traffic for Amazon EC2 instances. </br>
By default, they deny all inbound traffic and allow all outbound traffic. Just like network ACLs, custom rules can be added to configure which traffic should be allowed. </br>
Multiple Amazon EC2 instances can be associated with the same security group, or they can each use different security groups. </br>

### Stateful packet filtering
Unlike network ACLs, security groups remember previous decisions made for incoming packets. </br>
When a packet response for a request returns to the instance, the security group remembers the previous request and allows the response to proceed regardless of inbound traffic rules. </br>

With both network ACLs and security groups, companies can configure custom rules for the traffic in their VPCs. </br>

## Global Networking
So far, it has all been about how companies interact with their AWS infrastructure, but what about the customers' perspective?
To end users, it should be as simple as entering the website into their browsers. This is in fact the case for most websites, but what makes this possible? </br>

### Domain Name System (DNS)
DNS resolution is what makes it possible, it involves a customer DNS resolver communicating with a company DNS server. </br>
It's the process of translating a domain name to an IP address. </br>

### Amazon Route 53
A DNS web service that gives developers and businesses a reliable way to route end users to interact with applications hosted in AWS. </br>
It connects user requests to infrastructure running in AWS, such as Amazon EC2 instances and load balancers. It can also route users to infrastructure outside of AWS. </br>

Another feature of Route 53 is the ability to manage the DNS records for domain names. New domain names can be registered directly in Route 53. </br>
DNS records for existing domain names managed by other domain registrars can also be transferred to the service. </br>

Amazon CloudFront, a content delivery service, works together with Amazon Route 53 to deliver content to customers. </br>

# Additional Resources
- [Networking and Content Delivery on AWS](https://aws.amazon.com/products/networking)
- [AWS Networking & Content Delivery Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/)
- [Amazon Virtual Private Cloud](https://aws.amazon.com/vpc)
- [What is Amazon VPC?](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [How Amazon VPC works](https://docs.aws.amazon.com/vpc/latest/userguide/how-it-works.html)
