# Pricing and Support
Business owners have a lot of responsibilities and one of them is managing costs.
AWS provides a lot of free tools to help companies plan and analyze the budgets for their AWS environments. </br>

## AWS Free Tier
Enables users to begin using certain services without having to worry about incurring costs for the specified period. </br>
Three types of offers are available

- ***Always Free***
    - Do not expire
    - Available to all AWS customers
    - Examples
        - ***AWS Lambda*** allows 1 million free requests and up to 3.2 million seconds of compute time per month
        - Amazon DynamoDB allows 25 GB of free storage per month
- ***12 Months Free***
    - Free for 12 months following the initial sign-up date to AWS
    - Examples
        - Specific amounts of ***Amazon S3 Standard Storage***
        - Thresholds for monthly hours of ***Amazon EC2*** compute time
        - Amounts of ***Amazon CloudFront*** data trasfer out
- ***Trials***
    - Short-term offers that start from the date of activation of a particular service
    - Length varies by number of days or the amount of usage in the service
    - Examples
        - ***Amazon Inspector*** offers a 90-day free trial
        - ***Amazon Lightsail*** (a service that enables companies to run virtual private servers) offers 750 free hours of usage over a 30-day period

## AWS Pricing Concepts
AWS offers a range of cloud computing services with pay-as-you-go pricing. </br>

### How AWS pricing works
There are three categories of pricing

- ***Pay for what you use***
    - Pay for exactly the amount of resources that are actually used
    - No long-term contracts or complex licensing
- ***Pay less when you reserve***
    - Some services offer reservation options that provide a significant discount compared to On-Demand Instance pricing
    - Example: Amazon EC2 Instance Savings Plan that provides savings of up to 72% over the equivalent On-Demand Instance capacity
- ***Pay less with volume-based discounts when you use more***
    - Some services offer tiered pricing where the per-unit cost is incrementally lower with increased usage
    - Example: the more Amazon S3 storage companies use, the less they pay for it per GB

### AWS Pricing Calculator
A tool that lets users explore AWS services and create an estimate for the cost of their use cases on AWS. </br>
Estimates can be organized by groups, which can reflect how their company is organized. They can be saved and shared with their generated links. </br>
For example, by using this tool, companies can review an estimated comparison of different Amazon EC2 instance types across AWS Regions. </br>

### AWS Pricing Examples
***AWS Lambda***
- Charges based on the number of requests for the functions and the time that it takes for them to run
- Allows 1 million free requests and up to 3.2 million seconds of compute time per month
- Compute Savings Plan offers lower compute costs in exchange for committing to a consistent amount of usage over a 1-year or 3-year term.

***Amazon EC2***
- Charges based on the compute time that are used while the instances are running
- For some workloads like batch processing jobs that are able to withstand interruptions, Spot Instances would provide up to 90% cost savings while still meeting the availability requirements

***Amazon S3***
- There are the four cost components
- **Storage** - Charges based on the objects' sizes, storage classes and how long each object is stored during this month
- **Requests and data retrievals** - Charges based on the number of requests made to the objects and buckets
- **Data transfer** - No cost to transfer data between different buckets or from Amazon S3 to other services within the same AWS Region, however, data that's transferred into and out of Amazon S3 is charged, with the following exceptions
    - Data transferred into Amazon S3 from the internet or out to Amazon CloudFront
    - Data transferred out to an Amazon EC2 instance in the same AWS Region as the Amazon S3 bucket
- **Management and replication** - Charges based on the storage management features that are enabled on the buckets, these include Amazon S3 inventory, analytics and object tagging

## Billing Dashboard
The ***AWS Billing & Cost Management dashboard*** is where companies can pay their AWS bill, monitor their usage, analyze and control their costs. </br>
Here are some examples

- Compare current month-to-date balance with the previous month and get a forecast of the next month based on current usage
- View month-to-date spend by service
- View Free Tier usage by service
- Access Cost Explorer and create budgets
- Purchase and manage Savings Plans
- Publish AWS Cost and Usage Reports

## Consolidated Billing
AWS Organizations, a service that enables companies to manage multiple AWS accounts from a central location, also provides the option for **consolidated billing**. </br>
This enables companies to receive a single bill for all AWS accounts in the organization, where the combined costs of all linked accounts can be easily tracked. The default maximum number of accounts allowed for an organization is 4, but can be increased by contacting AWS Support. </br>
On the monthly bill, itemized charges incurred by each account can be reviewed, enabling companies to have greater transparency into the organization's accounts. </br>

Another benefit is the ability to share bulk discount pricing, Savings Plans and Reserved Instances across the accounts in the organization. </br>
For example, one account might not have enough monthly usage to qualify for discount pricing. However, when multiple accounts are combined, their aggregated usage may result in a benefit that applies across all accounts in the organization. </br>

## AWS Budgets
As companies ramp up their AWS deployments, they often want to make sure they're not spending an unbudgeted amount. </br>
This can be accomplished by using ***AWS Budgets***, where budgets can be created to plan service usage, service costs and instance reservations. </br>
The information in AWS Budgets updates three times a day, helping companies accurately determine how close their usage is to the budgeted amounts or to the AWS Free Tier limits. </br>
Custom alerts can also be set for when the usage exceeds, or is forecasted to exceed, the budgeted amount. </br>

## AWS Cost Explorer
AWS has a variable cost model meaning that there won't be one fixed billed amount at the end of every month, as it fluctuates with the resources used and how they're used. This makes it important for companies to drill down into their bill and see how they're spending money. </br>
***AWS Cost Explorer*** is a tool that lets companies visualize, understand and manage their AWS costs and usage over time. </br>
It comes with a default report of the costs and usage for the top five cost-accruing AWS services. Custom filters and groups and be applied to analyze the data. </br>
By analyzing the AWS costs over time, companies can make informed decisions about future costs and how to plan their budgets. </br>

## AWS Support Plans
AWS offers four different Support plans to help companies troubleshoot issues, lower costs and efficiently use AWS services. </br>

### Basic Support
Free for all AWS customers and includes access to whitepapers, documentation and support communities. Companies can also contact AWS for billing questions and service limit increases. </br>
This level of support gives access to a limited selection of AWS Trusted Advisor checks. Additionally, ***AWS Personal Health Dashboard*** provides alerts and remediation guidance when AWS is experiencing events that may affect companies. </br>

### Developer, Business, Enterprise On-Ramp, and Enterprise Support
These Support plans include all the benefits of Basic Support, in addition to the ability to open an unrestricted number of technical support cases. They all have pay-by-the-month pricing and require no long-term contracts. </br>
- ***Developer Support***
    - Access to features such as
        - Best practice guidance
        - Client-side diagnostic tools
        - Building-block architecture support which consists of guidance for how to use AWS offerings, features and services together
    - Suitable for companies that are exploring AWS services and are unsure of how to potentially use them together to build applications that can address their needs
- ***Business Support***
    - Access to features such as
        - Use-case guidance to identify AWS offerings, features and services that can best support specific needs
        - All AWS Trusted Advisor checks
        - Limited support for third-party software such as common operating systems and application stack components
    - Suitable for companies that are starting to use a few AWS services
- ***Enterprise On-Ramp Support***
    - Access to features such as
        - A pool of ***Technical Account Managers*** to provide proactive guidance and coordinate access to programs and AWS experts
        - A Cost Optimization workshop (one per year)
        - A Concierge support team for billing and account assistance
        - Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard
    - Access to a specific set of proactive support services provided by a pool of Technical Account Managers
        - Consultative review and architecture guidance (one per year)
        - Infrastructure Event Management support (one per year)
        - Support automation workflows
        - 30 minutes of less response time for business-critical issues
    - Suitable for companies that are migrating production and business-critical workloads to AWS
- ***Enterprise Support***
    - Access to features such as
        - A designated Technical Account Manager to provide proactive guidance and coordinate access to programs and AWS experts
        - A Concierge support team for billing and account assistance
        - Operations Reviews and tools to monitor health
        - Training and Game Days to drive innovation
        - Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard
    - Access to a specific set of proactive support services provided by a designated Technical Account Manager
        - Consultative review and architecture guidance
        - Infrastructure Event Management support
        - Cost Optimization Workshop and tools
        - Support automation workflows
        - 15 minutes or less response time for business-critical issues

### Technical Account Manager (TAM)
The TAM is companies' primary point of contact at AWS, who'll educate, empower and evolve their cloud journey across the full range of AWS services. </br>
They provide expert engineering guidance, help design solutions that efficiently integrate AWS services, assist with cost-effective and resilient architectures and provide direct access to AWS programs and a broad community of experts. </br>
For example, if a company is interested in developing an application that uses several AWS services together, its TAM could provide insights into how to best use the services together. They achieve while aligning with the specific needs that the company is hoping to address through the new application. </br>

## AWS Marketplace
A digital catalog that includes thousands of software listings from independent software vendors. Companies to use it to find, test and buy software that runs on AWS. </br>
For each listing in AWS Marketplace, detailed information can be accessed, these include pricing options, available support and reviews from other AWS customers. </br>
Companies can also explore software solutions by industry and use case. For example, a company in the healthcare industry could review use cases that implement solutions to protect patient records or use machine learning models to analyze a patient's medical history and predict possible health risks. </br>

AWS Marketplace offers products in several categories

- Infrastructure Software
- DevOps
- Data Products
- Professional Services
- Business Applications
- Machine Learning
- Industries
- Internet of Things (IoT)

Within each category, there are subcategories to help narrow the search. For example, subcategories in DevOps include areas such as Application Development, Monitoring and Testing. </br>

# Additional Resources
- [AWS Pricing](https://aws.amazon.com/pricing)
- [AWS Free Tier](https://aws.amazon.com/free)
- [AWS Cost Management](https://aws.amazon.com/aws-cost-management/)
- [Whitepaper: How AWS Pricing Works](https://d1.awsstatic.com/whitepapers/aws_pricing_overview.pdf)
- [Whitepaper: Introduction to AWS Economics](https://d1.awsstatic.com/whitepapers/introduction-to-aws-cloud-economics-final.pdf)
- [AWS Support](https://aws.amazon.com/premiumsupport)
- [AWS Knowledge Center](https://aws.amazon.com/premiumsupport/knowledge-center/)
