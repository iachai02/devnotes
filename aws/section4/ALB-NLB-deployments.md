# ALB and NLB Deployments

## ELB Deployments

- target groups define:
  - target type
  - target protocol/port
  - VPC
  - health checks
  - registered targets
- ELB listener defines:
  - listener protocol/port
  - routing rules
  - SSL/TLS certificate
- network mappings define:
  - availability zones
  - subnets
- ELB deploys nodes in each AZ it is mapped to

## ELB Supported Configurations

- Application load balance (ALB)
  - Target type can be:
    - instance
    - ip
    - lambda
  - target group protocol must be HTTP/HTTPS
  - health check protocol must be HTTP/HTTPS
  - can define rules for advanced request routing
- Network Load Balancer (NLB)
  - Target type can be:
    - instance
    - ip
    - alb
  - target group protocol must be TCP/UDP
  - any health check protocol is supported
  - can define elastic IP per subnet

## Routing with Application Load Balancer (ALB)

- target groups are used to route requests to registered targets
- A rule is configured on the listener. ALBs listen on HTTP/HTTPS
- Requests can be routed based on the path in the URL
- requests can also be routed based on the host field in the HTTP header
- targets can be EC2 instances, IP addresses, and Lambda functions

## Routing with Network Load Balancer (NLB)

- NLB nodes can have elastic IPs in each subnet
- NLBs listen on TCP, TLS, UDP or TCP_UDP
- a separate listener on a unique port is required for routing
- requests are routed based on IP protocol data
- targets can be EC2 instances, IP addresses, or ALBs
- targets can be outside a VPC (e.g. on-premises)

## What's the Source IP Address the App sees?

- CLB and ALB use private IP of their ENIs as source address
- AWS NLB:
  - if instance specified by instance ID
    - IP=A
  - if instance specified by IP address
    - IP=B
- Applicable to TCP and TLS - for UDP and TCP_UDP should be IP=A
- when using an NLB with a VPC Endpoint or AWS GA source IPs are private IPs of NLB nodes
- Note: X-forwarded-for can be used with ALB to capture client IPs
