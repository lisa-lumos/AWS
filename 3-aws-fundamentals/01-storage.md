# AWS Storage Services

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

















