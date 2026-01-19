# Account Management

## Organizations Overview

- Global service
- Manage multiple AWS accounts
- Main account is the master account
- Consolidated billing across all accounts
- Restrict privilidges using Service Control Policies
- Multi account strategies
  - Create accounts per department, cost center or dev/test/prod
  - Use tagging for billing
  - Enable cloudtrail on all accounts and send to central S3 account
  - Send cloudwatch logs to central logging account
- Service Control Policies (SCP)
  - Whitelist or blacklist IAM actions
  - Applied at OU or account level
  - Does not apply to master account
  - Applies to all users and roles
  - Must have explicit ALLOW
    - Does not allow anything by default

## AWS Control Tower

- Govern multi-account AWS environment
- Runs on top of AWS organizations
- Benefits
  - Automate enviornment setup and policy management
  - Detect policy violations
  - Monitor compliance

## AWS Resource Access Manager (RAM)

- Share resources you own with other AWS accounts
- Share any account within your organization
- Avoid resource duplication

## AWS Service Catalog

- Self service portal to launch resources pre-defined by admins
- Includes VMs, Databases, Storage, etc

## AWS Pricing Models

- Free Tier
- Pay as you go/on demand pricing
- Spot instance pricing
- Reserved instance pricing
- Savings Plan pricing
- Dedicated host pricing

## AWS Compute Optimizer

- Helps choose optimal configurations and resources based on workload
- Uses machine learning and cloudwatch utilization logs 
- Recommendations can be exported to S3

## Billing and Cost Tools

- Estimating costs 
  - Pricing Calculator
- Tracking Costs
  - Billing dashboard
  - Cost allocation tags
  - Cost and usage reports
  - Cost explorer
- Monitoring
  - Billing alarms
  - Budgets

## AWS Cost Anamoly Detection

- Continously monitor cost and usage to detect unusual spends
- Sends you report with root cause analysis

## AWS Service Quotas

- Notifies when you're close to a service quota threshold

## AWS Trusted Advisor

- High level AWS account assessment
- Provides recommendations on six catagories
  - Cost optimization
  - Performance
  - Security
  - Fault tolerance
  - Service limits
  - Operational Excellence

## Support Plans

- Basic Support Plan
  - 24x7 access to cuetomer support
  - AWS Trusted advisor access
  - AWS Personal Health Dashboard access
- Developer Support Plan
  - All items in Basic Support
  - Business hours access to cloud support individuals
  - Unlimited cases/contacts
  - Response times
    - General support < 24 business hours
    - Systems issues < 12 business hours
- Business Support Plan
  - Intended for use with production workloads
  - Full Trusted Advisor access
  - 24x7 access to Cloud Engineers via phone, email, chat 
  - Unlimited cases/contacts
  - Response times
    - General support < 24 business hours
    - Systems issues < 12 business hours
    - Prod system issues < 4 hours
    - Prod down <1 hour
- Enterprise Onramp Support plan
  - Production or business critical workloads
  - Includes Business support plan items
  - Accces to technical account managers (TAM)
  - Concierge support team access for billing and account best practices
  - Infra event managment
  - Response times
    - General support < 24 business hours
    - Systems issues < 12 business hours
    - Prod system issues < 4 hours
    - Prod down <1 hour
    - Business critical system down < 30 minutes
- Enterprise support plan
  - Business critical workloads
  - Includes all of Enterprise onramp
  - Response times
    - General support < 24 business hours
    - Systems issues < 12 business hours
    - Prod system issues < 4 hours
    - Prod down < 1 hour
    - Business critical system down < 15 minutes
