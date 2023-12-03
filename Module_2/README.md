# Compute in the Cloud
Amazon Elastic Compute Cloud (EC2) is highly flexible, cost effective and quick when compared to running servers on premises in a data center. </br>
The following has to be done with traditional on-premises resources

- Spend time researching the type of servers and how many are needed
- Spend money upfront to purchase hardware
- Wait for the servers to be delivered to you
- Install the servers in your physical data center
- Make sure they are secure and powered up
- Make all the necessary configurations

With EC2, Amazon already took care of all the hard parts, companies can

- Provision and launch EC2 instances within minutes
- Stop using them when workloads have finished running
- Pay only for the compute time that's used when instances are running
- Save costs by paying only for the exact server capacity that's needed

### Multitenancy
EC2 runs on top of physical host machines managed by AWS using virtualization technology. </br>
A hypervisor is responsible for sharing the underlying physical resources between instances, also known as virtual machines. </br>
It also makes sure that EC2 instances are secure and isolated from each other. </br>

### How Amazon EC2 Works
- ***Launch***
    - Being by selecting a template with basic configurations which include
        - Operating system
        - Application server
        - Other applications
    - Next, select the instance type, which is the hardware configuration of the instance
    - Finally, specify the security settings to control the network traffic that can flow into and out of the instance
- ***Connect***
    - There are many ways to connect to the instance
        - Programs and applications have multiple different methods to connect directly to the instance and exchange data
        - Users can connect to the instance by logging in and accessing the computer desktop
- ***Use***
    - After connecting to the instance, commands can be run to
        - Install software
        - Add storage
        - Copy and organize files
        - etc

## Amazon EC2 Instance Types
- ***General purpose***
    - Balance of compute, memory and networking resources
    - Example workloads
        - Application servers
        - Backend servers for enterprise applications
        - Small and medium databases
    - Suitable for applications with roughly equivalent needs in all resource areas
- ***Compute optimized***
    - More compute resources with high-performance processors
    - Example workloads
        - High-performance web servers
        - Compute-intensive application servers
        - Dedicated gaming servers
        - Batch-processing workloads requiring many transactions in a single group
    - Suitable for compute-bound applications
- ***Memory optimized***
    - Designed to deliver fast performance for memory-intensive workloads
    - Example workloads
        - High-performance database
        - Real-time processing of a large amount of unstructured data
    - Suitable for applications with high memory needs
- ***Accelerated computing***
    - Higher efficiency when performing certain functions with hardware accelerators or coprocessors
    - Example functions
        - Floating-point number calculations
        - Graphics processing
        - Data pattern matching
    - Example workloads
        - Graphics applications
        - Game streaming
        - Application streaming
    - Suitable for specific applications that benefit from hardware accelerators
- ***Storage optimized***
    - Designed for workloads that require high, sequential read and write access to large datasets on local storage
    - Input/output operations per second (IOPS) is a metric that measures the performance of a storage device
    - Example workloads
        - Distributed file systems
        - Data warehousing applications
        - High-frequency online transaction processing (OLTP) systems
    - Suitable for applications with high IOPS requirements

## Amazon EC2 Pricing
- ***On-Demand***
    - Instances that run continuously until they're stopped
    - Ideal for short-term and irregular workloads that cannot be interrupted
    - Example use cases
        - Developing, testing and running applications that have unpredictable usage patterns
- ***Reserved Instances***
    - Two types of billing discount can be applied to the use of On-Demand Instances
    - Either with a 1-year or 3-year term, with the latter giving more cost savings
    - ***Standard Reserved Instances***
        - Good fit for steady-state applications with fixed instance types, size and the AWS Region to run in
        - Specifications required to state include
            - Instance type and size: for example, _m5.xlarge_
            - Platform description (operating system): for example, _Microsoft Windows Server or Red Hat Enterprise Linux
            - Tenancy: Default tenancy or dedicated tenancy
        - Option to specify an Availability Zone to get EC2 capacity reservation, which ensures that the amount of EC2 instances will be available when needed
    - ***Convertible Reserved Instances***
        - Suitable for running instances with different instance types or across different Availability Zones
        - Trade in a deeper discount when flexibility is required
    - At the end of the term, the instances can continue to be used without interruption
    - But On-Demand rates will be charged until one of the following is done
        - The instance is terminated
        - A new Reserved Instance that matches the attributes is purchased
- ***EC2 Instance Savings Plan***
    - Hourly spend commitment to an instance family and Region for a 1-year or 3-year term
    - Savings of up to 72% compared to On-Demand rates, which is similar to that of Standard Reserved Instances
    - Usage beyond the commitment is charged at regular On-Demand rates
    - Good when flexibility is needed, as the Availability Zone, instance size, OS or tenancy doesn't affect the savings
    - Doesn't include an EC2 capacity reservation option
- ***Spot Instances***
    - Utilize unused Amazon EC2 computing capacity
    - Savings of up to 90% compared to On-Demand rates
    - Ideal for workloads with flexible start and end times, or those that can withstand interruptions
- ***Dedicated Hosts***
    - Physical servers with fully dedicated Amazon EC2 instance capacity
    - There are two types
        - On-Demand Dedicated Hosts
        - Dedicated Hosts Reservations
    - Most expensive out of all options

## Scaling Amazon EC2
Most businesses have ***varying customer workloads***, there'll be times with high demand and times with no demand at all. </br>
The ***on-premises data center dilemma*** is the question of how much is the right amount of hardware to purchase? </br>
Buying for the average usage means there'll be no money wasted on average, but it won't be enough for the peak loads </br>
Buying for the max load results not just in waste of resources, but waste of money as well. </br>
This is where AWS comes in to tackle the impossible problem of on-premises data centers. </br>

### Amazon EC2 Auto Scaling
This service enables companies to automatically add or remove Amazon EC2 instances in response to changing demand, which helps maintain a greater sense of application availability. </br>
There are two approaches

- ***Dynamic scaling*** responds to changing demand
- ***Predictive scaling*** automatically schedules the right number of Amazon EC2 instances based on predicted demand

They can be used together to achieve faster scaling </br>
When creating an ***Auto Scaling Group***, there are three things to configure

- ***Minimum capacity*** is the number of Amazon EC2 instances that'll always be running
- ***Desired capacity*** is the number of desired Amazon EC2 instances that defaults to the minimum capacity if not set
- ***Maximum capacity*** is the maximum number of Amazon EC2 instances that can be scaled to

All of this results in a cost-effective architecture that provides the best customer experience while reducing expenses. </br>

## Directing Traffic with Elastic Load Balancing
When there are multiple Amazon EC2 instances running the same program serving the same purpose, how does an incoming request know which one to go to? </br>
This is where the ***Elastic Load Balancing*** comes in. </br>
Acting as a single point of contact for all incoming web traffic to the Auto Scaling Group, it automatically distributes them among the Amazon EC2 instances to make sure that no single one has to carry the bulk of it. </br>
The combined use of Elastic Load Balancing and Amazon EC2 Auto Scaling ensures that applications provide high performance and availability. </br>

## Messaging and Queuing
When applications communicate directly, problems arise when one of them fails. </br>
This is called a ***tightly coupled*** architecture, which is flawed and unreliable. </br>
A more reliable architecture is ***loosely coupled***, where failures are isolated and don't cascade throughout the entire system. </br>
This can be achieved by designing applications with a ***microservices*** approach. </br>
Here are the two services that facilitate application integration. </br>

### Amazon Simple Queue Service (SQS)
A messaging queue service that enables software components to send, store and receive messages between each other, without losing messages or requiring other services to be available. </br>
Here's the flow

- Applications send messages into a queue
- Users or services retrieve them from the queue
- Users or services process and delete them from the queue

### Amazon Simple Notification Service (SNS)
A publish/subscribe service that enables software components to send messages to end users all at one go. </br>
Subscribers can be web servers, email addresses, AWS Lambda functions or other options. </br>
Here's the flow

- Applications create topics for messages of different categories
- Subscribers can subscribe to any number of topics
- Applications publish messages for all topics
- Subscribers only receive messages for the topics they subscribed

## Additional Compute Services
Although EC2 instances are flexible, reliable and scalable, there might be better alternatives depending on the use case. </br>
Many management processes are required, such as the initial set up, scaling configuration, patching when new software packages come out and ensuring solutions have been architected to be hosted in a highly available manner. </br>
This is where the term ***serverless*** comes in, it means that the underlying infrastructure or instances that host the applications are hidden away and cannot be accessed. </br>
All of the management aspects of the underlying environment, like provisioning, scaling, high availability and maintenance, are taken care of. </br>
There are various serverless services that AWS offers. </br>

### Amazon Lambda
A service that allows code to run without the need of provision or management or servers. </br>
Here's the flow

- Code is uploaded to Lambda
- Set triggers from event sources such as AWS services, mobile applications or HTTP endpoints
- Lambda runs the code only when triggered
- Pay only for the compute time that's used

### Containers
Provide a standard way to package an application's code and dependencies into a single object. </br>
Suitable for processes and workflows with essential requirements for security, reliability and scalability. </br>

### Amazon Elastic Container Service (Amazon ECS)
A highly scalable and high-performance container management system. </br>
Supports Docker containers and API calls to launch and stop Docker-enabled applications. </br>
Docker is an open-source software platform that enables quick building, testing and deploying of applications. </br>
Amazon ECS supports both Docker Community Edition and Docker Enterprise Edition, which is subscription-based. </br>

### Amazon Elastic Kubernetes Service (Amazon EKS)
A fully managed service for running Kubernetes on AWS. </br>
Kubernetes is an open-source system that enables deployment and management of containerized applications at scale. </br>
AWS actively works together with the Kubernetes community to allow new features and functionalities to be applied easily to applications managed by Amazon EKS. </br>

### Amazon Fargate
A serverless compute engine for containers that works with both Amazon ECS and Amazon EKS. </br>
As AWS Fargate manages the server infrastructure, there's no need to provision or manage servers. </br>
This allows companies to focus on innovating and developing applications. </br>
Again, only the resources that are required to run the containers need to be paid. </br>

# Additional Resources
- [Compute on AWS](https://aws.amazon.com/products/compute)
- [AWS Compute Blog](https://aws.amazon.com/blogs/compute/)
- [AWS Compute Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/compute-services.html)
- [Hands-On Tutorials: Compute](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23compute&awsf.getting-started-content-type=content-type%23hands-on)
- [Category Deep Dive: Serverless](https://aws.amazon.com/getting-started/deep-dive-serverless/)
- [Amazon EC2 Reserved Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-reserved-instances.html)
- [How Savings Plans apply to usage](https://docs.aws.amazon.com/savingsplans/latest/userguide/sp-applying.html)
