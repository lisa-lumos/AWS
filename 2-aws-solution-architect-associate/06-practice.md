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
















