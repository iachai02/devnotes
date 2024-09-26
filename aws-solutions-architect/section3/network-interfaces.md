# Network Interfaces (ENI, ENA, EFA)

- the primary network interface has a private IP and optionally a public IP
- additional ENIs can be attached from subnets within the same AZ
- you cannot attach ENIs from subnets in different AZs
- ENI (Elastic network interface)
  - basic adapter type for when you don't have any high-performance requirements
  - can use all instance types
- ENA (Elastic network adapter)
  - Enhanced networking performance
  - higher bandwidth and lower inter-instance latency
  - must choose supported instance type
- EFA (Elastic fabric adapter)
  - use with High Performance Computing and MPT and ML use cases
  - Tightly coupled applications
  - can use with all instance types
