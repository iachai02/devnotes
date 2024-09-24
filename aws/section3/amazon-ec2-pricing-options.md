# Amazon EC2 Pricing Options

- On-demand
  - standard rate: no discount; no commitments; dev/test, short-term, or unpredictable workloads
- Reserved
  - 1 or 3-year commitment; up to 75% discount; steady-state, predictable workloads and reserved capacity
- Spot instances
  - Get discounts of up to 90% for unused capacity. Can be terminated at any time
- Dedicated Instances
  - Physical isolation at the host hardware level from instances belonging to other customers; pay per instance
- Dedicated hosts
  - physical server dedicated for your use; Socket/core visibility, host affinity; pay per host; workloads with server-bound software licenses
- Savings plans
  - commitment to a consistent amount of usage (EC2 + Fargate + Lambda); Pay by $/hour; 1 or 3-year commitment

## Amazon EC2 Billing

- Billed per second; minimum charge of 1 minute
  - per-second billing is for Amazon, Linux, Windows, and Ubuntu in On-demand, Reserved, and Spot forms
- Billed per hour; minimum charge of 1 hour
  - commercial linux distros such as Red Hat El and SUSE ES use hourly pricing
- Volumes billed per second; minimum of 1 minute

## Amazon EC2 Reserved Instances (RIs)

- term is 1 or 3 years
  - standard RI: change AZ, instance size (Linux), networking type
    - use ModifyReservedInstances API
  - Convertible RI: change AZ, instance size (Linux), networking type
    - change family, OS, tenancy, payment option
    - Use ExchangedReservedInstances API
  - can pay all upfront, partial upfront, no upfront
- when the attributes of a used instance match the attributes of an RI the discount is applied
- tenancy: default or dedicated
- Availability zone:
  - reserves capacity in specified AZ
- Region:
  - does not reserve capacity; discount applies to all AZ

## Amazon EC2 On-Demand Capacity Reservations

- reserve compute capacity for your Amazon EC2 instances in a specific Availability Zone
- any duration can be specified
- mitigates against the risk of being unable to get on-demand capacity
- does not require any term commitments and can be cancelled at any time
  - the availability zone in which to reserve the capacity
  - the number of instances for which to reserve capacity
  - the instance attributes, including the instance type, tenancy, and platform/OS

## AWS Savings Plans

- Computes Saving Plan: 1 or 3-year; hourly commitment to usage of Fargate, Lambda, and EC2; Any Region, family, size, tenancy, and OS
- EC2 Savings Plan: 1 or 3-year; hourly commitment to usage of EC2 within a selected Region and Instance Family; Any size, tenancy and OS

## Amazon EC2 Spot Instances

- spot instance: one or more EC2 instances
- spot fleet: launches and maintains the number of spot/on-demand instances to meet specified target opacity
- EC2 fleet: launches and maintains specified number of spot/on-demand/reserved instances in a single API call
- can define separate OD/Spot capacity targets, spot price, instance types, and AZs
- 2-minute warning if AWS need to reclaim capacity - available via instance metadata and CloudWatch Events

## Spot Block

- Requirement: uninterrupted for 1-6 hours
- solution: spot block
- pricing is 30%-45% less than On-Demand
