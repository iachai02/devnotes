# Architecture Patterns

- Example 1:
  - Requirement: a select group of users only should be allowed to change their IAM passwords
  - Solution: create a group for the users and apply a permissions policy that grants the iam:ChangePassword API permissions
- Example 2:
  - Requirement: an amazon EC2 instance must be delegated with permissions to an Amazon DynamoDB table
  - Solution: Create a role and assign a permissions policy to the role that grants access to the database service
- Example 3:
  - Requirement: a company has created their first AWS account. They need to assign permissions to users based on job function
  - Solution: Use AWS managed policies that are aligned with common job functions
- Example 4:
  - Requirement: a solutions architect needs to restrict access to an AWS service based on the source IP address of the requester
  - Solution: Create an IAM permissions policy and use the Condition element to control access based on source IP address
- Example 5:
  - Requirement: a developer needs to make programmatic API calls from the AWS CLI
  - Solution: Instruct the developer to create a set of access keys and use those for programmatic access
- Example 6:
  - Requirement: A group of users require full access to all Amazon EC2 API actions
  - Solution: Create a permissions policy that uses a wildcard for the Action element relating to EC2
