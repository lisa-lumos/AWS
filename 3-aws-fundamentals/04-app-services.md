# 4. App Services
Application integration and customer engagement services. 

## Step Functions
Using a visual workflow, coordinates the components of distributed applications and microservices. E.g.: Make the 2nd function to run only if the first function succeeds, or execute 2 functions in parallel. Define your application visually as a series of steps, then deploy the application automatically. 

## Simple WorkFlow (SWF)
Works similar to step functions in coordinating multiple components of a business process. For new applications, recommend to use step functions, instead of SWF. 

## Simple Notification Service (SNS)
Flexible, fully managed pub-sub messaging service. You can create a topic, and users can subscribe to that topic, so when you publish a message, they can receive  it. It can also push notifications to mobile device. 

## Simple Queue Service (SQS)
Fully managed message queueing service, so you can decouple you applications from demand. It allows messages to build up in a queue, until the processing server can catch up with demand. 

### Example
An application which is a process server that runs on a auto-scaling group of 2 EC2 instances. When messages come in, the auto-scaling group will add more instances to cope with the increasing demand. But if the increase in demand (and a large spike) happens in 1 second, and the auto-scaling group cannot handle it, because it takes 5-10 min to each instance to launch and be up and running. If there is a queue (SQS) in front of the auto-scaling group, the requests can then be handled. But if the average demand exceeds the max capacity of the auto-scaling group (because instances are unhealthy, app is faulty, etc), and messages in queue builds up, the solution is, we can put a CloudWatch Alarm (metric) for the queue, so it will alert us with SNS email notification if the queue continues to grow and we need to investigate it. This CloudWatch metric could also alert the auto-scaling group that the queue is too big, so the auto-scaling group knows to launch more instances, and vise versa, to reduce num of instances when queue is empty - which is a automated solution for the problem. 

## Amazon Connect
A self-service contact center; pay-as-you-go. Has a drag and drop GUI so you can create process flows that define customer interactions, without coding. 

## Amazon Pinpoint
Allow you to send email, SMS and mobile push messages for targeted marketing campaigns, and direct messages to your individual customers. E.g.: for an order confirmation. 

## Simple Email Service (SES)
Bulk email sending service. 

### Using SES to send an email


















