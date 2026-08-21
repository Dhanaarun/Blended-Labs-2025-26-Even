# Build Your VPC and Launch a Web Server (AWS) 

## Author

* **Name**: Dhanashree A
* **Register Number**: 212224040065
* **Date of Submission**: 21.08.2026

---

## Objective

The objective of this experiment is to understand how to design and configure a basic network infrastructure in AWS using a Virtual Private Cloud (VPC). This lab focuses on creating a VPC with a public subnet, configuring an Internet Gateway and route table, launching an EC2 instance, and hosting a simple web server that can be accessed over the internet.

---

## Prerequisites

* Basic understanding of cloud computing concepts
* AWS account or AWS Academy Lab access
* Web browser with internet connectivity

---

## Tools Used

* AWS Management Console
* Amazon VPC
* Amazon EC2
* Internet Gateway
* Route Table
* Security Groups

---

## Tasks Performed

### Task 1: Create a VPC

Create a new Virtual Private Cloud (VPC) with a private IP address range. The VPC acts as a logically isolated network in AWS where all other resources will be deployed.

Students should create a VPC with an appropriate CIDR block (for example, 10.0.0.0/16) and assign a meaningful name.


### Task 2: Create a Public Subnet

Create a subnet inside the VPC to host public resources. Enable auto-assign public IPv4 so that instances launched in this subnet receive a public IP address.

The subnet should use a smaller CIDR range (for example, 10.0.1.0/24).


### Task 3: Create and Attach Internet Gateway

Create an Internet Gateway (IGW) and attach it to the VPC. This allows communication between resources in the VPC and the internet.


### Task 4: Configure Route Table

Create a route table and add a default route (0.0.0.0/0) pointing to the Internet Gateway. Associate this route table with the public subnet.

This step ensures that traffic from the subnet can reach the internet.


### Task 5: Create Security Group

Create a security group to act as a virtual firewall for the EC2 instance. Configure inbound rules to allow:

SSH on port 22

HTTP on port 80


### Task 6: Launch EC2 Instance

Launch an EC2 instance inside the public subnet using Amazon Linux 2 AMI and a suitable instance type (t2.micro).

Attach the previously created security group and key pair.


### Task 7: Configure Web Server

Install and start a web server (Apache HTTPD) on the EC2 instance using user data or manual commands.

Create a simple HTML page and verify that it can be accessed from a web browser using the public IP address of the instance.---

## Workflow (Student Explanation)

(Write the steps you followed in your own words)
Step-1:
I started the lab and logged into the Amazon Web Services Management Console in the N. Virginia (us-east-1) region.
Step-2:
I created a custom VPC using Amazon VPC, configured public and private subnets, and enabled an Internet Gateway and NAT Gateway to manage internet connectivity.
Step-3:
I added additional public and private subnets in a second Availability Zone and updated the route tables to ensure proper routing for both internet-facing and private traffic.
Step-4:
I created a Security Group named Web Security Group and configured it to allow HTTP (port 80) access from anywhere to enable web traffic.
Step-5:
I launched an EC2 instance using Amazon EC2 in the public subnet, enabled auto-assign public IP, attached the security group, and selected the required key pair.
Step-6:
I configured a user data script to automatically install Apache and deploy a web application, then verified the web server by accessing the instance’s public DNS in a browser.

---

## Output Screenshots (Attach 3)

### Screenshot 1: VPC and Subnet Details
<img width="1328" height="572" alt="image" src="https://github.com/user-attachments/assets/82f508c9-adbb-4eeb-8ef0-2539428b8b3b" />


---

### Screenshot 2: EC2 Instance Running

<img width="1322" height="582" alt="image" src="https://github.com/user-attachments/assets/0d3d15d0-1a5a-4341-b549-54fa687ce1c1" />

---

### Screenshot 3: Web Server Output in Browser




<img width="1315" height="613" alt="Screenshot 2026-08-21 153408" src="https://github.com/user-attachments/assets/2c9eea83-fa86-4fb4-85c0-1b78602395a3" />


---

## Result 

This experiment successfully demonstrated the creation of a custom VPC and deployment of a public-facing web server in AWS. By configuring networking components such as subnets, route tables, and security groups, and by launching an EC2 instance with a web server, the basic architecture of a cloud-hosted application was understood.
