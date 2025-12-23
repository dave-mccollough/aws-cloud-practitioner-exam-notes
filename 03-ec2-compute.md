# EC2 - Elastic Compute Cloud

- Setup Budget

## EC2 Basics

- Most popular AWS offering
- Elastic Compute Cloud (IaaS)
  - VMs in the cloud (EC2)
  - Virtual Drives (EBS)
  - Load Balancing (ELB)
  - Scaling services - Autoscaling Group (ASG)

- Size and configuration options
  - Operating Systems
    - Mac
    - Windows 
    - Linux
  - CPU
  - RAM
  - Storage 
    - Network Attached (EBS and EFS)
    - Hardware (EC2 Instance Store)
  - Networking
    - Provides network access/public IP
  - Firewall Rules/Security group
  - Bootstrap script
    - Runs at launch
  - EC2 User Data
    - Launch commands when EC2 instance starts
    - Only runs on startup
    - Install updates
    - Install software
    - Download files from internet
    - Runs as root user 

## EC2 Instance Types

- [Link](https://aws.amazon.com/ec2/instance-types/)
- General Purpose
  - Great for most workloads
  - Good balance between 
    - Compute
    - Networking
    - Memory
- Compute Optimized
  - Great for compute intensive tasks/high performance processors
    - Batch processing
    - Media Transcoding
    - High performance compute
    - High performance web servers
    - Machine learning/data science
    - Game servers
- Memory Optimized
  - Great for workloads that process large datasets in memory
    - High performance non-relational databases
    - Distributed web cache
    - In memory databases for BI
    - Applications performing real time processing for unstructured data
- Storage Optimized
  - Great for storage intensive tasks with high speed read/write access
  - Data warehousing
  - Distributed file systems
  - Cache for redis

## EC2 Purchasing Options

- On Demand Instances
  - Pay for what you use
    - Linux and Windows - billed per second after the first minute
    - All other OS - Billed by the hour
    - Highest cost with no upfront payment
    - No long term commitment
    - Short term, uninterruptible, and unpredictable workloads
- Reserved instance
  - 1 and 3 year reservation period
  - Long running workloads
  - No upfront, partial upfront, or full upfront payment
  - Buy and sell in Reserved Instance Marketplace
  - Convertable instance types
    - Flexible instances - change EC2 instance type
- EC2 Saving Plans
  - Discount based on long term usage
  - Commig to certain type of usage
  - Locked to specific instance family and region
  - Flexible across
    - Instance size
    - OS
    - Tenancy
- Spot Instances
  - Most cost efficient AWS instance
    - Discounts of up to 90% compared to on demand
  - You can lose instance if your max price is less than current spot price
  - Not suitable for critical jobs
- Dedicated Hosts
  - Physical server with EC2 instance capacity fully dedicated to your use
  - Compliance requirements, software licenses
  - On demand or reserved purchase options
  - Most expensive

## Security Groups

- Fundamental to network security in AWS
- Controls how traffic is allowed in or out of EC2 instances
- Security rules only contain rules
- Security group rules can be referenced by IP or Security group
- Can be attached to multiple instances
- Can be locked to region or VPC configuration
- If traffic is blocked, EC2 won't see it
- Use one security group for SSH access
- If app times out, may be security group issue
- All inbound traffic is blocked by default
- All outbound traffic is authorized by default
- Ports to know
  - 22: SSH
  - 21: FTP
  - 22: SFTP
  - 80: HTTP
  - 443: HTTPS
  - 3389: RDP

## EC2 Instance Connect

- Browser based session into EC2 instance