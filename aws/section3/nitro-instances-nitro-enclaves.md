# Nitro Instances and Nitro Enclaves

## AWS Nitro System

- Nitro is the underlying platform for the next generation of EC2 instances
- support for many virtualized and bare metal instance types
- breaks functions into specialized hardware with a Nitro Hypervisor
- specialized hardware includes:
  - nitro cards for VPC
  - nitro cards for EBS
  - nitro for instance storage
  - nitro card controller
  - nitro security chip
  - nitro hypervisor
  - nitro enclaves
- improves performance, security, and innovation:
  - performance close to bare metal for virtualized instances
  - elastic network adapter and elastic fabric adapter
  - more bare metal instance types
  - high network performance (e.g. 100 gbps)
  - high performance computing (HPC) optimizations
  - dense storage instances (e.g. 60 TBs)

## AWS Nitro Enclaves

- isolated compute environments
- runs on isolated and hardened virtual machines
- no persistent storage, interactive access, or external networking
- uses cryptographic attestation to ensure only authorized code is running
- intergrates with AWS Key Management Service (KMS)
- protect and securely process highly sensitive data:
  - personally identifiable information (PII)
  - Healthcare data
  - Financial data
  - Intellectual property data
