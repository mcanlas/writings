---
updated: Jan 2023
---
# Notes about DynamoDB

- DynamoDB tables in AWS are isolated, deployed artifacts; there is no "server" to collocate tables
- Tables have two primary key types:
  - Primary key only. Also known has hash key or partition key or hash attribute
    - Items with the same hashed key will be located together
    - Enables the retrieval of singular items by key
  - Composite primary key of partition key and sort key
    - Items with the same partition key will be located together, then sorted by sort (like a clustered index in MS SQL?)
    - Sort key also known as range attribute
    - Enables the retrieval of singular items by composite key
    - Enables the retrieval of multiple items in one partition, with an optional range query
