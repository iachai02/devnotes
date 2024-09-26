# Permissions Boundaries

- Ex: Joannne is in developers policy which allows full control of S3, CloudWatch, EC2, and IAM and a permissions boundary which sets the maximum permissions that the entity can have
  - permissions boundaries are attached to users and roles
  - even though on the developers policy she has control of IAM, on the permissions boundaries it doesn't show IAM permissions so Joanne doesn't actually have control over IAM
  - she can't create an IAM account because the permissions boundary does not allow it

## Privilege Escalation

- Ex: Lindsay has IAMFullAccess which means she is assigned permissions to AWS IAM only and cannot launch AWS resources. She creates an IAM user called X-User and assigns AdministratorAccess permissions. She can log in to the X-user account and gain full privileges to the AWS account.
- not a good thing

## Preventing Privilege Escalation

- Ex: Linday has IAMFullAccess, but instead adds permissions boundary which ensures that users created by Lindsay have the same or fewer permissions. She then does the same thing, but because of the permissions boundary, her new IAM account does not have more permissions than her.
