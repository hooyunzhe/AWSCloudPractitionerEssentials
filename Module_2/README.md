# Compute in the Cloud
Amazon Elastic Compute Cloud (EC2) is highly flexible, cost effective and quick when compared to running servers on premises in a data center. <\br>
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
EC2 runs on top of physical host machines managed by AWS using virtualization technology. <\br>
A hypervisor is responsible for sharing the underlying physical resources between instances, also known as virtual machines. <\br>
It also makes sure that EC2 instances are secure and isolated from each other. <\br>

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
    - Hourly spend commitment
