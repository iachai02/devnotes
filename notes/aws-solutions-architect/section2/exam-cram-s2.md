# Exam Cram Section 2

## AWS Identity and Access Management (AWS IAM)

- IAM is used to securely control individual and group access to AWS resources
- IAM makes it easy to provide multiple users secure access to AWS resources
- IAM can be used to manage:
  - users
  - groups
  - access policies
  - roles
  - user credentials
  - user password policies
  - multi-factor authentication (MFA)
  - API keys for programmatic access (CLI)
- by default, new users are created with NO access to any AWS services - they can only login to the AWS console
- permissions must be explicitly granted to allow a user to access an AWS service
- IAM users are individuals who have been granted access to an AWS account
- IAM is universal (global) and does not apply to regions
- IAM is eventually consistent
- Authentication methods:
  - console password - use to login to AWS Management Console
  - access keys - used for programmatic access
  - server certificates - uses SSL/TLS certificates
- IAM Users
  - an IAM user is an entity that represents a person or service
  - by default, users cannot access anything in your account
  - root user credentials are the email address used to create the account and a password
  - the root account has full administrative permissions, and these cannot be restricted
  - IAM users can be created to represent applications, and these are known as "service accounts"
  - you can have up to 5000 users per AWS account
- IAM Groups
  - groups are collections of users and have policies attached to them
  - a group is not an identity and cannot be identified as a principal in an IAM policy
  - use groups to assign permissions to users
  - use the principal of least privilege when assigning permissions
  - you cannot nest groups (groups within groups)
- IAM Roles
  - Roles are created and then "assumed" by trusted entities
  - With IAM roles you can delegate permissions to resources for users and services
  - IAM users or AWS services can assume a role to obtain temporary security credentials
  - temporary security credentials are issued by the AWS Security Token Service (STS)
- IAM Policies
  - Policies are documents that define permissions and can be applied to users, groups, and roles
  - policy documents are written in JSON (key value pair that consists of an attribute and a value)
  - all permissions are implicitly denied by default
  - the most restrictive policy is applied

## Types of IAM Policy

- Identity-based policies - attached to users, groups, or roles
- Resource-based policies - attached to a resource; define permissions for a principal accessing the resource
- IAM permissions boundaries - set the maximum permissions an identity-based policy can grant an IAM entity
- AWS Organizations service control policies (SCP) - specify the maximum permissions for an organization or OU
- Session policies - used with AssumeRole\* API actions

## AWS IAM Best Practices

- lock away your AWS account root user access keys
- create individual IAM users
- user groups to assign permissions to IAM users
- grant least privilege
- get started using permissions with AWS managed policies
- use customer managed policies instead of inline policies
- use access levels to review IAM permissions
- configure a strong password policy for your users
- enable MFA
- use roles for applications that run on Amazon EC2 instances
- use roles to delegate permissions
- do not share access key8s
- rotate credentials regularly
- remove uneccessary credentials
- use policy conditions for extra security
- monitor activity in your AWS account
