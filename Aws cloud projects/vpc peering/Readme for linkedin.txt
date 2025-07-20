🔧 AWS Hands-On Practice – VPC Peering & EC2 Communication Setup

📍 Region: Mumbai

1️⃣ Created VPC-1 with CIDR block 10.0.0.0/16
2️⃣ Created a subnet in VPC-1 named vpc-1-subnet with CIDR 10.0.0.0/24
3️⃣ Configured and attached an Internet Gateway to VPC-1
4️⃣ Created a Route Table named vpc-1-rt, added a route for 0.0.0.0/0 via Internet Gateway, and associated it with the subnet

5️⃣ Created VPC-2 with CIDR block 192.168.0.0/16
6️⃣ Set up its subnet, Internet Gateway, route table, and associations similarly

🔗 VPC Peering Configuration

7️⃣ Navigated to the VPC Peering section and created a connection named vpc-peering
8️⃣ Sent a peering request from VPC-1 to VPC-2 and accepted the request
9️⃣ Updated the route tables in both VPCs to allow traffic between 10.0.0.0/16 and 192.168.0.0/16

💻 EC2 Instance Deployment

🔸 Launched an EC2 instance named vpc-instance-1 in VPC-1
🔸 Selected Windows AMI, instance type t3.micro, and created a new key pair
🔸 Enabled public IP, selected ap-south-1b, opened required ports in the security group, and launched the instance

🔸 Repeated the same steps to launch another EC2 instance in VPC-2

🛠️ Configuration and Testing

🔸 Accessed both instances via RDP, disabled Windows Firewall via Server Manager
🔸 Verified connectivity between both instances using ping command – ✅ Success!

🎯 Successfully configured VPC peering and instance communication across VPCs in AWS. Great hands-on practice for networking fundamentals in the cloud!

#AWS #VPC #VPCPeering #EC2 #CloudNetworking #AWSTraining #HandsOn #CloudLearning #LinkedInLearning #AWSMumbaiRegion