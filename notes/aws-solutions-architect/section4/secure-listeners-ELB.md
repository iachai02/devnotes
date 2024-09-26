# Secure Listeners for ELB

## SSL/TLS Termination

- ACM certificate or certificate imported into ACM or IAM
- with a L7 ELB a new connection is established with the instance
- self-signed certificate can be used, or a certificate from a private certificate authority
- public certificate must be used if single encrypted encrypted
