# IAM Best Practices

- require human users to use federation with an identity provider to access AWS using temporary credentials
- require workloads to use temporary credentials with IAM roles to access AWS
- require multi-factor authentication (MFA)
- rotate access keys regularly for use cases that require long-term credentials
- safeguard your root user credentials and don't use them for everyday tasks
- apply least-privilege permissions
- get started with AWS managed policies and move toward least-privilege permissions
- Use IAM Access Analyzer to generate least-privilege policies based on access activity
- regularly review and remove unused users, roles, permissions, policies, and credentials
- use conditions in IAM policies to further restrict access
- verify public and cross-account access to resources with IAM Access Analyzer
- use IAM Access Analyzer to validate your IAM policies to ensure secure and functional permissions
- establish permissions guardrails across multiple accounts
- use permission boundaries to delegate permissions management within an account
