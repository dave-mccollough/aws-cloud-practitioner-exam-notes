# Virtual Private Cloud (VPC) and Networking

## IP addresses in AWS

- IPv4
  - Internet Protocol Version 4
  - Public IPv4
    - EC2 instances get a new public IP each time you stop then start them - default behavior
  - Private IPv4
    - Can be used for private networks (LAN) or internal AWS networking
    - Fixed for EC2 instances even after a stop/start
  - **Elastic IP**
    - Allows you to attach fixed public IPv4 addresses to EC2 instances
    - All public IPv4 addressses will be charged $0.005 per hour
- IPv6
  - Internet Protocol Version 6 
    - All addresses are public in AWS

## VPC and Subnets

- VPC
  - Virtual Private Cloud
  - Private network to deploy your resources
- Subnets
  - Allows you to partition your network inside you VPC
- Public Subnet
  - Subnet accessible from the internet
  - Have a route to the internet gateway
- Private Subnet
  - Subnet that is not accessible from the internet
- Route Tables
  - Define access between subnets and to the internet
- Internet Gateways
  - Helps VPC instances connect with the internet
- NAT Gateways
  - AWS Managed
  - Allow instances within a private subnet to access the internet while remaining private
- NAT Instances
  - Self Managed
  - Allow instances within a private subnet to access the internet while remaining private

## Security Groups and Network Access Control Lists (ACL)

- NACL
  - Network ACL
  - Operates at the subnet level
  - Stateless
    - Return traffic must be explicitly allowed by rules
  - Rules are processed in numbered order when deciding whether to allow traffic
  - Firewall that controls traffic to and from subnet
  - Can have ALLOW and DENY rules
  - Are attached at the subnet level
  - Rules only include IP addresses
- Security Groups
  - Operates at the instance level
  - Is stateful
    - Return traffic is allowed regardless of rules
  - All rules are evaluated before deciding whether to allow traffic
  - Firewall that controls traffic to and from an EC2 Instance
  - Supports only ALLOW rules
  - Rules include IP addresses and other security groups

## VPC Flow Logs and VPC Peering

- VPC Flow Logs
  - Capture information about IP traffic going into your interfaces
    - VPC Flow Logs
    - Subnet Flow Logs
    - Elastic Interface Flow Logs
  - Helps monitor and troubleshoot connectivity issues
  - Captures network information form AWS managed interfaces
  - VPC flow logs can be routed to S3, CloudWatch Logs and AWS Firehose

- VPC Peering
  - Connect VPC using AWS network
  - Makes them behave as if they are the same network
  - Must not have overlapping CIDR 
  - Must be established for each VPC that needs to communicate with one another

## VPC Endpoints

- Allow you to connect to AWS services using a private network instead of public network
- Lower latency and improved security
- VPC Endpoint Gateway
  - S3
  - DynamoDB
- VPC Endpoint Interface
  - Most services

## AWS PrivateLink - VPC Endpoint Services

- Secure and scalable way to expose a service to 1000s of VPCs
- Does not require VPC peering, internet gatewy, NAT route tables, etc
- Requires a network load balancer
  - Service VPC
  - Customer VPC (ENI)

## Site to Site and Direct Connect

- Site to Site VPN
  - Connect an on-prem VPN to AWS
  - Connection is automatically encrypted
  - Connection over public internet
  - On-prem must use a customer gateway
  - AWS must use a virtual private gateway
- Direct Connect (DX)
  - Physical connection between onprem and AWS
  - Connection is private, secure, fast
  - Connection is over a private network
  - Takes at least a month to establish

## AWS ClientVPN

- Connect from computer using OpenVPN to AWS network
- Allows you to connect to your EC2 instances over a private IP
- Routed over public internet

## Transit Gateway

- Transitive peering between thousands of VPCs and on-prem
  - Hub and spoke connection - star
- One gateway provides the functionality
- Works with Direct Connect Gateway and VPN Connections