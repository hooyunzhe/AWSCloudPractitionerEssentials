# Security
Security is a vital aspect of running businesses on the cloud, no company wants their applications breached or data leaked. </br>
AWS Cloud offers various security mechanisms, like the shared responsibility model. </br>

## AWS Shared Responsibility Model
There are a variety of resources that companies can create in the AWS cloud, but the question is who's responsible for keeping them secure, the company (the customer) or AWS?
The answer is ***both***, as AWS environments shouldn't be treated as a single object. Instead, they should be treated as a collection of parts that build upon each other. </br>

The model divides into ***customer responsibilities (security in the cloud)*** which are

- Customer Data
- Platform, Applications, Identity and Access Management
- Operating Systems, Network and Firewall Configuration
- Client-side Data Encryption | Server-side Encryption | Networking Traffic Protection

and ***AWS responsibilities (security of the cloud)*** which are

- Software
- Compute | Storage | Database | Networking
- Hardware / AWS Global Infrastructure
- Regions | Availability Zones | Edge Locations

This is similar to division of responsibilities between a homeowner and a homebuilder. The builder (AWS) is responsible for constructing the house and ensuring it's solidly built, while it's the responsibility of the homeowner (the customer) to secure everything in the house by ensuring that the doors are closed and locked. </br>

***Customers: Security in the cloud***

- Customers are responsible for the security of everything that they create and put _in_ the AWS Cloud
- They maintain complete control over the content and are responsible for managing security requirements of their content, including
    - What content are stored on AWS
    - Which AWS services are used
    - Who has access to the content
    - How access rights are granted, managed and revoked
- The steps taken will depend on factors such as
    - The services that are used
    - The complexity of the systems
    - Specific operational and security needs
- Steps include
    - Selecting, configuring and patching the operating systems that will run on Amazon EC2 instances
    - Configuring security groups and managing user accounts

***AWS: Security of the cloud***

- AWS is responsible for the security _of_ the cloud
- AWS operates, manages and controls the components at all layers of infrastructure, including
    - Host operating system
    - Virtualization layer
    - Physical security of data centers
- AWS is responsible for protecting the global infrastructure that runs all of the services offered in the AWS Cloud, including
    - AWS Regions
    - Availability Zones
    - Edge locations
- AWS manages the security of the cloud, specifically the physical infrastructure that hosts the resouces, including
    - Physical security of data centers
    - Hardware and software infrastructure
    - Network infrastructure
    - Virtualization infrastructure
- AWS provides several reports from third-party auditors, who have verified its compliance with a variety of computer security standards and regulations

## User Permissions and Access
When an AWS account is created, the only user is the ***root user***, who's the owner of the account and has permission to do anything. </br>
Since this user is so powerful, it's recommended to turn on ***multi-factor authentication (MFA)*** to ensure that logging in requires not only the email and password, but also a randomized token. </br>
Having only one user is not practical as not all employees should have the same level of access, as such, a granular way of controlling access is by using ***AWS Identity and Access Management***</br>

### AWS Identity and Access Management (IAM)
A service that enables companies to manage access to AWS services and resources securely. </br>
It gives companies the flexibility to configure access based on the specific operational and security needs, by using a combination of IAM features including

- IAM users, groups and roles
- IAM policies
- Multi-factor authentication

### AWS account root user
The user that's accessed by signing in with the email address and password used to create the AWS account, with complete access to all the AWS services and resources in the account. </br>

> ***Best practice:*** </br>
The root user should **not** be used for everyday tasks. </br>
Instead, create the first IAM user and assign it permissions to create other users. </br>
Then, continue to create other IAM users for performing regular tasks. </br>
Only use the root user when performing a limited number of tasks that are only available to the root user, such as changing the email address or AWS support plan. </br>
More information: "Tasks that require root user credentials" in the [AWS Account Management Reference Guide](https://docs.aws.amazon.com/accounts/latest/reference/root-user-tasks.html)

### IAM users
Identities that represent the person or application that interacts with AWS services and resources. They consist of a name and credentials. </br>
By default, they have no permissions when they're created. To allow them to perform specific actions in AWS, such as launching an Amazon EC2 instance or creating an Amazon S3 bucket, the necessary permissions must be granted. </br>

> ***Best practice:*** </br>
Create **individual** IAM users for each person who needs to access AWS, even if they require the same level of access. </br>
This provides additional security by allowing each IAM user to have a unique set of security credentials.

### IAM policies
Documents that allow or deny permissions to AWS services and resources, enabling companies to customize users' levels of access to resources. </br>
Example: allowing users to access all of the Amazon S3 buckets within the account, or just one specific bucket. </br>

> ***Best practice:*** </br>
Follow the security principle of **least privilege** when granting permissions. </br>
This will help prevent users or roles from having more permissions than needed to perform their tasks. </br>
Example: if an employee needs access to only a specific bucket, specify the bucket in the IAM policy instead of granting the employee access to all of the buckets in the account.

### Example: IAM policy
```json
{
    "Version": "2012-10-17",
    "Statement": {
        "Effect": "Allow",
        "Action": "s3:ListObject",
        "Resource": "arn:aws:s3:::AWSDOC-EXAMPLE-BUCKET"
    }
}
```
Here's an example IAM policy that allows permission to access the objects in the Amazon S3 bucket with ID: _AWSDOC-EXAMPLE-BUCKET_ </br>
Additional policies must be attached to allow permission to access other services and perform other actions in AWS. </br>
Instead of assigning permissions to each individual IAM user, a more efficient way would be to place users into an ***IAM group***

### IAM groups
A collection of IAM users that will all be granted permissions specified in the policies that's assigned to it. </br>
This makes it easier to adjust permissions when an employee transfers to another role, where they're simply removed from the previous group and added to the new group, ensuring that they only the permissions that are required for their current role. </br>
When temporary permissions are needed, ***IAM roles*** can be utilized. </br>

### IAM roles
Identities that users can assume to gain temporary access to permissions. </br>
Before an IAM user, application or service can assume an IAM role, they must be granted permission to switch to the role and abandon all previous permissions of the previous role. </br>

### Multi-factor authentication
Provides an extra layer of security for AWS accounts by requiring a second form of authentication through a separate device. </br>
The AWS MFA device could be a hardware security key, a hardware device or an MFA application on a device such as a smartphone. </br>
It's the best practice to enable MFA for the root user and IAM users, this will keep the AWS account safe from unauthorized access. </br>

## AWS Organizations
As companies grow, it's important to have a separation of duties. </br>
For example, developers should have access to development resources while accounting staff should have access to billing information, or even have business units separate so that they can experiment with AWS services without affecting each other. </br>
Having to keep track of multiple accounts, some might have wrong permissions. One way to install order and to enforce who is allowed to perform certain functions in what account is to make sure of an AWS service called ***AWS Organizations***. </br>

It provides a central location to consolidate and manage multiple AWS accounts. When an organization is created, a **root** will be automatically created. It's the parent container for all the accounts. </br>
***Service control policies (SCPs)*** can be used to centrally control permissions for the accounts in the organization, this enables companies to place restrictions on the AWS services, resources and individual API actions that users and roles in each account can access. </br>

### Organizational units
In AWS Organizations, accounts can be grouped into ***organizational units (OUs)*** to make it easier to manage accounts with similar business or security requirements. </br>
When a policy is applied to an OU, all the accounts in the OU automatically inherit the permissions specified in the policy. </br>
By organizing separate accounts into OUs, workloads or applications that have specific security requirements can be isolated more easily. </br>
For instance, accounts that can access only the AWS services that meet certain regulatory requirements, can be put into one OU. Then, a policy can be attached to the OU that blocks access to all other AWS services that do not meet the regulatory requirements. </br>

## Compliance
In every industry, there are specific standards that need to be upheld and companies will be audited or inspected to ensure that they've met those standards. </br>
For example, software that deals with consumer data in the EU needs to comply with ***General Data Protection Regulation (GDPR)*** and healthcare applications in the US need to meet compliance requirements of ***Health Insurance Portability and Accountability Act (HIPAA)***. </br>

Whatever the compliance need is, companies need some tools to be able to collect documents and records as well as inspect their AWS environment to check if they meet the compliance regulations that they're under. </br>
AWS has already built out data center infrastructure and networking following industry best practices for security, customers of AWS inherit all the best practices of AWS policies, architecture and operational processess. </br>
AWS complies with a long list of assurance programs that can be found online. This means that companies can focus on meeting compliance within their own architectures that are built on top of AWS. </br>
As the customer owns the data in AWS, companies can employ multiple different encryption mechanisms to keep data safe, either through building it on top of AWS or using the features that already exist in many services. For many services, enabling data protection is a configuration setting on the resource. </br>

### AWS Artifact
A service that provides on-demand access to AWS security and compliance reports and select online agreements. </br>
It consists of two main sections:

- ***AWS Artifact Agreements***
    - For companies that need to sign agreements with AWS regarding the use of certain types of information throughout AWS services
    - Review, accept and manage agreements for an individual account and for all accounts in AWS Organizations
    - Offers different types of agreements to address the needs of customers who are subject to specific regulations, such as HIPAA
- ***AWS Artifact Reports***
    - For employees of companies that need more information about their responsibility for complying with certain regulatory standards
    - Provides compliance reports from third-party auditors, who have tested and verified that AWS is compliant with a variety of global, regional and industry-specific security standards and regulations
    - Remains up to date with the latest reports released

Here are some of the security and compliance reports AWS Artifact provides

- AWS ISO certifications
- Payment Card Industry (PCI) reports
- Service Organization Control (SOC) reports

### Customer Compliance Center
Resources for further learning on AWS compliance. </br>
Read customer compliance stories to discover how companies in regulated industries have solved various compliance, governance and audit challenges. </br>
Access compliance whitepapers and documentation on topics such as

- AWS answers to key compliance questions
- An overview of AWS risk and compliance
- An auditing security checklist

Access an auditor learning path that's designed for individuals in auditing, compliance and legal roles who want to learn more about how their internal operations can demonstrate compliance using the AWS Cloud. </br>

## Denial-of-Service Attacks
Deliberate attempts to make a website or application unavailable to users. </br>
For example, an attacker might flood a website or application with excessive network traffic until the targeted website or application becomes overloaded and is no longer able to respond. </br>
If the website or application becomes unavailable, this ***denies service*** to users who are trying to make legitimate requests. </br>

### Distributed denial-of-service attacks
A larger scale version of the above, where multiple sources are used to start an attack that aims to make a website or application unavailable. </br>
This can come from a group of attackers or even a single attacker, who can use multiple infected computers, also known as "bots", to send excessive traffic to a website or application. </br>

Types of DDoS attacks

- UDP flood
    - Low-level and brute-force
    - Sending requests to helpful parts of the internet, like the Nation Weather Service, which will send data to the fake return address
    - Solution: ***security groups*** for the entire AWS network that only allow proper request traffic
- Slowloris
    - Pretending to have a terribly slow connection to hog the server
    - Solution: ***Elastic Load Balancer*** that will handle the http traffic request first and waits until the entire message is complete before sending it to the frontend web server
- HTTP level
    - More sophisticated
    - Look like normal customers asking for normal things
    - Solution: ***AWS Shield with AWS WAF (Web Application Firewall)***

### AWS Shield
A service that protects applications against DDoS attacks. </br>
Provides two level of protection

- ***AWS Shield Standard***
    - Automatically protects all AWS customers at no cost, from the most common and frequently occurring types of DDoS attacks
    - As network traffic comes into applications, it uses a variety of analysis techniques to detect malicious traffic in real time and automatically mitigates it
- ***AWS Shield Advanced***
    - A paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks
    - Integrates with other services such as Amazon CloudFront, Amazon Route 53 and Elastic Load Balancing
    - Can be integrated with AWS WAF by writing custom rules to mitigate complex DDoS attacks

## Additional Security Services
Encryption can be used to ensure applications' data is secure, while in storage (***encryption at rest***) and while it's transmitted (***encryption in transit***). </br>

### AWS Key Management Service (AWS KMS)
A service that enables companies to perform encryption operations through the use of ***cryptographic keys***, which are random strings of digits used for locking (encrypting) and unlocking (decrypting) data. </br>
It can be used to create, manage and use cryptographic keys. The use of keys across a wide range of services and applications can also be controlled. </br>
Additionally, specific levels of access control can be chosen for the keys, specifying which IAM users and roles are able to manage keys. </br>
Keys can be temporarily disabled so that they're not in use by anyone. They'll never leave AWS KMS and companies are always in control of them. </br>

### AWS WAF
A web application firewall that lets companies monitor network requests that come into their web applications. </br>
It works together with Amazon CloudFront and an Application Load Balancer. </br>
it uses a web access control list (ACL) to protect companies' AWS resources. </br>
If an application has been receiving malicious network requests from several IP addresses, they can be blocked to prevent them from continuing to access the application. </br>

### Amazon Inspector
A tool that performs automated security assessments that helps improve the security and compliance of applications. </br>
It checks applications for security vulnerabilities and deviations from security best practices, such as open access to Amazon EC2 instances and installations of vulnerable software versions. </br>
After it has performed an assessment, it'll provide a list of security findings that prioritizes by severity level, including a detailed description of each security issue and a recommendation for how to fix it. </br>
However, AWS doesn't guarantee that following the provided recommendations resolves every potential security issue. Under the shared responsibility model, customers are responsible for the security of their applications, processes and tools that run on AWS services. </br>

### Amazon GuardDuty
A service that provides intelligent threat detection for companies' AWS infrastructure and resources. It identifies threats by continuously monitoring the network activity and account behavior within companies' AWS environments. </br>
Once it's enabled, it'll continuously analyze data from multiple AWS sources, including VPC Flow Logs and DNS logs. </br>
The detailed findings of any threats that it detects can be reviewed from the AWS Management Console. These include recommended steps for remediation. </br>
AWS Lambda functions can be configured to take remedian steps automatically in response to GuardDuty's security findings. </br>

# Additional Resources
- [Security, Identity, and Compliance on AWS](https://aws.amazon.com/products/security)
- [Whitepaper: Introduction to AWS Security](https://docs.aws.amazon.com/whitepapers/latest/introduction-aws-security/welcome.html)
- [Whitepaper: Amazon Web Services - Overview of Security Processes](https://docs.aws.amazon.com/whitepapers/latest/aws-overview-security-processes/aws-overview-security-processes.pdf)
- [AWS Security Blog](https://aws.amazon.com/blogs/security/)
- [AWS Compliance](https://aws.amazon.com/compliance)
- [AWS Customer Stories: Security, Identity, and Compliance](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23security-identity-compliance)
- [Security best practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
