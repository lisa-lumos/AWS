# Cost-Optimized Architectures
Q1: An application you want to run on Amazon Elastic Compute Cloud (Amazon EC2) requires you to license it based on the number of physical CPU sockets and cores on the hardware on which you plan to run the application. Which tenancy model should you specify? 1. Dedicated Host? 2. Dedicated Instance? 3. Shared tenancy? 4. Bring your own license (BYOL)?

A: 1. Dedicated host.  

Notes: BYOL is not a tenancy model. Shared tenancy is default, which means many people share a host. Dedicated host (dedicated hardware to support existing software licenses and improve compliance) have a dedicated host id. The use of dedicated tenancy will launch instances as dedicated instances. 

Q2: A sales reporting application running on EC2 is set up to run once at the end of every month. The report takes several hours to compile, but can be paused and resumed. To achieve the best possible price for this workload, which Amazon EC2 payment model should be used? 

A: Spot instances. 

Notes: do not have a consistent workload. Need to achieve best price. 





























