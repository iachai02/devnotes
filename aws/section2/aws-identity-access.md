# AWS Identity and Access Management (IAM)

- IAM Principals must be authenticated to send requests (with a few exceptions)
- A principal is a person or application that can make a request for an action or operation on an AWS resource
- AWS determines whether to authorize the request (allow/deny)
- Core components of IAM
  - User: user gains permissions applied to the group through the policy
  - User groups: used to add users and applying policies
  - Roles: roles are used for delegation and are assumed
  - Policies: used to determines what users are allowed to do, attaching to the user groups if there are more than one policies
    - identity based policies can be applied to users, groups, and roles
    - define the permissions for the identities or resources they are associated with

## IAM Users

- the root user has full permissions
- best practice to not use root user + enable MFA (Multi-factor authentication)
- email used for sign up
- AWS IAM
  - up to 5000 individual user accounts can be created. Users have no permissions by default
  - has an amazon resource name
    - ex: arn:aws:iam:: 625148252389
- Authentication via username/password for console of access keys for API/CLI

## IAM User Groups

- helps from a management perspective
- 3 groups
  - admin group
  - development group
  - operations group
- some users might be in multiple groups
- main reason to use groups is to apply permissions to users using policies
- user gains the permissions applied to the group through the policy

## IAM Authentication Methods

- user -> username and password (mfa token optional) -> AWS IAM account -> AWS management console
  - the user is authenticated and can perform operations in the console
- Command line interface/API -> access key ID and Secret access key -> AWS IAM account -> AWS API
  - access keys are used for programmatic access

## Root User vs IAM User

- Root user
  - login: email address
  - permissions: full-unrestricted
- IAM user
  - login: friendly name: John or AWS account ID or Alias
  - permissions: IAM Permissions policy
