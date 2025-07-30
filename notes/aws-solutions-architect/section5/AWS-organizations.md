# AWS Organizations

- AWS organizations allows you to consolidate multiple AWS accounts into an organization that you create an centrally manage
- available in two feature sets:
  - consolidated billing
  - all features
- includes root accounts and organizational units
- policies are applied to root accounts or OUs
- consolidated billing includes:
  - paying account - independent and cannot access resources of other accounts
  - linked accounts - all linked accounts are independent
- you can group accounts into Organizational Units (OUs)
- Service Control Policies (SCPs) can control tagging and the available API actions
- create accounts programmatically using the Organizations API
- enable AWS SSO using on-prem directory
- receive a consoidated bill
- enable CloudTrail in management account and apply to members
