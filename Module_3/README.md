# Global Infrastructure and Reliability
When there's high traffic, one data center isn't enough. </br>
The global footprint of AWS allows its infrastructure to be highly available and fault tolerant. </br>

## AWS Global Infrastructure
AWS builds its data centers in large groups called ***Regions*** in locations closest to where the business traffic demands. </br>
Each Region is isolated from every other Region, which means no data goes in or out of it, unless permission is explicitly granted. </br>
There are four business factors that determine which Region to choose

- ***Compliance***
    - Certain companies have data regulations that require its data to reside in specific locations
- ***Proximity***
    - The closer a Region is to the customers, the faster content is delivered to them
- ***Service Availability***
    - Not all Regions have the features that are needed
- ***Pricing***
    - Cost of services vary from Region to Region

### Availability Zones
Within each Region, there are multiple isolated and physically separate ***Availability Zones***, which contain one or more data centers. </br>
They are located far enough to not be all affected by the same natural disaster, but close enough to have low latency. </br>
The best practice is to ***run across two Availability Zones in a Region***, which means redundantly deploying the infrastructure in two AZs. </br>
Many AWS services are ***regionally scoped***, which means they run synchronously across multiple AZs. One example is ELB (Elastic Load Balancing) </br>

## Edge Locations
When there are customers all over the world or in cities not close to one of the Regions, copies of data can be cached locally to accelerate communication. </br>
This concept is called ***Content Delivery Networks*** (CDNs), which are commonly used all over the world. </br>
Here are two Amazon services that use Edge locations. </br>

### Amazon CloudFront
A CDN service that helps deliver data, video, applications and APIs to customers around the world with low latency and high transfer speeds. </br>

### Amazon Route 53
A domain name service (DNS) that helps directing customers to the correct web locations with reliably low latency. </br>

### Amazon Outposts
A service where AWS installs a fully operational mini Region in a company's own data center. </br>

## How to Provision AWS Resources
In AWS, interaction with services is through using APIs, which are application programming interfaces. Meaning that there are pre determined ways to interact with services in order to provision, configure and manage AWS resources. </br>
There are three ways to interact with services. </br>

- ***AWS Management Console***
    - Web-based
    - Access recently used services
    - Search for services by name, keyword or acronym
    - Includes wizards and automated workflows
    - Monitor resources
    - View alarms
    - Access billing information
- ***AWS Command Line Interface (AWS CLI)***
    - Control multiple AWS services directly
    - Automate actions through scripts
    - Examples
        - Launch Amazon EC2 instances
        - Connect Amazon EC2 instances to specific Auto Scaling groups
- ***Software Development Kits (SDKs)***
    - Perform actions through APIs designed on various programming languages or platforms
    - Use AWS services with existing applications
    - Create entirely new applications that run on AWS
    - Documentation and sample code provided
    - Supports C++, Java, .NET and more

### AWS Elastic Beanstalk
A service that builds Amazon EC2-based environments based on desired configurations, which can be saved and deployed again easily. </br>
This provides the convenience of not having to provision and manage all of the pieces separately, while still having the visibility and control of the underlying resources. </br>
Here are tasks that could be performed

- Adjust capacity
- Load balancing
- Automatic scaling
- Application health monitoring

All of this enables companies to focus on business applications and not the infrastructure. </br>

### AWS CloudFormation
An ***infrastructure as code*** tool that supports definition of a wide variety of AWS resources in a declarative way using JSON or YAML text-based documents called CloudFormation templates. </br>
This allows companies to define what should be built without specifying the details of how it's built, as the CloudFormation engine will take care of calling the APIs behind the scenes. </br>

CloudFormation isn't just limited to EC2-based solutions, it supports many different AWS resources such as storage, databases, analytics, machine learning and more. </br>
In summary, this service provisions resources in a safe and repeatable manner, enabling companies to frequently build their infrastructures and applications without having to perform manual actions. It determines the right operations to perform when managing the stack and rolls back changes automatically if it detects errors. </br>

# Additional Resources
- [Global Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/)
- [Interactive map of the AWS Global Infrastructure](https://www.infrastructure.aws/)
- [Regions and Availability Zones](https://aws.amazon.com/about-aws/global-infrastructure/regions_az)
- [AWS Networking and Content Delivery Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/)
- [Tools to Build on AWS](https://aws.amazon.com/tools/)
- [AWS Customer Stories: Content Delivery](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23content-delivery)
