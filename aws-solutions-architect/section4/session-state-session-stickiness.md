# Session State and Session Stickiness

## Storing Session State

- session data such as authentication details stored in DynamoDB Table
- session data retrieved from DynamoDB Table
- user does not need to re-authenticate
- ElastiCache is also a popular solution for storing session-state data

## Sticky Sessions

- Cookie is generated and client bound to instance for the cookie lifetime
- session data such as authentication details stored locally
- client is directed to another instance
- if an instance fails, session state is lost - use with session state store for more resiliency
