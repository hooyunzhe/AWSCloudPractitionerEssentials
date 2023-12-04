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
This concept is called ***Content Delivery Networks***