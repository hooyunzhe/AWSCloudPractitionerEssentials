# Storage and Databases
When companies run their businesses, there will be data that needs to be stored. </br>
This is where databases comes in, but not just any database, companies need to make sure they choose the right database for the task and the right storage for data types. </br>

## Instance Stores and Amazon Elastic Block Store (Amazon EBS)
When using Amazon EC2 instances to run applications, they need access to CPU, memory, network and storage. All of these different components are provided by EC2 instances. </br>
As applications run, they often need block-level storage that stores files, which are series of bytes in blocks on disc. </br>
When a file is updated, only the pieces that change are updated. This makes it an efficient storage type when working with applications like databases, enterprise software or file systems </br>

### Instance stores
Temporary block-level disk storage for Amazon EC2 instances that's physically attached to the host computer. </br>
As instances are virtual servers, when they start from a stopped state, the host might be different. Meaning that instances stores have the same lifespan as the instances and all data will be lost when they are terminated. </br>

### Amazon Elastic Block Store (Amazon EBS)
A service that provides block-level storage volumes for Amazon EC2 instances, where all data remains available when they're stopped or terminated. </br>
When creating EBS volumes, configuration such as volume size and type must first be defined. After they're created, they can be attached to Amazon EC2 instances. </br>
Because data in EBS volumes needs to persist, it's important to back up the data. </br>

### Amazon EBS snapshots
Incremental backups for Amazon EBS volumes where the first one copies all the data and subsequent ones only save the blocks of data that have changed since the most recent snapshot. </br>
This is different from full backups, in which all the data in a storage volume is copied every time, including data that hasn't changed since the most recent backup. </br>

## Amazon Simple Storage Service (Amazon S3)
A storage service that allows companies to store and retrieve a virtually unlimited amount of data at any scale. </br>
Data is stored as objects, which are stored in buckets. The maximum object size is 5TB. </br>
Permissions can be set to control visibility and access to objects, there's also a versioning feature to track changes to objects over time. </br>

### Object storage
Each object consists of data, metadata and a key. </br>
The data can be an image, video, text document or any other type of file. Metadata contains information about the data, how it's used, the object size and more. Lastly, the key is the object's unique identifier. </br>
Unlike block storage, when a file in object storage is modified, the entire object is updated. </br>

### Amazon S3 storage classes
As usual, with Amazon S3, it has a pay-for-what-you-use model. </br>
There's a range of storage classes for different business and cost needs. Here are the two factors to consider when selecting a class

- How often the data will be retrieved
- How available the data needs to be

There are a total of eight classes

- ***S3 Standard***
    - Designed for frequently accessed data
    - Stores data in a minimum of three Availability Zones
    - Provides high availability for objects
    - Suitable for wide range of use cases such as
        - Websites
        - Content distribution
        - Data analytics
    - Has a higher cost than other classes intended for infrequently accessed data and archival storage
- ***S3 Standard-Infrequent Access (S3 Standard-IA)***
    - Ideal for infrequently accessed data
    - Similar to S3 Standard but with lower storage price and higher retrieval price
    - Suitable for infrequently accessed data that requires high availability when needed
- ***S3 One Zone-Infrequent Access (S3 One Zone-IA)***
    - Stores data in a single Availability Zone
    - Has a lower storage price than S3 Standard-IA
    - Good when cost savings on storage are desired
    - Suitable for data that can be easily reproduced in the event of an Availability Zone failure
- ***S3 Intelligent-Tiering***
    - Ideal for data with unknown or changing access patterns
    - Requires a small monthly monitoring and automation fee per object
    - When an object hasn't been accessed for 30 consecutive days, it'll be moved to the infrequent access tier, S3 Standard-IA.
    - When an object in the infrequent access tier is accessed, it'll be moved to the frequent access tier, S3 Standard.
    - Suitable for data with access patterns that frequently change
- ***S3 Glacier Instant Retrieval***
    - Works well for archived data that requires immediate access
    - Can retrieve objects within a few milliseconds
    - Suitable for archival data with a need for the same retrieval performance as S3 Standard
- ***S3 Glacier Flexible Retrieval***
    - Low-cost storage designed for data archiving
    - Able to retrieve objects within 1 minute or up to 12 hours
    - Suitable for archival data with a flexible retrieval requirement
- ***S3 Glacier Deep Archive***
    - Lowest-cost object storage class ideal for archiving
    - Able to retrieve objects within 12 to 48 hours
    - Supports long-term retention and digital preservation
    - Objects are replicated and stored across at least three geographically dispersed Availability Zones
    - Suitable for archival data that's accessed once or twice in a year
- ***S3 Outposts***
    - Creates S3 buckets on Amazon S3 Outposts
    - Makes it easier to retrieve, store and access data on AWS Outposts
    - Designed to store data durably and redundantly across multiple devices and servers on Outposts
    - Suitable for workloads with local data residency requirements that must satisfy demanding performance needs by keeping data close to on-premises applications

### Comparing Amazon EBS and Amazon S3
- ***Amazon Elastic Block Store***
    - Sizes up to 16 TiB each
    - Survive termination of their EC2 instance
    - Solid state by default
    - HDD options
- ***Amazon Simple Storage Service***
    - Unlimited storage
    - Individual objects up to 5 TBs
    - Write once/read many
    - 99.999999999% durability

Example use case: ***website where users upload photos of themselves to find animals that look like them*** </br>
Ideal service: ***Amazon S3*** </br>
Reasons:
- Already web enabled, with every object having a URL where access rights can be controlled
- Regionally distributed meaning no backup strategies are needed
- Substantial cost savings compared to the same storage load on EBS
- Serverless meaning no EC2 instances are needed

Example use case: ***80GB video file that's being edited*** </br>
Ideal service: ***Amazon EBS*** </br>
Reasons:
- Block storage breaks the file down to small components
- When one scene is edited and the change is saved, only the blocks that contain those bits will be updated by the engine
- Saves time and compute capacity

Conclusion: ***Use S3 when using complete objects or there are only occasional changes, use EBS when doing complex read, write or change functions***

## Amazon Elastic File System (Amazon EFS)
A scalable file system for AWS Cloud services and on-premises resources. As files are added or removed, Amazon EFS grows or shrinks automatically. It can scale on demand to petabytes without disrupting applications. </br>

### File storage
An approach where multiple clients, such as users, applications, servers and more, can access data that is stored in shared file folders. </br>
File storage servers use block storage with a local file system to organize files. </br>

### Comparing Amazon EBS and Amazon EFS
- ***Amazon EBS***
    - Stores data in a ***single Availability Zone***
    - Amazon EC2 instances must reside within the same AZ to be attached to EBS volumes
- ***Amazon EFS***
    - Stores data in ***multiple Availability Zones***
    - Duplicate storage enables concurrent access of data from all the AZs in the Region where a file system is located
    - On-premises servers can access Amazon EFS using AWD Direct Connect

## Amazon Relational Database Service (Amazon RDS)
Often times, data relates to each other. These relationships need to be stored somewhere. </br>
This is where ***relational database management system (RDBMS)*** comes in. </br>

### Relational databases
A type of database where ***structured query language (SQL)*** is used to store and query data. This allows data to be stored in an easily understandable, consistent and scalable way. </br>
Example data:

| ID | Product name               | Size   | Price |
| -- | -------------------------- | ------ | ----- |
| 1  | Medium roast ground coffee | 12 oz. | $5.30 |
| 2  | Dark roast ground coffee   | 20 oz. | $9.27 |

### Amazon Relational Database Service
A managed service that enables companies to run relational databases in the AWS cloud. </br>
It automates tasks such as hardware provisioning, database setup, patching and backups, which reduces time spent on administration. </br>
Other services can be integrated to fulfill business and operational needs, such as using AWS Lambda to query databases from serverless applications </br>
Many Amazon RDS database engines offer encryption at rest (protecting data while it's stored) and encryption in transit (protecting data while it's being sent and received). </br>

### Amazon RDS database engines
Amazon RDS is available on six database engines that optimize for memory, performance or input/output (I/O)

- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

### Amazon Aurora
An enterprise-class relational database that's compatible with MySQL and PostgreSQL. It's up to five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases. </br>
It helps reduce database costs by reducing unnecessary input/output operations while ensuring that the resources remain reliable and available. </br>
Good for workloads that require high availability, as it replicates six copies of data across three AZs and continuously backs up the data to Amazon S3. </br>

## Amazon DynamoDB
Relational databases work great for many use cases and have been the standard type of database historically, but they can have performance and scaling issues when under stress. </br>
Their rigid schema means they cannot have any variation in the types of data that's stored in a table, making them not ideal for less rigid datasets that are accessed at a very high rate. </br>
This is where ***non-relational databases***, or ***NoSQL***, databases comes in. </br>

### Nonrelational databases
A type of database where tables are used to store data. </br>
Nonrelational databases are often referred to as "NoSQL databases" because they use structures other than rows and columns to organize data. </br>
One common type of structural approach is ***key-value pairs***, where keys are items and values are attributes, which can be added or removed at any time. </br>
Additionally, not every item has to have the same attributes. </br>

Example data:

| Key | Value                        |
| --- | ---------------------------- |
| 1   | Name: John Doe               |
|     | Address: 123 Any Street      |
|     | Favorite drink: Medium latte |
| 2   | Name: Mary Major             |
|     | Address: 100 Main Street     |
|     | Birthday: July 5, 1994       |

### Amazon DynamoDB
A managed key-value database service that delivers single-digit millisecond performance at any scale. </br>
It's serverless meaning that there's no need to provision, patch or manage servers and install, maintain or operate software. </br>
As the size of databases shrink or grow, it automatically scales to adjust for changes in capacity while maintaining consistent performance. This makes it suitable for use cases that requires high performance while scaling. </br>

### Comparing Amazon RDS and Amazon DynamoDB
- ***Amazon RDS***
    - Automatic high availability with recovery provided
    - Customer ownership of data
    - Customer ownership of schema
    - Customer control of network
- ***Amazon DynamoDB***
    - Key-value structure requiring no advanced schema
    - Massive throughput capabilities
    - PB size potential
    - Granular API access

Example use case: ***sales supply chain management system where weak spots have to be analyzed*** </br>
Ideal service: ***Amazon RDS*** </br>
Reasons:
- Relational databases have been around since the moment businesses started using computers
- Built for business analytics
- Able to perform complex analysis of data spread across multiple tables with relational joins and more

Example use case: ***employee contact list with names, phone numbers, emails and employee IDs*** </br>
Ideal service: ***Amazon DynamoDB*** </br>
Reasons:
- Most use cases have nothing to do with complex relationships and are essentially look-up tables
- Eliminates the overhead of unnecessary relational functionalities
- Able to build powerful and incredibly fast databases

## Amazon Redshift
So far, the types of databases mentioned are suitable for workloads that require fast, reliable and current data. They can handle thousands of transactions per second, are highly available and massively durable. </br>
But there are times where business needs focus on what already happened, this kind of data analysis require databases that are in a whole different realm. </br>
Most relational databases tend to function fabulously at certain capacities in order to handle the velocity of real time read/write functionality. With modern telemetry and the explosion of IoT, the volume of data will overwhelm even the beefiest traditional relational database. This is where data warehouses and data lakes come in. </br>

Amazon Redshift is a data warehousing service for big data analytics, it offers the ability to collect data from many sources and helps companies understand relationships and trends across their data. </br>

## AWS Database Migration Service
When companies want to use the various database services on AWS and already have databases either on-premises or in the cloud, they need a way to migrate them. </br>

***AWS Database Migration Service (AWS DMS)*** is a service that enables companies to migrate their relational or nonrelational databases and other types of data stores. Data is moved between a source database and a target database, which can be of the same type or different types. </br>
The former is called ***homogeneous migrations***, they are straightfoward since schema structures, data types and database code is compatible between source and target. </br>
The latter is called ***heterogeneous migrations***, they need to go through a two-step process where their schema and code are first converted using the AWS Schema Conversion Tool, then their data migrated from the source to the target. </br>
During the migration, the source database remains operational, reducing downtime for any applications that rely on it. </br>

### Other use cases for AWS DMS
- ***Development and test database migrations*** enable developers to test applications against production data without affecting production users
- ***Database consolidation*** where several databases are combined into a single database
- ***Continuous replication*** where ongoing copies of data are sent to other target sources instead of a one-time migration

## Additional Database Services
Despite what database vendor might say, there is no one-size-fits-all database for all purposes. </br>
Other than the above mentioned database flavors, AWS offers even more databases for special business requirements </br>

- ***Amazon DocumentDB***
    - A document database service that supports MongoDB workloads
    - Suitable for content management, catalogs and user profiles
- ***Amazon Neptune***
    - A graph database service ideal for highly connected datasets
    - Suitable for social networking, recommendation engines, fraud detection and knowledge graphs
- ***Amazon Quantum Ledger Database (Amazon QLDB)***
    - A ledger database service
    - Suitable for banking for financial records that require 100% immutability
- ***Amazon Managed Blockchain***
    - A service where blockchain networks can be created and managed with open-source frameworks
    - Suitable for data that requires storage in a distributed ledger system without a central authority
- ***Amazon ElastiCache***
    - A service that adds caching layers on top of databases to help improve the read times of common requests from milliseconds to microseconds, it supports Redis and Memcached
    - Suitable for relational data that needs to be accessed often and at high speeds
- ***Amazon DynamoDB Accelerator (DAX)***
    - A native in-memory caching layer for DynamoDB that helps improve response times from single-digit milliseconds to microseconds
    - Suitable for nonrelational data that needs to be accessed often and at high speeds

# Additional Resources
- [Cloud Storage on AWS](https://aws.amazon.com/products/storage)
- [AWS Storage Blog](https://aws.amazon.com/blogs/storage/)
- [Hands-On Tutorials: Storage](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23storage&awsf.getting-started-content-type=content-type%23hands-on)
- [AWS Customer Stories: Storage](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23storage)
- [AWS Database Migration Service](https://aws.amazon.com/dms/)
- [Databases on AWS](https://aws.amazon.com/products/databases)
- [Category Deep Dive: Databases](https://aws.amazon.com/getting-started/deep-dive-databases/)
- [AWS Database Blog](https://aws.amazon.com/blogs/database/)
- [AWS Customer Stories: Databases](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23databases)
