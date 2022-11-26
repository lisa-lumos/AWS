# 5. Review
CloudFront has a cache, which could indirectly save cost. 

Q1: What is the most cost-effective way to save easily reproducible and highly accessed objects? 
1. S3-IA
2. Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA)
3. Amazon S3 Standard (S3 Standard)
4. Amazon Simple Storage Service Glacier

A: 3

Notes: because it is highly accessed, for IA, you need to pay for retrievals. You can expedite retrieval for Glacier, but there's a fee, and shouldn't be done frequently. For S3 Standard, you can retrieve things quickly. 

Q2: A company is planning to use Amazon Simple Storage Service (Amazon S3) to host project documents. At the end of the project, the documents must be moved to archival storage. Which implementation step would ensure that the documents are managed accordingly? 
1. Add a bucket policy on the Amazon S3 bucket
2. Configure lifecycle configuration rules on the Amazon S3 bucket. 
3. Create an AWS Identity and Access Management (IAM) policy for the Amazon S3 bucket
4. Enable cross-origin resource sharing (CORS) on the Amazon S3 bucket

A: 2

Q3: Which services use edge locations by default?
1. Amazon Cloud Front
2. AWS WAF
3. Amazon Route 53
4. All of the above

A: 4

Notes: 













