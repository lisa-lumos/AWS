# 3. Secure Applications and Architectures
Q1: Which Amazon Simple Storage Service (Amazon S3) encryption option does not require AWS to persistently store the encryption keys that uses to decrypt data? 1. Client-side encryption? 2. SSE-KMS? 3. SSE-S3? 4. SSe-C?

A: Last one is correct. SSE: Server-side encryption. KMS: key management service. For S3, the keys are managed by the S3 service. SSE-Customer is the right answer. With client-side encryption, you can store your key with AWS still

Q2: Which of the following are features of Amazon Elastic Block Store (Amazon EBS)? (Select TWO.) 1. Amazon EBS volumes can be encrypted transparently to workloads on the attached instance? 2. Amazon EBS data is automatically backed up to tape? 3. Data on Amazon EBS volume is lost when the attached instance is stopped? 4. Data stored on Amazon EBS is automatically replicated within an Availability Zone? 

A: 1, 4

Q3: Which of the following should you consider implementing when you need to allow a user access to an S3 bucket? (Choose TWO) 1. Policies attached to the use? 2. Security Group setting? 3. Resource Policy? 4. Network ACL? 

A: 1， 3

Notes: Network ACL and security group are for VPC. 

Q4: You are creating an application running on EC2 that needs access to DynamoDB. Which of the following is the most secure method to provide access for the application? 1. IAM Role? 2. Keys for a IAM user? 3. Keys for the AWS account? 4. The username and password for an IAM user?

A: 1. 

Notes: Generally if you see role as a choice, that is often the right choice. EC2 can have a role attached to it, which passes on the policies that is attached to this role to any processes that runs inside that EC2 instance. It is the best way to pass permissions to whatever runs on that instance. Hard coded keys in anything is just a bad idea. Using AWS account (root) for this is risky, as has credit card info etc, need to avoid root for day to day work. Choice 4 is as bad as a key. IAM roles can be attached to EC2 instances, to lambda functions, basically anything that does compute, so it allows that compute service to access other AWS services. You can also allow an IAM user to assume the role, even across accounts.  

Q5: What must you create first before you can establish subnets? 1. Security Group? 2. Network ACL? 3 Route table? 4. VPC?

A: 4. 

Q6: You need an application (web accessible) and database tier (Amazon RDS).. What meets these requirements wile maximizing security? 1. Public subnets for both the application tier and the database? 2. Public subnets for the application tier, and private subnets for the database? 3. Public subnets for the application tier with NAT Gateway, and private subnets for the database? 4. Public subnets for the application tier, plus private subnets for the database and NAT Gateway? 5. Private subnets for both the application tier and the database? 
 
A: 2 . NAT: network access translation. Choice 5 need a load balancer to be accessible to the web. 


















