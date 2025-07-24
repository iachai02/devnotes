# System Design Notes

- One server and one database will not scale as user base grows
  - SOLUTION: distributed system
    - network of independent computers working as one coherent system
  - Key characteristics:
    - Scalability: systems ability to handle growing commands
      - Horizontal scaling: adding more servers
      - Vertical scaling: upgrading existing hardwares
    - Reliability: reliable system continues to function correctly even when components fail
    - Availability: percentage of time a system remains operational
    - Efficiency: measured by latency which is the delay in getting the first response and throughput which is the number of operations per time unit
- Balancing the trade-offs in distributed systems between scalability and consistency
- Distributed systems face inherent limitations
  - CAP theorem
