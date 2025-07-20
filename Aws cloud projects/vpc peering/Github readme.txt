# AWS VPC Peering and EC2 Communication Setup

This project demonstrates how to set up VPC peering between two VPCs in the **Mumbai (ap-south-1)** region and enable communication between EC2 instances across both VPCs.

---

## 🗺️ Region: Mumbai (ap-south-1)

---

## 🏗️ Step-by-Step Setup

### 1. Create VPC-1
- **CIDR Block**: `10.0.0.0/16`
- **Subnet**: `vpc-1-subnet` → `10.0.0.0/24`
- **Internet Gateway**: Created and attached to VPC-1
- **Route Table**: `vpc-1-rt`
  - Route: `0.0.0.0/0` → Internet Gateway
  - Subnet Association: `vpc-1-subnet`

---

### 2. Create VPC-2
- **CIDR Block**: `192.168.0.0/16`
- **Subnet**: `vpc-2-subnet` → `192.168.0.0/24`
- **Internet Gateway**: Created and attached to VPC-2
- **Route Table**: `vpc-2-rt`
  - Route: `0.0.0.0/0` → Internet Gateway
  - Subnet Association: `vpc-2-subnet`

---

### 3. Configure VPC Peering
- **Name**: `vpc-peering`
- **Peering Request**: From VPC-1 to VPC-2
- **Accept Request**: From VPC-2
- **Route Table Updates**:
  - **VPC-1**: Add route `192.168.0.0/16` → Peering Connection
  - **VPC-2**: Add route `10.0.0.0/16` → Peering Connection

---

### 4. Launch EC2 Instances

#### VPC-1 EC2 Instance
- **Name**: `vpc-instance-1`
- **AMI**: Windows
- **Type**: `t3.micro`
- **Key Pair**: `vpc-instance-key`
- **Network Settings**: VPC-1, Subnet `ap-south-1b`
- **Public IP**: Enabled
- **Security Group**: Allow RDP (TCP 3389), ICMP (ping)

#### VPC-2 EC2 Instance
- Similar configuration, launched in **VPC-2**

---

### 5. Configuration & Testing
- Access EC2 via **RDP**
- Disable **Windows Firewall** in both instances via Server Manager
- Use **ping** command between both instances
- ✅ **Result**: Successful communication via VPC Peering

---

## 📌 Summary
This setup validates a successful VPC Peering connection and EC2 communication between two isolated VPCs across different CIDR blocks in the same AWS region.

---

## 📁 Tags
`#AWS` `#VPC` `#EC2` `#Peering` `#Networking` `#CloudSkills` `#HandsOnLabs` `#MumbaiRegion`

---

## 🧑‍💻 Author
**Awesome Verma**  
Cloud & IT Enthusiast | RHEL Linux | AWS | Networking | Python  
[LinkedIn](https://www.linkedin.com) <!-- Replace with actual LinkedIn profile -->