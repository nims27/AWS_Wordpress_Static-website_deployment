# AWS_Wordpress_Static-website_deployment
Deploy static wordpress website using AWS console

Overview
This project demonstrates how to host a WordPress website on AWS using various AWS services and resources. The architecture includes a Virtual Private Cloud (VPC), public and private subnets, an Application Load Balancer (ALB), Auto Scaling Group, Amazon EFS for shared storage, Amazon RDS for database management, and more.

*** Architecture ***

>> Virtual Private Cloud (VPC):

Configured with public and private subnets across two Availability Zones for high availability and fault tolerance.
Public subnets house infrastructure components like the NAT Gateway and Application Load Balancer.
Private subnets house EC2 instances running the WordPress application.

>> Internet Gateway:

Facilitates connectivity between the VPC instances and the internet.

>> Security Groups:

Act as a network firewall to control inbound and outbound traffic to EC2 instances.

>> NAT Gateway:

Allows instances in private subnets to access the internet while remaining inaccessible from the outside world.

>> Application Load Balancer (ALB):

Distributes incoming web traffic to EC2 instances within the Auto Scaling Group across multiple Availability Zones.

>> Auto Scaling Group:

Manages EC2 instances to ensure availability, scalability, fault tolerance, and elasticity.

>> Amazon EFS:

Provides a shared file system for storing WordPress files.

>> Amazon RDS:

Hosts the MySQL database for WordPress.

>> AWS Certificate Manager:

Secures application communications with SSL/TLS certificates.

>> Amazon Route 53:

Manages DNS records and domain registration.

>> Amazon SNS:

Configured to alert about activities within the Auto Scaling Group.

*** Setup Instructions ***

1. VPC and Subnet Configuration
Create a VPC with both public and private subnets across two Availability Zones.
Deploy an Internet Gateway and associate it with the VPC.
Configure Security Groups to control access to instances.
Place infrastructure components like NAT Gateway and ALB in public subnets.
Ensure instances in private subnets can access the internet through the NAT Gateway.

2. EC2 Instance Deployment
Launch EC2 instances in private subnets for the WordPress application.
Configure EC2 Instance Connect for secure connections.
Use Auto Scaling Groups to manage the EC2 instances.

3. Application Load Balancer Setup
Deploy an ALB in public subnets to handle incoming web traffic.
Configure the ALB to route traffic to EC2 instances across multiple Availability Zones.
Set up a target group and attach it to the ALB.

4. Shared Storage with Amazon EFS
Set up Amazon EFS and mount it to the EC2 instances.
Use EFS to store WordPress files.

5. Database Setup with Amazon RDS
Launch an RDS instance for MySQL.
Configure WordPress to connect to the RDS instance.

6. DNS Configuration
Register a domain name and set up DNS records using Amazon Route 53.

7. SSL/TLS Configuration
Use AWS Certificate Manager to secure communication with SSL/TLS certificates.

8. Auto Scaling and Monitoring
Set up Auto Scaling Groups to manage EC2 instances.
Configure Amazon SNS to alert about scaling activities.

*** Conclusion ***

This project sets up a robust, scalable, and secure WordPress hosting environment on AWS. It leverages AWS infrastructure and services to ensure high availability, fault tolerance, and scalability. For more details, check the GitHub repository containing the reference diagrams and scripts.

