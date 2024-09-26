# Amazon Elastic Load Balancing

- provides high availability and fault tolerance
- targets include:
  - amazon EC2 instances
  - amazon ECS containers
  - IP addresses
  - Lamda functions
  - other load balancers

## Types of Elastic Load Balancer (ELB)

- Application Load Balancer:
  - Operates at the request level
  - routes based on the content of the request (L7)
  - supports path-based routing, host-based routing, query string parameter-based routing, and source IP address-based routing
  - supports instances, IP addresses, Lambda functions and containers as targets
- Network load balancer:
  - oeprates at the connection level
  - routes connections based on IP protocol data (L4)
  - offers ultra high performance, low latency and TLS offloading at scale
  - can have a static IP/Elastic IP
  - supports UDP and static IP addresses as targets
- gateway load balancer:
  - used in front of virtual appliances such as firewalls, IDS/IPS, and deep packet inspection systems
  - operates at layer 3 - listens for all packets on all ports
  - forwards traffic to the TG specified in the listener rules
  - exchanges traffic with appliances using the GENEVE protocol on port 6081

## ELB Use cases

- Application Load Balancer
  - web applications with L7 routing (HTTP/HTTPS)
  - microservices architectures (e.g. Docker containers)
  - lambda targets
- Network Load Balancer
  - TCP and UDP based applications
  - ultra-low latency
  - static IP addresses
  - VPC endpoint services
- Gateway Load Balancer
  - Deploy, scale, and manage 3rd party virtual network appliances
  - centralized inspection and monitoring
  - firewalls, intrusion detection and prevention systems, and deep packet inspection systems
