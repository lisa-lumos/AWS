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
Global content delivery network. 

























