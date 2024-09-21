# Access Keys and IAM Roles with EC2

## Using Access Keys with Amazon EC2

- IAM User (not as secure)
  - AWS CLI configured with access keys
  - the access key is associated with an IAM account
  - the access key will use the permissions assigned to the IAM user
- IAM Role (use this method)
  - credentials are not stored on the instance
  - The role is assumed by the EC2 instance
