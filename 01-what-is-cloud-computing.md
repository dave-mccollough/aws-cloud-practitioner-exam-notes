# What is Cloud Computing

## Traditional IT Overview
- Network Terminology
- Network
    - Cables, routers and servers connected with each other
- Router
    - Networking device that forwards packets between computer networks
- Switch
    - Sends packets to correct server or client

- Problens with traditional IT
- Pay for data center
    - Rent, cooling, power, maintenance
- Adding, upgrading and maintaining hardware takes time
- Time and cost intensive to scale
- Teams to monitor data center and infrastructure
- Disaster planning and recovery

## What is cloud computing

- On demand delivery of compute, database, storage, and other IT resources
  - Pay as you go pricing model
  - Provision the exact resoures you need
  - Access as many resources as you need almost instantly
  - Provides a simple way to manage compute, servers, databases, etc
  - [Link](https://aws.amazon.com/what-is-cloud-computing/)

- 6 Advantages of Cloud Computing
  - Trade fixed expense for variable expense
  - Benefit from massive economies of scale
  - Stop guessing capacity
  - Increase speed and agility
  - Stop spending money running and maintaining data centers
  - Go global in minutes 
  - [Link](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/six-advantages-of-cloud-computing.html)

- Cloud Deployment Methods
  - Private Cloud
    - Cloud resources not exposed to the public 
    - Great for data residency or unique security needs
  - Public Cloud
    - Cloud resources provided by a third-party (AWS, Azure, GCP)
    - Delivered over the internet
    - 6 Advantages of Cloud Computing
  - Hybrid Cloud
    - Some servers are managed on prem, some capabilites are extended to the cloud
    - Provide control over infrastructure
    - Flexibility

- 5 Characteristics of Cloud Computing
  - On demand service
  - Broad network access
  - Multi-tenancy and resource pooling
  - Rapid elasticity and scalability
  - Measured service

- Problems solved by the cloud
  - Flexibility
  - Cost effectiveness
  - Scalability
  - Elasticity
  - High Availability and Fault Tolerance
  - Agility

## Types of Cloud Computing

- IaaS
  - Infrastructure as a Service
  - Provides networking, servers and data storage
  - Highest level of flexability
  - Closest comparison to on-prem IT
  - AWS example
    - EC2

- PaaS
  - Platform as a Service
  - Don't need to manage underlying infrastructure
  - Focus on deployment and management of applications
  - AWS example
    - Elastic Beanstalk

- SaaS
  - Software as a Service
  - Product that is managed by service provider
  - AWS example
    - Rekognition (Machine learning)

- Pricing
  - Pay for compute time
  - Pay for storage
  - Pay for data egress
    - Ingress is free

## AWS Services

- Regions
  - Naming: `us-east-1`, `eu-west-3`, etc
  - Made of of multiple data centers
  - Most AWS services are scoped to a region
  - How to choose a region
    - Proximity to customers
    - Data governance or compliance concerns
    - Available services
    - Pricing

- Availability Zones (AZ)
  - Each region is made up of 3-6 AZs
  - Naming: `ap-southeast-2a`, `ap-southeast-2b`, etc.
  - Each AZ has one or more data centers with redundant power, networking and connectivity
  - Geographically seperated from each other so they are isolated from disasters
  - Connected via high bandwidth, ultra low latency networking

- Points of presence (Edge locations)
  - 400+ points of presence
    - 400+ edge locations
    - 10+ regional caches
  - Allows content to be delivered to users with lower latency

- Global Services
  - IAM
  - Route53 (DNS)
  - Cloudfront (CDN)
  - WAF 
- Most AWS services are region scoped
  - EC2
  - Elastic Beanstalk
  - Lambda
  - Etc...

## Shared Responsibility Model

- [Link](https://aws.amazon.com/compliance/shared-responsibility-model/)
- AWS Responsible for the security of the cloud
  - Compute
  - Storage
  - Database
  - Networking
  - Regions
  - AZ
  - Edge Locations
- Customer responsible for security in the cloud
  - Customer data
  - Platform, apps, identty and access management
  - Operating system, network and firewall configuration
  - Data encryption, server side encryption, networking traffic

## Acceptable Use Policy

- [Link](https://aws.amazon.com/aup/)
- No harmfull or offensive use of content
- No security violations
- No network abuse
- No email or message abuse