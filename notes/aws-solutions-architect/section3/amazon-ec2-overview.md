# Amazon EC2 Overview

## Amazon Elastic Compute Cloud (EC2)

- EC2 hosts are managed by AWS
- many instances run on each host server
- An EC2 instance is a virtual server
- a selection of instance types come with varying combinations of CPU, memory, storage, and networking
- EC2 instances run windows, linux, or macOS
- EC2 instances are attached to the network via an Elastic Network Interface (ENI)
- EC2 instances are launched in public or private subnets within an Amazon Virtual Private Cloud (VPC)

## Flexible and On-Demand

- Instances can be stopped when not needed and then started again
- can be terminated

## EC2 Instance Families & Types

- Instance families provide varying combinations of hardware resources
- larger sizes provide greater hardware capability
- example: m5.large
  - m is the family name
  - 5 is the generation number
  - large is the size of the instance

## Elastic Network Interfaces (ENIs)

- Instances in public subnets may have a private IP and a public IP
- instances in private subnets only have private IP addresses
- additional ENIs can be attached from subnets within the same AZ

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

## Network Interfaces (ENI, ENA, EFA)

- Elastic network interface
  - basic adapter type for when you don't have any high-performance requirements
  - can use with all instance types
- Elastic network adapter
  - enhanced networking performance
  - higher bandwidth and lower inter-instance latency
  - must choose supported instance type
- elastic fabric adapter
  - use with high performance computing and MPI and ML use cases
  - tightly coupled applications
  - can use with all instance types

## Amazon Elastic Block Store (EBS)

- EBS volumes exist within an Availability Zone
- The volume is attached over a network
- the volume is automatically replicated within the AZ

## Amazon EBS Volume Use Cases

- gp3 (general purpose SSD): most workloads, including databases and dev/test environments
- gp2 (general purpose SSD): boot volumes, dev/test, general workloads
- io2 (provisioned IOPS SSD): high-performance databases, critical applications
- io1 (provisioned IPOS SSD): databases requiring high IOPS
- st1 (throughput optiized HDD): streaming, big data, log processing
- sc1 (cold HDD): archival storage, infrequent access workloads

## Amazon EBS vs Instance Store

- EBS volumes are attached over the network
- instance store volumes are physically attaches to the host and offer high-performance
- instance store volumes are ephemeral (non-persistent)

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
