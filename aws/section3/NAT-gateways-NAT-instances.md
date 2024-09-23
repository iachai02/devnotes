# NAT Gateways and NAT Instances Overview

## NAT Gateways

- the NAT gateway is created in the public subnet
- the NAT gateway ID must be specified in the private subnet RT
- managed by AWS
- cannot access through SSH

## NAT instances

- uses a special AMI with the string "amzn-ami-vpc-nat" in the name
- must disable source/destination checks
- the NAT instance ID must be specified in the private subnet RT
- managed by you
- can use as a bastian host
