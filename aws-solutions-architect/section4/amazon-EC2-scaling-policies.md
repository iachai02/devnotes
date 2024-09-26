# Amazon EC2 Scaling Policies

## Dynamic Scaling - Target Tracking

- Average CPU = 71.5%
- ASGAverageCPUUtilization = 60%
- Instance metrics are not counted until warm-up time has expired
- AWS recommend scaling on metrics with a 1-minute frequency

## Dynamic Scaling - Simple Scaling

- Alarm set to CPU >= 60%
- CPU = 70%
- launch 2 instances
- wait 300 seconds before allowing another scaling activity

## Dynamic Scaling - Step Scaling

- Alarm set to CPU >= 60%
- CPU = 70%
- Launch 2 instances
- CPU = 80%
- Alarm set to CPU >= 60%
- launch 4 instances

## Scheduled Scaling

- schedule set to scale daily at 08:45
- launch x instances
