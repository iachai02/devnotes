# Architecture Patterns - Auto Scaling and ELB

- Requirement: High Availability and elastic scalability for web servers
  - Solution: Use amazone EC2 Auto Scaling and an Application Load Balancer across multiple AZs
- Requirement: Low-latency connections over UDP to a pool of instances running a gaming application
  - Solution: Use a network load balancer with a UDP listener
- Requirement: Clients need to whitelist static IP addresses for a highly available load balanced application in an AWS Region
  - Solution: Use an NLB and create static IP addresses in each AZ
- Requirement: Application on EC2 in an Auto Scaling group requires disaster recovery across Regions
  - Solution: Create an ASG in a second region with the capacity set to 0. Take snapshots and copy them across Regions (Lambda or DLM)
- Requirement: Application on EC2 must scale in larger increments if a big increase in traffic occurs, compared to small increases in traffic
  - Solution: Use Auto Scaling with a step scaling policy and configure a larger capacity increase
- Requirement: Need to scale EC2 instances behind an ALB based on the number of requests completed by each instance
  - Solution: Configure a target tracking policy using the ALBRequestCountPerTarget metric
- Requirement: Application runs on EC2 behind an ALB. Once authenticated users should not need to reauthenticate if an instance fails
  - Solution: Use session state store such as DynamoDB or ElastiCache
- Requirement: company is deploying an IDS/IPS system using virtual appliances and needs to scale horizontally
  - Solution: Deploy a Gateway Load Balancer in front of the virtual appliances
