# EC2 Placement Groups

- Cluster: packs instances close together inside an Availability Zone. This strategy enables workloads to achieve the low-latency network performance necessary for tightly-coupled node-to-node communication that is typical of HPC applications
- Partition: spreads your instances across logical partitions such that groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions. This strategy is typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka
- Spread: strictly placess a small group of instances across distinct underlying hardware to reduce correlated failures

## Cluster Placement Group

- Uses enhanced networking, low network latency and high throughput for inter-instance traffic
  - when trying to communicate, can use extremely low latency

## Partition Placement Group

- On separate underlying hardware
- each partition is located on a separate AWS rack
- Partitions can be in multiple AZs (up to 7 per AZ)

## Spread Placement Group

- Each instance is located on a separate AWS rack

## EC2 Placement Group Use Cases

- Tightly-coupled application that requires low-latency, high throughput network traffic between instances
  - use cluster placement group
- Distributed and replicated NoSQL database; requires separate hardware for node groups
  - use partition placement group
- small number of critical instance that should be kept separate from each other
  - use spread placement group
