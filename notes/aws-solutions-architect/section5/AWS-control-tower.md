# AWS Control Tower

- A landing zone is a well-architected multi-account baseline
- preventive guardrails disallow API actions using SCPs
- detective guardrails are used for governance and compliance
- directory source can be IAM identity Center, SAML 2.0 IdP, or Microsoft AD

## AWS Control Tower - Shared Accounts

- Management account - The AWS account used to launch AWS control tower. The root user and IAM administrator have full access to all resources in the landing zone
- Log archive account - contains a central amazon s3 bucket for storing a copy of all AWS CloudTrail and AWS Config log files for all other accounts in the landing zone
- Audit account - aggregates and stores logs collected from all other accounts in the landing zone. Secure account with restricted access

## AWS Control Tower - Guardrails

- Preventive guardrails
  - purpose: preventive guardrails are designed to proactively prevent policy violations before they occur. They enforce compliance and security best practices by restricting certain actions or configurations.
  - how they work: these guardrails are implemented using AWS Service Control Policies (SCPs). They effectively limit what actions uses and roles can perform in the AWS accounts within the organization
  - examples:
    - disallow deletion of CloudTrail Logs and S3 Logging Buckets
    - disallow public read access to S3 Buckets
    - require encryption on EBS Volumes
    - disallow RDP/SSH Access from 0.0.0.0/0
- Detective Guardrails
  - purpose: detective guardrails are designed to monitor and report on policy violations or non-compliant activities that have already occurred. They help in identifying misconfigurations or activities that do not adhere to the organization's policies
  - how they work: these guardrails are implemented using AWS Confit rules and Lambda functions. They continuously evaluate the configuration of AWS resources and gneerate alerts or reports when non-compliance is detected
  - Examples:
    - detecting publicly accessible Amazon S3 buckets
    - detect whether versioning is enabled for Amazon S3 buckets
    - detect whether encryption is enabled for Amazon RDS instances
    - monitoring for IAM policies that grant overly broad permissions

## AWS Organizations vs Control Tower

- AWS organizations
  - manage multiple accounts
  - consolidated billing
  - organizational units
  - service control policies
  - tag policies
  - backup policies
- AWS Control tower
  - extends capabilities of AWS Organizations
  - landing zones (best practices)
  - federated access (IAM Identity Center)
  - centralized logging
  - account factory (automation)
  - guardrails (governance rules)
