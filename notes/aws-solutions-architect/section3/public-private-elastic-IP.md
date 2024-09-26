# Public, Private and Elastic IP Addresses

- a public IP address is a dynamic address
- an elastic IP address is a static address
- both ENIs and EIPs can be remapped to a different instance
- EIPs can be remapped across AZs
- public IP address
  - lost when the instance is stopped
  - used in public subnets
  - no charge
  - associated with a private IP address on the instance
  - cannot be moved between instances
- private IP address
  - retained when the instance is stopped
  - used in public and private subnets
- elastic IP address
  - static public IP address
  - you are charged if not used
  - associated with a private IP address on the instance
  - can be moved between instances and elastic network adapters
