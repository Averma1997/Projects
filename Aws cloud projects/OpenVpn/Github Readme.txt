🛡️ OpenVPN Deployment on AWS – Project Documentation
This project demonstrates how to deploy an OpenVPN Access Server on AWS and securely connect to a private EC2 instance using a VPN tunnel.

🔧 Infrastructure Setup on AWS
1. Login and VPC Creation
Logged in to the AWS Management Console.

Navigated to the VPC section.

Clicked Create VPC → selected VPC only.

Assigned a name to the VPC and set the IPv4 CIDR block to 10.0.0.0/16.

Clicked Create.

2. Create Public Subnet
Opened Subnets → clicked Create Subnet.

Selected the created VPC.

Named the subnet: public-subnet.

Selected Availability Zone: ap-south-1a.

Set IPv4 Subnet CIDR block to 10.0.0.0/24.

Clicked Create Subnet.

3. Internet Gateway Configuration
Navigated to Internet Gateways → clicked Create Internet Gateway.

Named it: internet-gateway.

Attached the Internet Gateway to the VPC.

4. Create Route Table for Public Subnet
Went to Route Tables → clicked Create Route Table.

Named it: public-route.

Selected the VPC.

Added a route:

Destination: 0.0.0.0/0

Target: Internet Gateway

Saved changes.

In Subnet Associations, selected the public-subnet.

5. Create Private Subnet
Again navigated to Subnets → clicked Create Subnet.

Selected the same VPC.

Named the subnet: private-subnet.

Availability Zone: ap-south-1a.

Set IPv4 Subnet CIDR block: 10.0.1.0/24.

Clicked Create.

🚀 Deploying OpenVPN EC2 Instance
6. Launch OpenVPN Server
Went to EC2 Dashboard → clicked Launch Instance.

Instance name: openvpn.

Selected the OpenVPN Access Server AMI (subscribed via AWS Marketplace).

Selected instance type: t3.small.

Created a new key pair: openvpn-key.

Configured network:

Selected the created VPC.

Selected public-subnet.

Enabled Auto-assign Public IP.

Created a Security Group with All traffic allowed (for testing only).

Launched the instance.

🔐 Connecting to OpenVPN Server
7. Access via SSH using PuTTY
Used PuTTYgen to convert the .pem key to .ppk.

Opened PuTTY:

Hostname: OpenVPN public IP.

SSH → Auth: Selected .ppk private key.

Logged into the instance via SSH.

8. OpenVPN Initial Configuration
Ran the command: openvpnas.

Accepted the license agreement.

Changed admin password using:

bash
Copy
Edit
passwd openvpn
Copied the client URL shown in the console output.

9. Client Access Setup
Opened the URL in a browser.

Logged in with the openvpn user and new password.

Downloaded and installed the OpenVPN Client for Windows.

Logged into the client and successfully started the VPN connection.

💻 Connecting to a Private EC2 Instance
10. Access Private Instance over VPN
Decrypted the private EC2 instance key using AWS Console.

Copied RDP credentials.

Opened Remote Desktop Connection on Windows.

Connected using the private IP of the instance.

Successfully accessed the private instance via the VPN tunnel.

✅ Final Result
✅ OpenVPN Access Server deployed and configured.

✅ VPN tunnel created and verified.

✅ Successfully accessed a private EC2 instance over VPN.

🧰 Tools & Services Used
Category	Tool/Service
Cloud Platform	AWS (EC2, VPC, Subnets)
VPN Solution	OpenVPN Access Server
Key Management	AWS Key Pairs, PuTTYgen
Remote Access	SSH, RDP, OpenVPN Client

