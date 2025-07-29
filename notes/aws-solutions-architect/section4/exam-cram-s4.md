# Exam Cram

## Amazon EC2 Auto Scaling

- EC2 auto scaling launches and terminates instances dynamically
- scaling is horizontal (scales out)
- provides elasticity and scalability
- responds to EC2 status checks and CloudWatch metrics
- can scale based on demand (performance) or on a schedule
- scaling policies define how to respond to changes in demand
- auto scaling groups define collections of EC2 instances that are scaled and managed together
- health checks
  - EC2 = EC2 status checks
  - ELB = uses the ELB health checks in addition to EC2 status checks
- health check grace period
  - how long to wait before checking the health status of the instance
  - auto scaling does not act on health checks until grace period expires

## Auto Scaling - Monitoring

- group metrics (ASG)
  - data points about the Auto Scaling group
  - 1 minute granularity
  - no change
  - must be enabled
- basic monitoring (instances)
  - 5-minute granularity
  - no charge
- detailed monitoring (instances)
  - 1 minute granularity
  - charges apply

## Additional Scaling Settings

- cooldowns - used with simple scaling policy to prevent Auto Scaling from launching or terminating before effects of previous activities are visible. Default value is 300 seconds (5 minutes)
- termination policy - controls which instances to terminate first when a scale-in event occurs
- termination protection - prevents auto scaling from terminating protected instances
- standby state - used to put an instance in the InService state into the Standby state, update or troubleshoot the instance
- lifecycle hooks - used to perform custom actions by pausing instances as the ASG launces or terminates them
- use case:
  - run a script to download and install software after launching
  - pause an instance to process data before a scale-in (termination)

## Elastic Load Balancing

- Distributes incoming application traffic across multiple targets including:
  - Amazon EC2 instances
  - Containers
  - IP addresses
  - Lambda functions
- Provides fault tolerance for applications
- Distributes incoming traffic a single AZ or multiple AZs
- only 1 subnet per AZ can be enabled for each ELB
- ensure at least a /27 subnet and make sure there are at least 8 IP addresses available for the ELB to scale
- ELBs can be Internet facing or internal-only
- Internet facing ELB:
  - ELB nodes have public IPs
  - Routes traffic to the private IP addresses of the EC2 instances
  - Need one public subnet in each AZ where the ELB is defined
- Internal only ELB:
  - ELB nodes have private IPs
  - Routes traffic to the private IP addresses of the EC2 instances

## ELB Use Cases

- Application Load Balancer
  - Web applications with L7 routing (HTTP/HTTPS)
  - Microservices architectures (e.g. Docker containers)
  - Lambda targets
- Network Load Balancer
  - TCP and UDP based applications
  - Ultra-low latency
  - static IP addresses
  - VPC endpoint services
- Gateway Load Balancer
  - Layer 3
  - Listens for all IP packets across all ports
  - GLB and virtual applicances exchange applicaiton traffic using the GENEVE protocol on port 6081
  - Use with virtual appliances such as:
    - Firewalls
    - intrusion detection systems (IDS)
    - Intrusion prevention systems (IPS)
    - Deep packet inspection systems (DPI)

## Cross-Zone Load Balancing

- When cross-zone load balancing is enabled:
  - Each load balancer node distributes traffic across the registered targets in all enabled Availability Zones
- When cross-zone load balancing is disabled:
  - Each load balancer node distributes traffic only across the registered targets in its Availability Zone
  - With Application Load Balancers, cross-zone load balancing is always enabled
  - with network load balancers and gateway load balancers, cross-zone load balancing is disabled by default
