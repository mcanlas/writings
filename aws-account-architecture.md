---
updated: March 2024
---
# AWS account architecture

## Account per environment

One pattern I've seen twice now is having one AWS per deployment environment. So if you have three deployment environments (`dev`, `qa`, and `prod`) you would also have three different AWS account IDs. This allows for separation of resources. You can run tests and load tests in one environment without disrupting the other.

Two potential downsides to this are

- A. Data parity. In environments where features are very sensitive to the data that is present, the non-production layers may not have the same data or data-generating traffic that `prod` has. So accurate testing may be limited.
- B. Cross-environment interaction. There are some cases where synchronizing data across environments may be useful. But this option may be tougher than usual since the separate accounts need to have their access bridged to one another. But obviously you want the bridging to be done in a controlled way as to maintain the overall hygienic split between environments.

## Account per team

One pattern I think I've seen recommended but never used is to have accounts per developer and accounts per team. This is a logical extension of the "accounts per environment" pattern, and may be useful as the footprint on AWS begins to approach global account limits.

One downside is that interactions between different teams and their accounts needs to be more carefully orchestrated.

## See also

- AWS account limits
