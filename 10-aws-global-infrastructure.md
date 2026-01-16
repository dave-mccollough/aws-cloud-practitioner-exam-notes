# AWS Global Infrastructure

## Why create a global application
- Deployed in Regions and/or Edge locations
- Decreased latency
- Disaster Recovery
- Global infrastructure is harder to attack
- AWS Services 
  - Global DNS
    - Route53
    - Route users to closest deployment
    - Good for disaster recovery
  - Global Content Delivery Network (CDN)
    - CloudFront
    - Replicates app to AWS edge locations - decreased latency
    - Cache common requests
  - S3 Transfer acceleration
    - Accelerate global uploads and downloads into S3
  - AWS Global Accelerator
    - Improve global application availabity and performance
  
  ## Route 53

  - Managed DNS Service
    - DNS is a collection of rules and records that help clients how to reach a server using a URL
    - Simple Routing Policy
      - No health checks
    - Weighted routing policy
      - Route a percentage of traffic to specific EC2 instances
      - Can use health checks 
    - Latency routing policy
      - Route traffic based on latency
    - Failover Routing policy
      - Route traffic based on heathcheck
        - If health checks fails on one EC2 instance, can route to another 

## CloudFront

- CDN 
- Improves read performance - Content cached at the edge
- Improves user experience
- 100 of points of presence - edge locations
- DDoS protection 
  - Integration with Shield and AWS Web Application Firewall
- CloudFront Origins
  - S3 Bucket
    - Distributing files and caching at the edge
    - Uploading files to S3 via CloudFront
    - Secured Origin Access Control
  - VPC 
    - For applications hosted in VPC private subnets
    - Application Load Balancer/Network Load Balancer/EC2 Instance
  - Custom Origin (HTTP)
    - S3 Website
    - Any public HTTP backend

- CloudFront vs S3 Cross Region Replication
  - CloudFront
    - Global Edge Network
    - Files are cached for a TTL
    - Great for static content that must be available everywhere
  - S3 Cross Region Replication
    - Must be setup for the region you want to replicate to
    - Files updated in near real time
    - Great for dynamic content that needs to be available at low latency in a few regions

## S3 Transfer Acceleration

- Increase transfer speed by transferring file to an AWS edge location which will forward data to an S3 bucket in the target region

## AWS Global Accelerator

- Improves global application availability and performance using AWS network
- Leverage the AWS network to optimize the route to your application
- 2 Anycast IPs are created for your application and traffic is sent through edge locations
- Edge locations send traffic to your app

- AWS Global Accelerator vs CloudFront
  - Both use AWS global network and edge locations
  - Both integrate with AWS shield for DDoS protection
  - CloudFront
    - Improves performance for cacheable content (images, videos, etc)
    - Content is served at the edge
  - Global Accelerator
    - No caching
      - Proxying packets at the edge
    - Improves performance for applications over TCP and UDP
    - Good for HTTP use cases that require static IPs
    - Good for HTTP use cases that required fast regional failover

## AWS Outpost

- AWS Hybrid Cloud
- AWS will setup and manage outpost racks
  - Outpost racks are server racks that offer the same AWS infrastructure as the cloud allowing you to leverage AWS services on prem
- You are responsible for the physical security of outpost racks
- Provides
  - Low latency
  - Local data processing
  - Data residency
  - Easier migration from on prem to cloud

## AWS WaveLength

- Brings AWS services to the edge of 5G networks
- Ultra low latency for applications using 5G networks
- Traffic doesn't leave service providers network
- No additional charges or service agreements
- Use cases
  - Smart cities
  - Connected vehicles
  - Real time gaming
  - ML assisted diagnostics

## AWS Local Zones

- Places AWS services closer to end users to run latency sensitive applications
- Extends VPC to more locations
- Example
  - AWS Region:  N. Virginia
  - AWS Local Zone: Boston, Chicago, Dallas, etc...

## Global Applications Architecture

- Single Region, Single AZ
  - NOT highly available
  - NO global latency
- Single Region, Multiple AZ
  - Highly available
  - NO global latency
- Multi Region, Active Passive
- Multi Region, Active Active
