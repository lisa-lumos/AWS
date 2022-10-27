# 1. Resilient Architectures

## Design a multi-tier architecture solution
- Determine a solution design based on access patterns
- Determine a scaling strategy for components used in a design
- Select an appropriate database based on requirements
- Select an appropriate compute and storage service based on requirements

We see this architecture often: Web Servers - App Servers - Database Servers. Having multi-tier because if one tier breaks down, the other tiers can serve the traffic. They are easy to separate in AWS by putting into different subnets. 

Q1: A database is running on an Amazon EC2 instance. The database software has a backup feature that requires block storage. What storage option would be the lowest cost option for the backup data? 
- Answer: Amazon EBS Cold HDD Volume (sc1). 
- Note: Amazon S3 is an object storage, not a block storage. Amazon EBS Throughput Optimized HDD Volume (st1) is more expensive than the answer. Block storage (EBS) is more like a hard drive volume, is flexible. Object storage (S3) contains ID, Data, and Metadata, it is more like a hard bound book, not flexible, need to remove an object to update an object. File storage (EFS, works on the NSFv4 protocol, not compatible with Windows which is FSX) is like a block storage, but multiple computers can access this storage at the same time, like a shared storage. For EC2 storage, refer `https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html`. Cold storage means infrequently accessed storage. 

Q2: Which set of database engines does Amazon Relational Database Service (Amazon RDS) currently support?
- Answer: Oracle, Microsoft SQL Server, MySQL, PostgreSQL, MariaDB, Amazon Aurora (RDBMS built for the cloud with full MySQL and PostgreSQL compatibility)
- Note: Cassandra, MongoDB are not relational databases. 

Q3: Your web service has a performance SLA to respond to 90% of requests in <5 seconds. Under normal and heavy operations, disbributing requests over four instances meets performance requirements. What architecture ensures cost efficient high availability of your service if an Availability Zone becomes unreachable? 
- Answer: Deploy the service on four servers with auto scaling across two availability zones. 
- Note: if one zone becomes unavailable, because it is an auto scaling group, it will quickly add two more servers, which will then meet the requirements on performance. 

Q4: You wish to deploy a microservices-based application without the operational overhead of managing infrastructure. This solution needs to accommodate rapid changes in the volume of requests. What do you do?
- Answer: Run the microservices in AWS Lambda behind an API Gateway
- Note: ... (needs further research)

Q5: Using Amazon Elastic Container Service (ECS) to run a containerized we application, you wish to minimize costs by running multiple copies of a task on each container instance. What do you do?
- Answer: Configure an Application Load Balancer to distribute the requests using path-based routing. 
- Note: ... (needs further research)



## Design highly available and/or fault-tolerant architectures
- Determine the amount of resources needed to provide a fault-tolerant architecture across Availability Zones
- Select a highly available configuration to mitigate single points of failure
- Apply AWS service to improve the reliability of legacy applications when application changes are not possible
- Select an appropriate disaster recovery strategy to meet business requirements
Identify key performance indicators to ensure the high availability of the solution


## Design decoupling mechanisms using AWS services
- Determine which AWS services can be leveraged to achieve loose coupling of components
- Determine when to leverage serverless technologies to enable decoupling


## Choose appropriate resilient storage
- Define a strategy to ensure the durability of data
- Identify how data service consistency will affect the operation of the application
- Select data services that will meet the access requirements of the application
- Identify storage services that can be used with hybrid or non-cloud-native applications





















