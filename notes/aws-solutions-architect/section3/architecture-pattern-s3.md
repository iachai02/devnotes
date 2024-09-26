# Architecture Patterns - Amazon EC2

- requirement: company needs to run a short batch script to configure Amazon EC2 Linux instances after they are launched
  - solution: add the bash script to the user data of the EC2 instances
- requirement: a tightly coupled High Performance Computing (HPC) workload requires low-latency between nodes and optimimum network performance
  - solution: launch EC2 instances in a single AZ in a cluster placement group and use an Elastic Fabric Adapter (EFA)
- requirement: LoB application receives weekly bursts of traffic and must scale for short periods - need to most cost-effective solution
  - solution: use reserved instances for minimum required workload and then use Spot instances for the bursts in traffic
- requirement: a single instance application uses a static public IP address. In the event of failure, the address must be remapped to a failover instance
  - solution: attach an Elastic IP address to the EC2 instance. Remap the EIP in the event of a failure
- requirement: a fleet of amazon EC2 instances run in private subnets across multiple AZs. Company needs a redundant path to the internet
  - solution: deploy NAT gateways into multiple AZs and update route tables
- requirement: a team of engineers must administer EC2 instances in private subnets from remote locations using SSH
  - solution: deploy a bastion host in a public subnet and instruct the engineers to use the bastion host to "jump" to the instances in private subnets
- requirement: an application uses several EC2 instances. Architect must eliminate the risk of correlated hardware failures
  - solution: launch the instances in a spread placement group across distinct underlying hardware
- requirement: an application requires enhanced networking capabilities
  - solution: choose an instance type that supports enhanced networking and ensure the ENA module is installed and ENA support is enabled
- requirement: instance needs close to bare metal performance, EFA, and high performance networking
  - solution: use an AWS nitro instance type
