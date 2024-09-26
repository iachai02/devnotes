# Scaling Up vs. Scaling Out

## Stateful and Stateless Applications

- Stateless: person checks a weather website
  - no state recorded about the user's session
- stateful: person browsing amazon
  - amazon stores information about activity
- no data is stored on the web server, it is stateless
- when the user purchases, the application layer process the order and records the data in the database. This is stateful
- the cart items are stored in cookies on the computer

## Scalability and Elasticity: Scaling Up

- scaling up means adding resources to the server

## Scalability and Elasticity: Scaling Out

- add more instances of that particular application

## Scaling up vs out

- scaling up: going from a t2.micro, 1 vCPU, 1 GB RAM to c5.xlarge, 4 vCPU, 8 GB RAM
- scaling out: adding additional instances of t2.micro, 1 vCPU, 1 GB RAM

## Which scaling model should be used?

- EC2 with MySQL DB -> Scale UP
- EC2 with static website -> Scale OUT
