# 4. Networking

## 🏷 Connectivity to AWS
### Amazon Virtual Private Cloud (Amazon VPC)
A `networking service` that you can use to establish `boundaries around your AWS resources` is `Amazon Virtual Private Cloud (Amazon VPC)`.

Amazon VPC enables you to provision an `isolated section` of the AWS Cloud. In this isolated section, you can launch resources in a `virtual network` that you define. Within a virtual private cloud (VPC), you can organize your resources into `subnets`. A subnet is a section of a VPC that can contain resources such as Amazon EC2 instances.

### Internet gateway
To allow `public traffic` from the internet to access your VPC, you attach an `internet gateway` to the VPC. An internet gateway is `a connection between a VPC and the internet`. Without an internet gateway, no one can access the resources within your VPC.

### Virtual private gateway
To access `private resources` in a VPC, you can use a `virtual private gateway` - it allows traffic into the VPC `only if it is coming from an approved network`. The virtual private gateway is the component that allows `protected internet traffic` to enter into the VPC. A virtual private gateway enables you to establish a `virtual private network (VPN) connection` between `your VPC and your private network`, such as an on-premises data center or internal corporate network. 

### AWS Direct Connect
`AWS Direct Connect` is a service that enables you to establish a `dedicated private connection` between your data center and a VPC. The private connection that AWS Direct Connect provides helps you to `reduce network costs` and `increase the amount of bandwidth` that can travel through your network.

## 🏷 Subnets and network access control lists
### Subnets
In a VPC, `subnets` are separate areas that are used to `group together resources` based on security or operational needs. Subnets can be `public` or `private`. `Public subnets` contain resources that need to be accessible by the public, such as an online store’s website. `Private subnets` contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories. 

In a VPC, `subnets can communicate with each other`. For example, you might have an application that involves Amazon EC2 instances in a public subnet communicating with databases that are located in a private subnet.

### Network traffic in a VPC
When a customer requests data from an app hosted in the AWS Cloud, this request is sent as a `packet`. A packet is a `unit of data` sent over the internet or a network. It enters into a VPC through an `internet gateway`. Before a packet can `enter or exit a subnet`, it `checks for permissions`. These permissions indicate who sent the packet and how the packet is trying to communicate with the resources in a subnet. The VPC component that checks packet permissions for subnets is a `network access control list (ACL)`.

### Network (subnet) access control lists (ACLs)
A `network access control list (ACL)` is a `virtual firewall` that controls `inbound` and `outbound` traffic at the `subnet`. Each AWS account includes a `default network ACL`, you also create `custom network ACLs`. 

By default, your account’s `default network ACL` `allows all` inbound and outbound traffic, but you can modify it by adding your own `rules`. For `custom network ACLs`, all inbound and outbound traffic is `denied` until you add rules to specify which traffic to `allow`. Additionally, all network ACLs have an `explicit deny rule`. This rule ensures that if a packet doesn’t match any of the other rules on the list, the packet is denied. 

### Stateless packet filtering
`Network ACLs` perform `stateless` packet filtering. They `remember nothing` and check packets that cross the subnet border each way: inbound and outbound. When a packet response for that request comes back to the subnet, the network ACL does not remember your previous request. The network ACL checks the packet response against its list of rules to determine whether to allow or deny. 

### Security groups
After a packet has entered a subnet, it must have its permissions evaluated for resources inside the subnet, such as Amazon EC2 instances. The `VPC component` that checks packet permissions for an `Amazon EC2 instance` is a `security group`. A `security group` is a `virtual firewall` that controls `inbound and outbound traffic` for an `Amazon EC2 instance`. By default, a security group `denies all inbound` and `allows all outbound` traffic. You can add `custom rules` to configure which traffic to allow or deny.

If you have `multiple Amazon EC2 instances within a subnet`, you can associate them with the `same` security group or `use different` security groups for each instance. 

### Stateful packet filtering
`Security groups` perform `stateful` packet filtering. They `remember` previous decisions made for incoming packets. Consider the same example of sending a request out from an Amazon EC2 instance to the internet. When a packet response for that request returns to the instance, the security group `remembers your previous request`. The security group allows the response to proceed, `regardless of inbound security group rules`.

Both `network ACLs` and `security groups` enable you to configure custom rules for the traffic in your VPC.

## 🏷 Global networking
### Domain Name System (DNS)
Suppose that AnyCompany has a website hosted in the AWS Cloud. Customers enter the web address into their browser, and they are able to access the website. This happens because of `Domain Name System (DNS)` resolution. DNS resolution involves a `customer DNS resolver` communicating with a `company DNS server`. DNS resolution is the process of `translating a domain name to an IP address`. 

For example, suppose that you want to visit AnyCompany’s website. 
1. When you enter the domain name into your browser, this request is sent to a customer DNS resolver. 
2. The customer DNS resolver asks the company DNS server for the IP address that corresponds to AnyCompany’s website.
3. The company DNS server responds by providing the IP address for AnyCompany’s website, 192.0.2.0.

### Amazon Route 53 for DNS
`Amazon Route 53` is a `DNS web service`. It gives developers and businesses a reliable way to `route` end users to `internet applications hosted in AWS`. Amazon Route 53 connects user requests to infrastructure running in AWS (such as Amazon EC2 instances and load balancers). It can route users to `infrastructure outside of AWS`.

Another feature of Route 53 is the ability to `manage` the `DNS records for domain names`. You can `register new domain names directly` in Route 53. You can also `transfer DNS records` for existing domain names managed by other domain registrars. This enables you to `manage all of your domain names within a single location`.

### Example: How Amazon Route 53 and Amazon CloudFront deliver content
Suppose that AnyCompany’s application is running on several Amazon EC2 instances. These instances are in an `Auto Scaling group` that attaches to an `Application Load Balancer`. 
1. A customer requests data from the application by going to AnyCompany’s website. 
2. Amazon Route 53 uses DNS resolution to identify AnyCompany.com’s corresponding IP address, 192.0.2.0. This information is sent back to the customer. 
3. The customer’s request is sent to the nearest edge location through Amazon CloudFront. 
4. Amazon CloudFront connects to the Application Load Balancer, which sends the incoming packet to an Amazon EC2 instance.
















