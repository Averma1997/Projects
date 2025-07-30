🚀 Project: Deploying OpenVPN on AWS (Step-by-Step Guide)
Today, I successfully deployed OpenVPN on AWS using the following steps:

🛠️ Step-by-Step Configuration
Login to AWS Console
Logged in to the AWS Management Console.

VPC Creation

Navigated to VPC section.

Clicked on Create VPC → Selected VPC Only.

Gave a name: my-vpc.

Assigned IPv4 CIDR block: 10.0.0.0/16.

Clicked Create VPC.

Public Subnet Creation

Went to Subnets section → Clicked Create Subnet.

Selected VPC: my-vpc.

Named it: public-subnet.

Chose Availability Zone: ap-south-1a.

Assigned IPv4 Subnet CIDR block: 10.0.0.0/24.

Clicked Create Subnet.

Internet Gateway Setup

Navigated to Internet Gateways → Clicked Create Internet Gateway.

Named it: internet-gateway.

Attached it to my-vpc.

Route Table Setup

Went to Route Tables → Clicked Create Route Table.

Named it: public-route.

Associated with my-vpc.

Added a route:

Destination: 0.0.0.0/0

Target: internet-gateway

Saved changes.

Under Subnet Associations, associated public-subnet.

Private Subnet Creation

Again went to Subnets section → Clicked Create Subnet.

Selected same VPC: my-vpc.

Named it: private-subnet.

Availability Zone: ap-south-1a.

IPv4 Subnet CIDR block: 10.0.1.0/24.

Clicked Create Subnet.

Launch EC2 Instance for OpenVPN

Navigated to EC2 → Clicked Launch Instance.

Named it: openvpn.

Chose OpenVPN Access Server AMI (subscribed beforehand).

Selected instance type: t3.small.

Created and selected a new key pair: openvpn-key.

Chose my-vpc and public-subnet.

Enabled Auto-assign Public IP.

Created a Security Group allowing All Traffic (for testing/demo purpose).

Launched the instance.

Connect to EC2 using PuTTY

Used PuTTYgen to convert .pem key to .ppk format.

Opened PuTTY → Entered EC2 public IP under Host Name.

Under SSH → Auth → Browse and selected the .ppk private key.

Logged into the instance via SSH.

Configure OpenVPN Access Server

Ran initial OpenVPN Access Server setup commands.

Accepted the license agreement.

Changed the admin password using passwd openvpn.

Copied the client URL provided after setup.

Accessed the OpenVPN web interface using the browser.

Logged in with openvpn user and password.

Downloaded and installed the OpenVPN client on Windows.

Logged in with credentials and started the VPN.

Access Private Instance through VPN

Decrypted the private instance’s key from the AWS console.

Retrieved RDP credentials.

Connected via RDP using private IP through OpenVPN.

Project successfully completed 🎉.

✅ Outcome
🔐 Successfully configured OpenVPN Access Server in AWS and connected securely to a private instance using RDP over VPN.

🔗 Tools & Services Used
AWS EC2, VPC, Subnetting, Route Tables, Internet Gateway

OpenVPN Access Server AMI

PuTTY / PuTTYgen

Windows RDP