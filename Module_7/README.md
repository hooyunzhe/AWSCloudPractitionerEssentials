# Monitoring and Analytics
Naturally, companies want to know how their businesses are doing, including how well the systems and processes are running. </br>
Monitoring is the idea of observing systems, collecting metrics, evaluating those metrics over time and then using them to make decisions or take actions. </br>

## Amazon CloudWatch
A web service that enables companies to monitor and manage various metrics and configure alarm actions based on data from those metrics. </br>
It uses metrics to represent data points for the resources. AWS services send metrics to CloudWatch, which then uses them to create graphs automatically that show how performance has changed over time. </br>

### CloudWatch alarms
Alarms that automatically perform actions if the value of the specified metric has gone above or below a predefined threshold. </br>
For example, if a company's developers forget to stop the Amazon EC2 instances that are used for application development or testing purposes, they'll continue to run and incur charges. </br>
In this scenario, a CloudWatch alarm can be created to automatically stop an instance when the CPU utilization percentage has remained below a certain threshold for a specified period. Notifications can also be specified when configuring the alarm. </br>

### CloudWatch dashboard
A dashboard feature that enables companies to access all the metrics for their resources from a single location. </br>
Separate dashboards can be customized for different business purposes, applications or resources. </br>

In conclusion, here are the benefits of using Amazon CloudWatch

- Access all metrics from a central location
- Gain visibility into applications, infrastructure and services
- Reduce ***mean time to resolution (MTTR)***
- Improve ***total cost of ownership (TCO)***
- Drive insights to optimize applications and operational resources

## AWS CloudTrail
Being able to audit transactions in IT is a critical element in most compliance structures. </br>
This is where ***AWS CloudTrail***, a comprehensive API auditing tool comes in. </br>
Every single API call to AWS is recorded, including the identity of the API caller, the time of the API call, the source IP address of the API caller and more. It can be thought of as a _trail_ of breadcrumbs (or a log of actions) that someone has left behind them. </br>
With this tool, companies can view a complete history of user activity and API calls for their applications and resources. </br>
Events are typically updated within 15 minutes after an API call, they can also be filtered by specifying the time and date that an API call occurred, the user who requested the action, the type of resource that was involved and more. </br>

### CloudTrail Insights
An optional feature that allows CloudTrail to automatically detect unusual API activities. </br>
For example, it might detect that a higher number of Amazon EC2 instances than usual have recently launched. Companies can then review the full event details to determine which actions to take next. </br>

## AWS Trusted Advisor
When running businesses, it might be a good idea to have advisers who can come in from the outside and give recommendations. </br>
***AWS Trusted Advisor** is a web service that inspects a company's AWS environment and provides real-time recommendations in accordance with AWS best practices in the following five categories

- Cost optimization
- Performance
- Security
- Fault tolerance
- Service limits

For each category, it offers a list of recommended actions and additional resources to learn more about AWS best practices. </br>
The guidance provided can benefit companies at all stages of deployment, from creating new workflows and developing new applications, to making ongoing improvements to existing applications and resources. </br>

### AWS Trusted Advisor dashboard
On the AWS Management Console, completed checks for all five categories can be reviewed. </br>
For each category

- The green check indicates the number of items for which it detected **no problems**
- The orange triangle represents the number of recommended **investigations**
- The red circle represents the number of recommended **actions**

# Additional Resources
- [Management and Governance on AWS](https://aws.amazon.com/products/management-tools)
- [Monitoring and Observability](https://aws.amazon.com/products/management-tools/use-cases/monitoring-and-observability/)
- [Configuration, Compliance, and Auditing](https://aws.amazon.com/products/management-tools/use-cases/configuration-compliance-and-auditing/)
- [AWS Management & Governance Blog](https://aws.amazon.com/blogs/mt/)
- [Whitepaper: AWS Governance at Scale](https://docs.aws.amazon.com/whitepapers/latest/aws-governance-at-scale/introduction.html)
