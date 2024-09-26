# Exam Cram

## Amazon EC2

- with amazon EC2 you launch virtual server instances on the AWS cloud
- each virtual server is known as an "instance"
- with EC2 you have full control at the operating system layer
- key pairs are used to securely connect to EC2 instances
- storage is either Amazon EBS (persistent) or Instance Store (non-persistent)
- An Amazon Machine Image (AMI) provides the information required to launch an instance
- An AMI includes:
  - a template of the root volume for the instance
  - launch permissions
  - a block device mapping specifying the volumes to attach
- AMIs are regional. You can only launch an AMI from the region in which it is stored
- you can copy AMI's to other regions using the console, command line, or the API
- instance metadata is data about your instance that you can use to configure or manage the running instance
- user data is data that is supplied by the user at instance launch in the form of a script

## Benefits of Amazon EC2

- Elastic computing: easily launch hundreds to thousands of EC2 instances within minutes
- complete control: you control the EC2 instances with full root/administrative access
- flexible: choice of instance types, operating systems, and software packages
- reliable: EC2 offers very high levels of availability and instances can be rapidly commissioned and replaced
- secure: fully integrated with Amazon VPC and security features

## EC2 Placement Groups

- Cluster: pack instances close together inside an availability zone. This strategy enables workloads to achieve the low-latency network performance necessary for tightly-coupled node-to-node communication that is typical of HPC applications
- partition: spreads your instances across logical partitions such that groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions. This strategy is typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka
- spread: strictly places a small group of instances across distinct underlying hardware to reduce correlated failures

## EC2 Instance Lifecycle

- Stopping EC2 instances
  - EBS backed instances only
  - no charge for stopped instances
  - EBS volumes remain attached (chargeable)
  - Data in RAM is lost
  - instance is migrated to a different host
  - private IPv4 addresses and IPv6 addresses retained; public IPv4 addresses released
  - associated elastic IPs retained
- hibernating EC2 instances
  - applies to on-demand or reserved Linux instances
  - contents of RAM saved to EBS volume
  - must be enabled for hibernation when launched
  - specific prerequisites apply
  - when started (after hibernation):
    - EBS root volume is restored to its previous state
    - RAM contents are reloaded
    - the processes that were previously running on the instance are resumed
    - previously attached data volumes are reattached and the instance retains its instance ID
- rebooting EC2 instances
  - equivalent to an OS reboot
  - DNS name and all IPv4 and IPv6 addresses retained
  - does not affect billing
- retiring EC2 instances
  - instances may be retired if AWS detects irreparable failure of the underlying hardware that hosts the instance
  - when an instance reaches its scheduled retirement date, it is stopped or terminated by AWS
- terminating EC2 instances
  - deleting EC2 instance
  - cannot recover a terminated instance
  - by default root EBS volumes are deleted
- recovering EC2 instances
  - CloudWatch can be used to monitor system status checks and recover instance if needed
  - applies if the instance becomes impaired due to underlying hardware/platform issues
  - recovered instance is identical to original instance

## AWS Nitro System

- Nitro is the underlying platform for the next generation of EC2 instances
- breaks logical functions into specialized hardware with a Nitro Hypervisor
- Specialized hardware includes:
  - Nitro cards for VPC
  - Nitro cards for EBS
  - Nitro for instance storage
  - Nitro card controller
  - Nitro security chip
  - Nitro hypervisor
  - Nitro enclaves
- Improves performance, security, and innovation:
  - Performance close to bare metal for virtualized instances
  - Elastic Network Adapter and Elastic Fabric Adapter
  - More bare metal instance types
  - higher network performance (e.g. 100 Gbps)
  - high performance computing (HPC) optimizations
  - dense storage instances (e.g. 60TB)

## AWS Nitro Enclaves

- isolated compute environments
- runs on isolated and hardened virtual machines
- no persistent storage, interactive access, or external networking
- use cryptographic attestation to ensure only authorized code is running
- integrates with AWS Key Management Service
- protect and securely process highly sensitive data:
  - personally identifiable information (PII)
  - healthcare data
  - financial data
  - intellectual property data
