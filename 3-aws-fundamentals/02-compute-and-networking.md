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

## Creating a Web Server with EC2
Search ec2 in the console, Launch instance -> (Need to find an Amazon machine image, AMI, that has Linux OS and WordPress application) AWS Marketplace -> In the search bar, search for "bitnami wordpress", Select the one named WordPress with NGINX and SSL Certified by Bitnami and Automattic -> In the pricing page that pops up, click Continue -> Check the t2.micro instance type -> Next: Configure Instance Details (default VPC is created when we create an AWS account for the first time, and make sure to enable Auto-assign Public IP, so the web server will be discoverable)-> Next: Add Storage. -> Next: Add Tags, Add Tag, Key: Name (Note the capitalized N), Value: Wordpress -> Configure Security Group, create a rule that allows inbound traffic to web server (default is block inbound traffic, but the Bitnami AMI has automatically set it up for us, including ssh, http and https from any source) -> Review and Launch -> Launch -> We do not need to create a key pair for this practice, so check the "I acknowledge ..." -> Launch Instances

View Instances -> Go to the Status checks pane (see System status checks is Running, and Instance status checks is Running) -> Click on the Instance ID of the ec2 instance, see that the instance has got a Public IPv4 address, and a Public IPv4 DNS. Click "open address" hyperlink for either of them, if it shows This site can't be reached, then wait for a few more min and check again. If it shows Your connection is not private, this is because we do not have an SSL certificate associated with this web server. Copy the url to open it with http instead of https, and we see the Hello world page. This means out users can access the WordPress blog. But now we cannot access it as admin (append "wp-admin" to the url to access), because we need username and pwd. To get this, go to the logs of the Linux OS: In the instance page, Actions -> Monitor and troubleshoot -> Get system log -> scroll up a little bie, and see "Setting Bitnami application password to 'XXXX...'". Put it in the login url page and login as admin. Posts -> AddNew -> ...

To remove this instance, In the instance page, Instance state -> Terminate instance -> Terminate



























