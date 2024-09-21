# Amazon EC2 Overview

## Amazon Elastic Compute Cloud (EC2)

- EC2 hosts are managed by AWS
- An EC2 instance is a virtual server
- a selection of instance types come with varying combinations of CPU, memory, storage, and networking
- EC2 instances run windows, linux, or macOS

## Public, Private, and Elastic IP addresses

- Type:
  - Public IP address:
    - Lost when the instance is stopped
    - used in public subnets
    - no charge
    - associated with a private IP address on the instance
    - cannot be moved between instances
  - Private IP address:
    - retained when the instance is stopped
    - used in public and private subnets
  - Elastic IP address:
    - static public IP address
    - you are charged if not used
    - associated with a private IP address on the instance
    - can be moved between instances and Elastic Network Adapters

## Public Subnets

- VPC surrounding Availability Zone with a public and private subnet
- public and private subnets have different route tables

## Launching an EC2 Instance

- EC2 instance -> select an instance type
- EC2 instance -> select an amazon machine image (AMI) <-> EBS snapshot
- select an amazon machine image (AMI) -> linux or windows -> customized AMI
- An AMI defines the configuration of the instance
- the instance type defines the hardware profile (and cost)
- a snapshot is a point-in-time backup of an instance
- you can customize your instance and create a custom AMI
