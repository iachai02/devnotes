# Amazon EC2 Auto Scaling

- automatically launches and terminates instances
- maintain availability and scale opacity
- works with EC2, ECS, and EKS
- integrates with many AWS services, including:
  - CloudWatch for monitoring and scaling
  - Elastic Load Balancing for distributing connections
  - Amazon VPC for deploying instances across AZs

1. Automatic Scaling
   - auto scaling launches an extra instance
   - metric reports CPU > 80%
2. Maintain scalability
   - ASG replaces failed instance
   - CloudWatch notifies Auto Scaling

- scaling is horizontal (scales out)
- provides elasticity and scalability
- responds to EC2 status checks and CloudWatch metrics
- can scale based on demand (performance) or on a schedule
- scaling policies define how to respond to changes in demand
- health checks
  - EC2 = EC2 status checks
  - ELB = Uses the ELB health checks in addition to EC2 status checks
- health check grace period
  - how long to wait before checking the health status of the instance
  - auto scaling does not act on health checks until grace period expires
- types of auto scaling:
  - manual - make changes to ASG size manually
  - dynamic - automatically scales based on demand
  - predictive - uses machine learning to predict
  - scheduled - scales based on schedule

## Configuration of an Auto Scaling Group

- launch template specifices the EC2 instance configuration
- launch configurations are replaced by launch templates and have fewer features
