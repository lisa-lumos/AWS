# 2. Compute and Networking
## EC2 (Elastic Compute Cloud)

## EC2 Autoscaling

## Amazon Lightsail
Launch virtual servers running applications. 

## ECS (Elastic Container Service)
Highly scalable high performance container management service for Docker containers. The containers run on a managed cluster of EC2 instances. 

## AWS Lambda
Serverless, let you run code in AWS

## Examples
In a VPC, we can run a web app (such as WordPress), if this single EC2 instance cannot handle the demand, we can scale num of EC2 instances in or out depends on demand, via Auto Scaling Group, it also can check health of instances, and replace unhealthy instances with healthy instances. We then need a single endpoint for customer to go to, and direct customers to different instances, via a Elastic Load Balancer, it also can check health of instances. 

## CloudFront
Global content delivery network - securely delivers your frequently requested content to over 100 edge locations across the globe - achieves low latency and high transfer speeds for your end-users. Provides protection against DDoS attacks. 

## VPC (Virtual Private Cloud)
Let you provision a logically isolated section of the AWS cloud, and you can launch AWS resources in this virtual network of yours. No one can enter it unless you allow them to. 

## AWS Direct Connect
High speed, private, dedicated fiber-optic network connection to AWS. 

## Elastic Load Balancing (ELB)
Automatically distributes incoming traffic for your application across multiple EC2 instances, and also in multiple availability zones. If one AZ goes down, traffic will automatically be directed to other AZs. Could achieve high availability and fault tolerance by distributing traffic among these instances. 

## Route 53
Highly available and scalable domain name system (DNS), can handle direct traffic for your domain name and direct it to your back-end web server. 

## API Gateway
Fully managed service that makes it easy for developers to create and deploy secure APIs at any scale. Serverless. 

## Examples
It is always desirable to have architecture distributed across multiple AZs. In the above example, we can have EC2 instances across different AZs to have better availability. Furthermore, if the app running on the EC2 instances is a WordPress web server with a lot of images and videos (static content), then on top of EC2s, we can use CloudFront CDN, so the large static contents can be cached, to reduce latency for end users. It will also take the load off the EC2 instances, so that only the dynamic content that changes frequently will be forwarded over to ELB, and then to the EC2s. However, the CloudFront CDN service have its own DNS name that is complicated and means nothing to the end user, so we need Route 53, so user could use a domain name, and have the request forwarded to the CloudFront service. 











