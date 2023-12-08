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


