# Service Control Policies (SCP)

- SCPs control the maximum available permissions
- users in the management account are not restricted
- tag policy applied to enforce tag standardization
- dev users can only launch T2.micros instances
- prod users cannot launch any instance other than t2.micro (denied above)
- NOTE: SCPs do not grant ANY permissions, they control the AVAILABLE permissions
