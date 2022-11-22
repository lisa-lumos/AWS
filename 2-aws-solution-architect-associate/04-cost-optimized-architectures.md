# Cost-Optimized Architectures
Q1: An application you want to run on Amazon Elastic Compute Cloud (Amazon EC2) requires you to license it based on the number of physical CPU sockets and cores on the hardware on which you plan to run the application. Which tenancy model should you specify? 1. Dedicated Host? 2. Dedicated Instance? 3. Shared tenancy? 4. Bring your own license (BYOL)?

A: 1. Dedicated host.  

Notes: BYOL is not a tenancy model. Shared tenancy is default, which means many people share a host. Dedicated host (dedicated hardware to support existing software licenses and improve compliance) have a dedicated host id. The use of dedicated tenancy will launch instances as dedicated instances. 

Q2: A sales reporting application running on EC2 is set up to run once at the end of every month. The report takes several hours to compile, but can be paused and resumed. To achieve the best possible price for this workload, which Amazon EC2 payment model should be used? 

A: Spot instances. 

Notes: do not have a consistent workload. Need to achieve best price.

Q3: Your business wants to migrate an existing application to its AWS account along with its relational database. This app needs to be available at all times, but will also experience unpredictable periods of inactivity. What is the best solution to build this application that minimizes costs?
1. Run the app in containers with Fargate and use Amazon Aurora Serverless for the database. 
2. Run the app on EC2 instances using a T-class instance type. Use Amazon Redshift for the database. 
3. Use AWS CloudFormation to deploy the infrastructure when it is needed. Delete the stack at the beginning of the idle periods. 
4. Deploy the application on EC2 instances in an Auto Scaling group behind an Application Load Balancer. Use Amazon RDS for MySQL for the database. 

A: 1. 

Notes: problem statement needs scale capabilities. CloudFormation is an orchestration engine, infra as code, you need to tell it to run, takes minutes to create instances, delay is too large for this scenario (takes too long to spin up). Serverless Aurora could grow/contract based on needs. You can also configure the db to Pause compute capacity after a certain time period. 



























