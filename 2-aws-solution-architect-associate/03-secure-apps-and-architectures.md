# 3. Secure Applications and Architectures
Q1: Which Amazon Simple Storage Service (Amazon S3) encryption option does not require AWS to persistently store the encryption keys that uses to decrypt data? 1. Client-side encryption? 2. SSE-KMS? 3. SSE-S3? 4. SSe-C?
A: Last one is correct. SSE: Server-side encryption. KMS: key management service. For S3, the keys are managed by the S3 service. SSE-Customer is the right answer. With client-side encryption, you can store your key with AWS still

Q2: Which of the following are features of Amazon Elastic Block Store (Amazon EBS)? (Select TWO.) 1. Amazon EBS volumes can be encrypted transparently to workloads on the attached instance? 2. Amazon EBS data is automatically backed up to tape? 3. Data on Amazon EBS volume is lost when the attached instance is stopped? 4. Data stored on Amazon EBS is automatically replicated within an Availability Zone? 
A: 1, 4

Q3: Which of the following should you consider implementing when you need to allow a user access to an S3 bucket? (Choose TWO) 1. Policies attached to the use? 2. Security Group setting? 3. Resource Policy? 4. Network ACL? 
A: 1， 3
Notes: Network ACL and security group are for VPC. 






















