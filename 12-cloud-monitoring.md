# Cloud Monitoring

## CloudWatch Metrics

- Provides metrics for every AWS service
- Allows you to create dashboards of metrics
- Important metrics
  - EC2
    - CPU utilization
    - Status checks
    - Network
  - EBS volumes
    - Disk read/writes
  - S3 Buckets
    - BucketSizeBytes
    - NumberOfObjects
    - AllRequests
  - Billing
    - Total Estimated Charge - Only in us-east-1
  - Service Limits
    - How much you have been using a service API

## CloudWatch Alarms

- Trigger notifications for any metric
  - Auto Scaling
  - EC2 Actions
  - SNS Notifications
- Can choose period and metric to evaluate alarm

## CloudWatch Logs

- Logs can be collected from
  - Elastic Beanstalk
  - ECS
  - AWS Lambda
  - CloudTrail
  - CloudWatch
  - Route 53
- Enables real time montoring of logs
- Adjustable CloudWatch Log retention
- Need to setup agent to push logs from EC2 instance to CloudWatch
- CloudWatch can be used on prem as well

## EventBridge

- Formerly CloudWatch Events
- Serverless service for event driven applications
- Schedule Cron jobs
- Event Pattern
  - Event rules react to a service doing something
  - Trigger Lambda function, send SQS/SNS messages


## CloudTrail

- Continuous logging for AWS account
- Provides governance, compliance and audit for AWS account
- Enabled by default
- Get a history of events/API calls within AWS account
- Can put logs from CloudTrail into CloudWatch or S3
- A trail can be applied to all regions or a single region

## X-Ray

- Visual analysis of application
- Benefits
  - Troubleshoot performance
  - Understand dependancies in microservice enviornment
  - Find service issues
  - Review requests
  - Check on SLA time

## CodeGuru

- ML powered service for automated code reviews and application performance recommendations
- 2 functions
  - CodeGuru Reviewer
    - Automated code reviews for static code analysis
  - CodeGuru Profiler
    - Provides recomendations about application performance during runtime

## AWS Health Dashboard 

- AWS Health Dashboard - Service History
  - Shows health of all services across all regions
  - Shows historical data for each day
  - Has RSS feed
- AWS Health Dashboard - Your Account
  - Alerts and remediation guidance when AWS is experiencing events that may impact you
  - Personalized view of performance and availability
  - Global Service