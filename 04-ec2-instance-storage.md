# EC2 Instance Storage

## EBS Overview

- EBS (Elastic Block Storage)
- What is an EBS Volume
  - Network drive you attach to instance while they run
  - Allows instances to persist data after termination
  - Can only be mounted to one instance at a time
  - Bound to a specifc AZ
    - Network USB device

- EBS Volume
  - Network drive 
  - Uses network to communicate with instance which may cause latency
  - Can be detached and reattached to another EC2 instance
  - Locked to AZ
    - To move volume to another AZ, you need to snapshot it
  - Billed for provisioned capacity
  - Can be deleted on instance termination

## EBS Snapshots

- Make a point in time backup (snapshot) of your EBS volume at any point in time
- Not necessary to detach, but recommended
- Snapshots can be copied across region or AZ

## AMI

- Amazon Machine Image
- Can configure your own software, configuration, operating system, etc 
  - Faster boot and configuration time because software is pre-packaged
- Built for a specifc region, but can be copied across regions
- EC2 instances can be launched from 
  - Public AMI - Amazon provided
  - Your own AMI
  - AWS Marketplace AMI
- Process to create an AMI
  - Start and configure EC2 instance
  - Stop the instance
  - Build the AMI - this will create EBS snapshots as well

## EC2 Image Builder

- Used to automate the creation of virtual machines or container images
- Can be run on a schedule
- Free service - only pay for underlying infrastructure

## EC2 Instance Store

- If you need high performance hardware disk, use EC2 instance store
- Better I/O performance than EBS
- Ephemeral 
- Good for buffer, temporary content, cache
- Risk of data loss if hardware files
- Backups/replication are your responsibility

## EFS Overview

- Elastic File System
- Managed network file system
- Can be mounted to 100s of EC2 instances
- Works with Linux EC2 instances in multi-az
- Highly scalable and available
- Expensive - Pay per use with no capacity planning

- EFS Infrequent Access (EFS-IA)
  - Storage class optimized for files not accessed frequently
  - Up to 92% cheaper than EFS Standard
  - EFS will automatically move files to EFS-IA based on last time they were accessed
    - Lifecycle policy
  - Transparent to apps accessing EFS

## Amazon FSx

- Fully managed Windows native shared file system
- Built on Windows file server
- Supports SMB and NTFS
- Can be integrated with Entra ID
- Can be accessed from AWS or on-prem infrastructure

- Amazon FSx for Lustre
  - High performance scalable file storage High performance compute
  - Name derived from Linux and Cluster
  - Use for machine learning, analytics, video processing