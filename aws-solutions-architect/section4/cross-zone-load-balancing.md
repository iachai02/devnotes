# Cross-Zone Load Balancing

- When cross-zone load balancing is enabled:
  - each load balancer node distributes traffic across the registered targets in all enabled Availability Zones
- When cross-zone load balancing is disabled:
  - each load balancer node distributes traffic only across the registered targets in its Availability Zone
  - with application load balancers, cross-zone load balancing is always enabled
  - with network load balancers and gateway load balancers, cross-zone load balancing is disabled by default

## Cross-Zone Load Balancing - Disabled

- if cross-zone load balancing is disabled:
  - each of the three targets in Availability Zone A receives 16.6% of the traffic
  - each of the two targets in availability zone B receives 25% of the traffic

## Cross-Zone Load Balancing - Enabled

- If cross-zone load balancing is enabled:
  - each of the five targets receives 20% of the traffic
