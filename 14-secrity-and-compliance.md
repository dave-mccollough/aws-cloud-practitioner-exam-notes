# Security and Compliance

## Shared Responsibility Model

- AWS Responsibility
  - Security of the cloud
  - Protecting infrastructure
  - Managed Services
- Customer Responsibility
  - Security in the cloud
  - EC2
    - Guest OS including patching, updates, etc
  - Firewall and network configuration
  - IAM
  - Encrypting application data
- Shared Controls
  - Patch management
  - Configuration management
  - Training and Awareness

## DDoS Protection

- AWS Shield Standard
  - Protects against DDoS attack for websites and applications
  - No additional cost
  - Protects against SYN/UDP floods, reflection attacks and other layer 3/4 attacks
- AWS Shield Advanced
  - 24/7 premium DDoS protection
  - $3000 per month, per organization
  - Protects against more sophisticated attacks
- AWS WAF
  - Protects web apps from common exploits
  - Layer 7 (HTTP)
  - Deploy on Application Load Balancer, API, CloudFront
  - Filter requests based on rules
- CloudFront and Route 53
  - Availability protection using global edge network
  - Can combine with AWS shield for attack mitigation at the edge
- Scaling
  - AWS Auto Scaling

## AWS Network Firewall

- Protects entire VPC
- Covers layer 3 to layer 7
- You can inspect the following in any direction
  - VPC to VPC traffic
  - Outbound to internet traffic
  - Inbound from internet traffic
  - To/from Direct Connect and Site-to-Site VPN

## AWS Firewall Manager

- Manage security rules for all accounts in AWS organization
- Security policies
  - Common set of security rules
    - VPC Security Groups
    - WAF rules
    - AWS shield advanced
    - AWS network firewall
- Rules are applied to new resources are they are created across all accounts (current and future) in AWS organization

## Penetration Testing

- AWS customers can perform pentests against 8 services without prior approval from AWS
  - EC2 instances, NAT Gateways, and Elastic Load Balancers
  - RDS
  - CloudFront
  - Aurora
  - API Gateways
  - Lambda and Lambda Edge functions
  - Lightsail resources
  - Elastic Beanstalk environments
- Prohibited activities
  - DNS zone walking using Route 53 hosted zones
  - DDoS attacks
  - Port flooding
  - Protocol flooding
  - Request flooding
- Learn more [here](https://aws.amazon.com/security/penetration-testing/).

## Encryption

- AWS KMS 
  - Key Management System
  - Opt in services
    - EBS volumes
    - S3 Buckets
    - Redshift
    - RDS
    - EFS
  - Enabled by default
    - CloudTrail logs
    - S3 Glacier
  - Types of Keys
    - Customer Managed Keys
      - Customer manages keys, rotation policy, etc
      - May be able to 'bring your own key'
    - AWS Managed Keys
      - Created and managed by AWS
      - Used by most AWS services
    - AWS Owned Keys
      - Collection of keys AWS owns and manages to use in multiple accounts
    - CloudHSM Keys
      - Keys generated from CloudHSM device
- CloudHSM
  - Cloud Hardware Security Module
  - AWS provisions encryption hardware
  - Dedicated hardware
  - You manage encryption
  - HSM device is tamper resistant

## AWS Certificate Manager

- Provision, Manage and deploy SSL/TLS certs
- Used to provide inflight encryption (HTTPS)
- Supports public and private TLS certs
- Free of charge for public TLS certs
- Automatic TLS cert renewal
- Integrates with 
  - ELB
  - CloudFront
  - APIs on API Gateway

## AWS Secrets Manager

- Newer service meant for storing secrets
- Ability to force rotation of secrets every X days
- Automate generation of secrets using Lambda
- Integration with RDS
- Secrets are encrypted using KMS
- Mostly used for RDS ingegration

## AWS Artifact

- Provides customers with ondemand access to AWS compliance documentation and agreements
- Artifact Reports
  - Allows you to download AWS security and compliance documents
- Artifact Agreements
  - Review, track, and accept AWS agreements
- Used to support internal compliance

## Amazon GuardDuty

- Intelligent threat discovery
- Uses machine learning for anomoly detection 
- Input data includes
  - CloudTrail event logs
  - VPC flow logs
  - DNS logs

## Amazon Inspector

- Automated Security Assessments
- EC2
  - Uses AWS SSM Agent 
  - Unintended network accessibility
  - OS known vulnerabilities
- Container Images
  - Assess images as they are pushed
- Lambda Functions
  - Identifies software vulnerabilities in function code and packages
  - Assess functions as they are deployed
- Send findings to Event Bridge
- Reporting/integration in AWS Security Hub

## AWS Config

- Auditing and compliance of resources
- Records configuration changes over time
- Can store configuration data in S3
- Receive alerts for config changes (SNS)
- Per region service
- Can be aggregated across regions and accounts

## Amazon Macie

- Fully managed data security and data privacy service
- Used to identify and alert on sensitive data (PII)

## AWS Security Hub

- Manage security across multiple AWS accounts and automate security checks
- Aggregates alerts in pre-defined or personal findings formats
- Must enable AWS Config Service to use

## Amazon Detective

- Identifies the root cause of secuirity issues
- Uses machine learning
- Collects and processes events from CPC flow logs, CloudTrail, and GuardDuty

## AWS Abuse

- Report suspected AWS resources used for abusive or illegal purposes
- Includes
  - Spam
  - Port Scanning
  - DDoS attacks
  - Intrusion Attempts
  - Hosting objectional material
  - Distributing malware

## Root User Privileges

- Root user = Account owner
- Has complete access to all AWS services 
- Do not use Root account for everyday tasks

## IAM Access Analyzer

- Find out which services are shared externally
  - S3 Buckets
  - IAM roles
  - KMS keys
  - Lambda functions
  - SQS Queues
  - Secrets manager secrets
  - Define Zones of trust
  