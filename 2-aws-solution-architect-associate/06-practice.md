# Practice

Q1: easy, skipped. 

Q2: What determines the amount of resources available to an EC2 instance?
A: Instance Type

Q3: Which Amazon S3 encryption option does not require AWS to persistently store the encryption keys it uses to decrypt data?  
1. Client-side encryption
2. SSE (Service side encryption) - KMS
3. SSE-S3
4. SSE-C

A: 4

Notes: with client-side encryption, AWS doesn't store the key, but also it cannot decrypt it either. KMS is key encrypting key, S3 keeps key in the S3 service, SSE-C, C stands for customer managed. 

Q4: easy, skip. Dedicated host specifies hardware. 

Q5: An application consists of Amazon EC2 instances placed in different AZs. The EC2 instances sit behind an Application Load Balancer. The EC2 instances are managed via an Auto Scaling group. A network address translation (NAT) instance is used for the EC2s to download updates from the internet. Which option is a bottleneck in the architecture?
1. EC2 instances
2. Elastic Load Balancing
3. NAT instance
4. Auto Scaling group

A: 3

Q6: easy, skipped. 

Q7: Which of the following should you consider implementing when you need to allow a user access to an S3 bucket? (Choose TWO). 
1. Policies attached to the user
2. Security Group settings
3. Resource Policy
4. Network ACL

A: 1, 3

Q8: easy, skip. 

Q9: You are running a database on an Amazon EC2 instance, and need to run backups locally. What would be the most cost effective location for these backups?
1. Amazon Glacier
2. Amazon EBS Cold HDD Volume (sc1)
3. Amazon S3
4. Amazon EBS Throughput Optimized HDD Volume (st1)

A: 2

Notes: 1 and 3 are on the cloud, not local. So only EBS is left. Cold is cheapest. 

Q10: You are creating an application running on EC2 that needs access to DynamoDB. Which of the following is the most secure method to provide access for the application?
1. IAM Role
2. Keys for an IAM user
3. Keys for the AWS account
4. The username and password for an IAM User

A: 1. 

Notes: don't put keys in code. not to mention password. 

Q11: You need to replicate proprietary, on-premises, reporting system data into AWS for long term analytics and archival. It is estimated that you require a high performance connection that is dedicated to your use. What option is best for your scenario?
1. VPC Peering Connection
2. AWS Database Migration Service (DMS)
3. Virtual Private Network
4. AWS Direct Connect

A: 4. 

Q13: You need an application (web accessible) and database tier (Amazon RDS). What meets these requirements while maximizing security? 
1. Public subnets for both the application tier and the database
2. Public subnets for the application tier, and private subnets for the database
3. Public subnets for the application tier, plus private subnets for the database and NAT Gateway
4. Private subnets for both the application tier and the database

A: 2. 

Note: NAT Gateway is unnecessary. 









