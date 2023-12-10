# Migration and Innovation
Companies may have existing deployments in on-premises environments or have started a cloud journey without AWS. </br>
AWS offers various options from migration tools, the AWS Cloud Adoption Framework and even the Snow Family, which are physical devices to migrate data in and out of AWS. </br>

## AWS Cloud Adoption Framework (AWS CAF)
Migrating to the cloud is a process, it takes a lot of effort to get applications migrated to AWS, and doing it successfully requires expertise. </br>
Different types of people in the company bring different perspectives to the table for migration, those perspectives should be harnessed to make sure everyone is on the same page. </br>
***AWS Cloud Adoption Framework*** helps companies manage this process through guidance and provides them advice to enable a quick and smooth migration to AWS. </br>

### Six core perspectives of the Cloud Adoption Framework
The AWS CAF organizes guidance into six areas of focus, called **Perspectives**. Each one addresses distinct responsibilities and helps the right people across the organization prepare for the changes ahead. </br>

- ***Business Perspective***
    - Ensure that IT aligns with business needs and that IT investments link to key business results
    - Use this to create a strong business case for cloud adoption and prioritize cloud adoption initiatives
    - Make sure business strategies and goals align with IT strategies and goals
    - Common roles
        - Business managers
        - Finance managers
        - Budget owners
        - Strategy stakeholders
- ***People Perspective***
    - Support development of an organization-wide change management strategy for successful cloud adoption
    - Use this to evaluate organizational structures and roles, new skill and process requirements and identify gaps, this helps prioritize training, staffing and organizational changes
    - Common roles
        - Human resources
        - Staffing
        - People managers
- ***Governance Perspective***
    - Focus on the skills and processes to align IT strategy with business strategy, which ensures that the business value is maximized and risks are minimized
    - Use this to understand how to update the staff skills and processes necessary to ensure business governance in the cloud
    - Manage and measure cloud investments to evaluate business outcomes
    - Common roles
        - Chief Information Officer (CIO)
        - Program managers
        - Enterprise architects
        - Business analysts
        - Portfolio managers
- ***Platform Perspective***
    - Include principles and patterns for implementing new solutions on the cloud and migrating on-premises workloads to the cloud
    - Use a variety of architectural models to understand and communicate the structure of IT systems and their relationships
    - Describe the architecture of the target state environment in detail
    - Common roles
        - Chief Technology Officer (CTO)
        - IT managers
        - Solutions architects
- ***Security Perspective***
    - Ensure that the organization meets security objectives for visibility, auditability, control and agility
    - Use the AWS CAF to structure the selection and implementation of security controls that meet the organization's needs
    - Common roles
        - Chief Information Security Officer (CISO)
        - IT security managers
        - IT security analysts
- ***Operations Perspective***
    - Enable, run, use, operate and recover IT workloads to the level agreed upon with business stakeholders
    - Use this to define how day-to-day, quarter-to-quarter and year-to-year business is conducted, as well as align with and support the operations of the business
    - The AWS CAF helps stakeholders define current operating procedures and identify the process changes and training needed to implement successful cloud adoption
    - Common roles
        - IT operations managers
        - IT support managers

## Migration Strategies
When it's time to migrate from on-premises deployment onto AWS, there are six possible options. These are called the ***six Rs***. </br>
The decision of the best fit should be based on time, cost, priority and criticality. </br>

### 6 strategies for migration
- ***Rehosting***
    - Move applications without changes
    - Also know as _list-and-shift_
    - Usually preferred by companies looking to implement its migration and scale quickly to meet a business case
- ***Replatforming***
    - Make a few cloud optimizations to realize a tangible benefit, without changing the core architecture of the application
    - Also known as _lift, tinker, and shift_
    - For large legacy migration that could use some optimization
- ***Refactoring***
    - Reimagine how an application is architected and developed by using cloud-native features
    - Also known as _re-architecting_
    - Driven by a strong business need to add features, scale or performance that would otherwise be difficult to achieve in the application's existing environment
- ***Repurchasing***
    - Move from a traditional license to a software-as-a-service model
    - Example: Migrating from a customer relationship management (CRM) system to Salesforce
- ***Retaining***
    - Keep applications that are critical for the business in the source environment
    - For applications that require major refactoring before they can be migrated or work that can be postponed until a later time
- ***Retiring***
    - Remove applications that are no longer needed
    - Usually have replacements live and functional

## AWS Snow Family
When companies need to get data to AWS, they would like to do it in an efficient and timely manner. The usual route is to copy the data over the internet, but this can take days, weeks or even months with the limitations of bandwidth. </br>
This is where ***AWS Snow Family*** comes in, it's a collection of physical devices that help physically transport up to exabytes of data into and out of AWS. </br>
These devices offer different capacity points and most include built-in computing capabilities. They're owned and managed by AWS and integrate with AWS security, monitoring, storage management and computing capabilities. </br>

- ***AWS Snowcone***
    - Small, rugged and secure edge computing and data transfer device
    - Features 2 CPUs, 4 GB of memory and up to 14 TB of usable storage
- ***AWS Snowball***
    - There are two types of devices
    - ***Snowball Edge Storage Optimized***
        - Suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs
        - Storage: 80 TB of HDD for block volumes and Amazon S3 compatible object storage, and 1 TB of SATA SSD for block volumes
        - Compute: 40 vCPUs and 80 GiB of memory to support Amazon EC2 sbe1 instances (equivalent to C5)
    - ***Snowball Edge Compute Optimized***
        - Provides powerful computing resources for use cases such as machine learning, full motion video analysis, data analytics and local computing stacks
        - Storage: 80 TB of HDD for Amazon S3 compatible object storage or Amazon EBS compatible block volumes, and 28 TB of NVMe SSD for block volumes
        - Compute: 104 vCPUs, 416 GiB of memory and an optional NVIDIA Tesla V100 GPU. Devices run Amazon EC2 sbe-c and sbe-g instances which are equivalent to C5, M5a, G3 and P3 instances
- ***AWS Snowmobile***
    - Exabyte-scale data transfer service for moving large amounts of data to AWS
    - Companies can transfer up to 100 petabytes of data per Snowmobile, a 45-foot long ruggedized shipping container pulled by a semi trailer truck

## Innovation with AWS
AWS offers many other services in various areas to enable innovation, here are some of them. </br>

- ***Machine Learning***
    - ***Amazon SageMaker*** for quickly building, training and deploying machine learning models at scale
    - ***Amazon Augmented AI (Amazon A2I)*** for a machine learning platform that any business can build upon without needing PhD level expertise in-house
- ***Artificial intelligence***
    - ***Amazon Transcribe*** for converting speech to text
    - ***Amazon Comprehend*** for discovering patterns in text
    - ***Amazon Textract*** for extracting text and data from documents
    - ***Amazon Fraud Detector*** for identifying potentially fraudulent online activities
    - ***Amazon Lex*** for building voice and text chatbots
    - ***AWS DeepRacer*** for experimenting with reinforcement learning while having fun in a racing environment
- ***Other***
    - ***VMware on AWS*** allows VMware based infrastructure that companies use on-premises to be lifted up and dropped onto AWS
    - ***AWS Ground Station*** provides satellites with the same pay-as-you-use pricing

### Innovate with AWS Services
When examining how to use AWS services, it's important to focus on the desired outcomes. </br>
In order to drive innovation in the cloud, the following conditions need to be clearly articulated

- The current state
- The desired state
- The problems that need to be solved

# Additional Resources
- [Migration & Transfer on AWS](https://aws.amazon.com/products/migration-and-transfer)
- [A Process for Mass Migrations to the Cloud](https://aws.amazon.com/blogs/enterprise-strategy/214-2/)
- [6 Strategies for Migrating Applications to the Cloud](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/)
- [AWS Cloud Adoption Framework](https://aws.amazon.com/professional-services/CAF/)
- [AWS Fundamentals: Core Concepts](https://aws.amazon.com/getting-started/fundamentals-core-concepts/)
- [AWS Cloud Enterprise Strategy Blog](https://aws.amazon.com/blogs/enterprise-strategy/)
- [Modernizing with AWS Blog](https://aws.amazon.com/blogs/modernizing-with-aws/)
- [AWS Customer Stories: Data Center Migration](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23datacenter-migration)
