📘 GitHub README.md (Detailed Project Steps):
markdown
Copy
Edit
# AWS NAT Gateway Project

This project demonstrates setting up a secure AWS network using a NAT Gateway to allow internet access for private EC2 instances.

## 🚧 Project Overview

Create a VPC with both public and private subnets, configure route tables, attach an Internet Gateway, and launch EC2 instances with appropriate network settings. The NAT Gateway is used to allow internet access from the private subnet.

---

## 🔧 Steps Performed

### 1. Create VPC
- Name: `vpc-nat`
- IPv4 CIDR block: `10.0.0.0/16`

### 2. Create Subnets
- **Public Subnet**
  - Name: `public-subnet`
  - AZ: `ap-south-1a`
  - CIDR block: `10.0.0.0/24`

- **Private Subnet**
  - Name: `private-subnet`
  - AZ: `ap-south-1a`
  - CIDR block: `10.0.1.0/24`

### 3. Internet Gateway
- Create IGW: `internet-gateway`
- Attach to `vpc-nat`

### 4. Route Tables
- **Public Route Table**
  - Name: `public-rt`
  - Add route: `0.0.0.0/0` → Internet Gateway
  - Associate with `public-subnet`

- **Private Route Table**
  - Name: `private-rt`
  - Associate with `private-subnet` (no default route yet)

### 5. NAT Gateway
- Create Elastic IP
- Deploy NAT Gateway in `public-subnet`
- Attach Elastic IP

- Update `private-rt`:
  - Add route `0.0.0.0/0` → NAT Gateway

### 6. EC2 Instances

#### Public EC2
- Name: `public-instance`
- AMI: Windows
- Type: `t3.micro`
- Key Pair: `public-key`
- Subnet: `public-subnet`
- Enable Auto-assign Public IP
- Security Group: Allow all traffic (for testing)

#### Private EC2
- Name: `private-instance`
- AMI: Windows
- Type: `t3.micro`
- Key Pair: `public-key` (same as public)
- Subnet: `private-subnet`
- Disable Public IP
- Security Group: Allow all traffic (for testing)

### 7. Testing Connectivity
- RDP into `public-instance`
- Disable Windows firewall
- Use RDP to connect from `public-instance` to `private-instance`
- Validate connectivity and private instance internet access via NAT Gateway

---

## ✅ Project Outcome

- Private instance successfully accessed via RDP from the public instance.
- Internet access for the private instance was enabled using NAT Gateway.
- Demonstrated secure and scalable network design in AWS.

---

## 🧰 Technologies Used
- AWS VPC, Subnets
- Internet Gateway, NAT Gateway
- Route Tables
- EC2 Instances (Windows)
- Security Groups, Elastic IP