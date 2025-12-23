# Identity and Access Management (IAM)

## IAM Users and Groups

- IAM: Identity and Access Management
- Root account created by default. Should not be used or shared
- Users are people in org. 
- Groups contain users, but not other groups
- Users don't have to belong to a group 
- Users can belong to many groups

- Permissions
  - Users or groups can be assigned policies (JSON documents)
  - Policies define the user's permsissions
  - Follow principles of least privilege
  
  ## IAM Policy Structure

- IAM policies consist of:
  - Version: Policy lanaguage version
  - Id: Policy ID - Optional
  - Statements: One or more individual statements - Required
    - Statements include
    - Sid: Statement Identifier - Optional
    - Effect: Whether statement denies or allows access
    - Principal: Account, user, or role policy is applied to
    - Action: List of actions policy allows or denies
    - Resource list: Resource policy applies to
    - Conditions: When the policy is in effect
  ```
  {
    "Version": "2012-10-17",
    "Statement": [
    {
      "Sid": "ExampleStatementId",
      "Effect": "Allow",
      "Action": "s3:ListAllMyBuckets",
      "Resource": "*"
        }
    ]
  }

## MFA and Pasword Policy

- Use strong passwords
- AWS allows you setup a password policy
- Allow IAM uses to change their passwords
- Virtual device or physical device for MFA

## Access Keys, CLI and SDK

- Access keys are generated through the AWS console
- Users manage their own keys
- Access keys are secret
  - Access Key Id: Username
  - Access Key Secret: Password

- AWS CLI
  - Interact with AWS using command line interface (CLI)
  - Direct access to AWS APIs
  - Alternate to AWS Managment console
  - [Open Source](https://github.com/aws/aws-cli)

- AWS SDK
  - Language specific APIs
  - Access and manage AWS services programmatically

## AWS Cloud Shell

- CLI environment in AWS management console
- [Docs](https://docs.aws.amazon.com/cloudshell/)

## IAM Roles for Services

- Assign permissions to AWS services with IAM roles
- Common roles include
  - EC2 Instance Roles
  - Lambda function roles
  - Roles for cloud formation

## IAM Security Tools

- IAM Credentials Report
  - Account level
  - Lists all account users and status of their crendentials
- IAM Access Advisor
  - User level
  - Shows permissions granted to user and services were last used
  - Use info to revise policies

## Best Practices

- Only use root account for account setup
- One physical user = 1 AWS user
- Create strong password policy
- Use MFA
- Assign users to groups and permissions to groups
- Give resources roles
- Audit permissions of account


