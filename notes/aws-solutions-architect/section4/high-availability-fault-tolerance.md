# High Availability and Fault Tolerance

## High Availability

- Minimal service interruption
- Designed with no single point of failure (redundancy)
- uptime measured in %, e.g. 99.99%
- synchronous or asynchronous replication
- lower cost compared to FT
- services that create HA:
  - elastic load balancing
  - EC2 Auto Scaling
  - Amazon Route 53

## Fault Tolerance

- No service interruption
- specialized hardware with instantaneous failover
- no downtime
- synchronous replication
- higher cost compared to HA
- examples of FT:
  - fault tolerant NICs
  - disk mirroring (RAID 1)
  - synchronous DB replication
  - redundant power
- the system may fail if there is no built-in redundancy
- redundant components allow the system to continue to operate

## High Availability and Fault Tolerance

- Think of an availabilty zone as a separate data center
- Auto scaling launches a new web server

## Durability and Availability

- Durability:
  - durability is protection against:
    - data loss
    - data corruption
    - S3 offers 11 9s durability (99.999999999)
  - if you store 10 million objects in S3, then you can expect to lose one object every 10,000 years!
- Availability:
  - availability is a measurement of:
    - the amount of time the data is available to access
    - expressed as a percent of time per year
    - e.g. 99.99%
