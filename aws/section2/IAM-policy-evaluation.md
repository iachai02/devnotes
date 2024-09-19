# IAM Policy Evaluation

## Evaluation Logic

![evaluation logic](../imgs/evaluation-logic.png)

## Steps for Authorizing Requests to AWS

1. Authentication - AWS authenticates the principal that makes the request

- Request context:
  - Actions - the actions or operations the principal wants to perform
  - Resources - the AWS resource object upon which actions are performed
  - Principal - the user, role, federated user, or application that sent the request
