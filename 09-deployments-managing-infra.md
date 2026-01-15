# Deployments and Managing Infrastructure

## CloudFormation

- Cloudformation is a declarative way to define AWS infrastructure for any resources that are supported.

## CDK(AWS Cloud Development Kit)

- Define cloud infrastructure using a familiar language
- Code is compiled into CloudFormation templates (JSON/YAML)
- Deploy application and infrastructure code at the same time

## AWS Elastic Beanstalk

- AWS Platform as a Service offering
- Managed service
- Developer manages code
- Three architecture models
  - Single instance deployment - for dev
  - LB and ASG - production and pre-production web apps
  - ASG only - non webapps in production (service workers)

## CodeDeploy

- Automatically deploys application
  - Works with EC2
  - Works with on-prem
  - Hybrid Service
- Servers/Instances must be configured ahead of deployment with the CodeDeploy agent

## AWS CodeCommit

- AWS GitHub alternative
- Fully managed by AWS
- Scalable and Highly available
- Private, secure and integrated with AWS
- Code changes are automatically versioned

## CodeBuild

- Code building service in the cloud
- Compiles source code, runs tests and produces packages that are ready to be deployed (by CodeDeploy)
- Fully managed
- Continously scalable
- Secure
- Pay as you go pricing

## AWS CodePipeline

- Orchestrate tests to have code pushed to production
  - Code > Build > Test > Provision > Deploy
- CI/CD 

## AWS CodeArtifact

- Artifact management solution
- Devs and CodeBuild retrieve dependancies from CodeArtifact

## AWS Systems Manager (SSM)

- Helps manager your EC2 and on-prem systems at scale
- Hybrid service
- Get insights about state of infrastructure
- Includes 10+ products
  - Patching automation for enhanced compliance
  - Fleet server maintainance
  - Parameter configuration
- Works for Linux, Windows, MacOS and Raspberry PI OS

