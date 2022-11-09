# 2. High-Performing Architectures

Q1: What determines the amount of resources available to an EC2 instance? Instance Type? AMI Image? Capacity reservation? Tenancy? 
A: Instance Type. 
Notes: Capacity reservation is for reserved instances. Tenancy: share resources with other people. 

Q2: A company has decided to host a MongoDB database on an Amazon EC2 instance. A large number of reads and writes are expected on the database. Which one of the following Amazon Elastic Block Store (Amazon EBS) storage types would be ideal to implement for the database? Amazon EBS Provisioned IOPS SSD? Amazon EBS Throughput Optimized HDD? Amazon EBS General Purpose SSD? Amazon EBS Cold HDD?
A: Amazon EBS Provisioned IOPS SSD
Notes: HDD is old type and has a lot of physical latency. SSD is better for IO. 

Q3: What are the basic building blocks fo Amazon Relational Database Service (Amazon RDS)? DB instances? EC2 Instances? Containers? EBS Volumes? 
A: DB instances.
Notes: Under the covers, it is EC2, but you cannot ssh into a database instance, they are fully managed. When you select DB instance class, the choices start with db.XXX, not mXX.XXX like in EC2. 

Q4: An application requires a relational database with an initial storage capacity of 4TB. The database will grow by 10GB per day. To support traffic, at least four read replicas are required to handle reads. Which option will meet these requirements? DynamoDB? Amazon S3? Amazon Aurora? Amazon Redshift?
A: Amazon Aurora
Notes: Capacity is not extraordinary, but not small. Need relational database,  Read replicas. Athena on S3 could allow you use sql to query, but it is not a database, and not for transactions. Aurora makes 2 replicas per availability zone.  

Q5: Which of the following are examples of making an infrastructure elastic? (Select THREE) 1. Creating an Auto Scaling group for your production instances that responds to capacity needs by scaling in or out? 2. Designing your dev environment so it can be turned off over the weekend? 3. Launching Read Replicas for your Amazon RDS database that has read-heavy workloads? 4. Determining your maximum capacity needs and provisioning production instances to constantly meet those needs? 5. Paying an annual fixed price for your IT resources? 
A: 1: yes. 2: it is manual/scheduled, but can turn off, so it is a kind of elasticity. 3. Yes. 4: constantly meet the maximum capacity is not elastic. 5. fixed = not changing. 

Q6: Which of the following are characteristics of Amazon EC2 Auto Scaling on AWS? (Select TWO) 1. Sends traffic to healthy instances? 2. Responds to changing conditions by adding or terminating Amazon EC2 instances? 3. Collects and tracks metrics and sets alarms? 4. Delivers push notifications? 5. Enforces a minimum number of running Amazon EC2 instances?
A: 2 and 5. 
Notes: 3 is Cloudwatch. 4 is Simple Notification Service












