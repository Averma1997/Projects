:
🚀 Today, I built an AWS project using NAT Gateway to enable secure internet access for private EC2 instances.
🔹 First, I created a VPC named vpc-nat with CIDR 10.0.0.0/16.
🔹 Then, created two subnets:
  📌 Public Subnet – CIDR 10.0.0.0/24, AZ ap-south-1a
  📌 Private Subnet – CIDR 10.0.1.0/24, AZ ap-south-1a
🔹 Added an Internet Gateway, attached it to the VPC.
🔹 Created a Public Route Table, added route 0.0.0.0/0 → IGW, and associated with the public subnet.
🔹 Created a Private Route Table and associated it with the private subnet.
🔹 Deployed a NAT Gateway in the public subnet with an Elastic IP.
🔹 Created two EC2 instances:
  💻 Public Instance: Windows AMI, public IP enabled, RDP access enabled.
  💻 Private Instance: Windows AMI, no public IP, all traffic allowed in SG.
🔹 Connected to the public instance via RDP, disabled firewall, and verified private instance access via RDP from inside.
✅ Successfully implemented secure private instance access using NAT Gateway!

#AWS #Cloud #VPC #NATGateway #EC2 #Networking #CloudComputing #ProjectWork