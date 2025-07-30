# Exam Cram

## AWS organizations

- AWS organizations allows you to consolidate multiple AWS accounts into an organization that you create and centrally manage
- available in two feature sets:
  - consoidated billing
  - all features
- includes root accounts and organizational units
- policies are applied to root accounts or OUs
- consolidated billing includes:
  - paying account - independent and cannot access resources of other accounts
  - linked acount - all linked accounts are independent

## Consolidated billing

- single payment method for all the AWS accounts in the Organization
- combined view of charges incurred by all your accounts
- pricing benefits from aggregated usage
- limit of 20 linked accounts for consolidated billing (default)
- can help with cost control through volume discounts
- unused reserved EC2 instances are applied across the group
- paying accounts should be used for billing purposes only

## Service Control Policies

- manage the maximum available permissions
- must have all features enabled in organization
- can be applied to accounts or OUs
- policies can be assigned at different points in the hierarchy
- SCPs affect only IAM users and roles - not resources policies
- SCPs affect the root account in member accounts
- SCPs do not affect any action performed by the management account
- deny list strategy:
  - uses the FullAWSAccess SCP
  - attached to every OU and account
  - overrides the implicit deny
  - explicitly allows all permissions to flow down from the root
  - create additional SCPs to explicitly deny permissions
