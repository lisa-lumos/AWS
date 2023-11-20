# AWS Storage Services
Not all AWS region supports all AWS services. There is also a secret region, which users do not know where it is, which is specifically for US government intelligence organizations, such as the CIA. 

Each region is divided up into at lease 2 availability zones, that are physically isolated from each other. 

Local zones are located close to large cities and their centers, and provides the lowest latency within that specific area. Local zones operate as an extension of an AWS region, and also have multiple availability zones for high availability. 

## Simple Storage Service (S3)
- serverless service
- upload objects to buckets, the size of bucket is theoretically unlimited. 

## Glacier
- serverless service
- cheapest storage option on AWS
- long term archive
- can set up a lifecycle rule to automatically migrate old data in S3 to glacier

## Elastic Block Store (EBS)
- highly available, low latency 
- for attaching to servers that are launched with the EC2

## Elastic File System (EFS)
- network attached storage
- allows multiple servers to access the one data source

## Storage Gateway
- enables hybrid storage between on-prem envs and the AWS cloud
- low latency, by caching frequently used data on-prem (for fast access), while less frequently used data on the cloud (for disaster recovery). 

## Snowball
- portable PB-scale device to migrate large amount of data from on-prem to cloud

## Examples
We have 2 EC2 instances inside a VPC. If we we want more storage for each of them, we can attach a EBS to each of the EC2 instances. But if we want the two EC2 instances to share the same storage, then we could attach a EFS Mount Target to each of the EC2 and attach an EFS to it. If we only want object storage, we can allow S3 to reach inside the VPC via VPC Endpoint, then access S3 from the EC2 instances, and can also set up lifecycle rule to move old objects to Glacier to save cost. 

Hybrid storage example: have onsite storage in a corporate data center, and also want to have data stored in S3, for disaster recovery. The corporate data center may have Pbs of data, so could use a snowball device, load data and send to AWS. And AWS will upload that data to S3. Use the AWS Storage Gateway to sync on-prem data with S3, through the AWS Direct Connect service (high speed link). 

## RDS
MySQL, Aurora, PostgreSQL, MS SQL Server, Oracle. 

## DynamoDB
Serverless. High speed, low latency. 

## Redshift
data warehouse, big data storage

## ElastiCache
In-memory data store

## Database Migration Service (DMS)
migrate databases, can across db types. 

## Neptune
Graph db, fully managed. Store relationships. 

## Examples
RDS can combine with a ElastiCache node to improve efficient and reduce cost, for high traffic requesting same data from server. Data lives in ElastiCache for a certain period. Deletion and writing of data are synced from RDS from ElastiCache. 

## Create a MySQL db with RDS
First, create a security group, so it can be attached to mySQL instance to allow remote connection to it. In the console, search for vpc, go to Security Groups under Security section on the left pane. Create security group -> Security group name: rds-intro-lab, Description: Inbound access from internet for MySQL RDS, VPC: (default) -> Under Inbound rules pane, Add rule -> Type: MySQL/Aurora, Source: Anywhere-IPv4, Add rule -> Source: Anywhere-IPv6. We do not need to define an outbound rule because security groups are stateful, so any inbound requests that comes in are allowed to get out automatically. -> Create security group. 

Next, create a mysql instance. In the console, search rds. Create database -> Standard create; MySQL; Templates: Free tier; DB instance identifier: intro-aws-db; Add Master username and Master password; DB instance class: dt.t2.micro; use default storage; uncheck Enable storage autoscaling; VPC: (default); Subnet group: (default); Public access: Yes; VPC security group: (add rds-intro-lab); Database authentication: Password authentication; Initial database name: test; uncheck Enable automated backups -> Create database. 

After a few minutes, the database status shows it is Available. Click on this db. The Endpoint is what we use to connect to this instance remotely (for the Hostname field when creating a new connection). Install MySQL workbench on the local computer, create a new connection, and see the db.  

To delete this db in the console, select it, then Actions -> Delete. To delete this security group (has to happen after db deletion is successful), navigate to it, Actions -> Delete security groups -> Delete. 
