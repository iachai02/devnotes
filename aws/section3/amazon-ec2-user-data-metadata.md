# Amazon EC2 User Data and Metadata

## Amazon EC2 Metadata

- Instance metadata is data about your EC2 instance
- Instance metadata is available at http://169.254.169.254/latest/meta-data

## IMDSv1 vs IMDSv2

- Instance Metadata Service (IMDS) comes in two versions:
  - IMDSv1: older and less secure
  - IMDSv2: newer, more secure, and requires a session token for authorization
  - default EC2 launch settings may disable IMDSv1

## Amazon EC2 User Data

- code is run when the instance starts for the first time (like running a script)
- Batch and PowerShell scripts can be run on Windows
- user data must be base64-encoded
- Encoding is automatic with the console and AWS CLI
- User data is limited to 16 KB, in raw form, before it is base64-encoded
- User data only runs the first time you launch your instance

## Amazon EC2 User Data via the AWS CLI

- user data is supplied by specifying the file
