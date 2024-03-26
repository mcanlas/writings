---
updated: March 2024
---
# Structured onboarding

(this isn't a standardized term)

Often with infrastructure in the cloud and enterprise spaces, certain patterns may merge. Statements like "all microservices should use this specific library" or "all lambds should emit these business metrics" might ring true. In these cases, the fundamental building blocks of the business is one abstraction higher than the primitive blocks themselves. AWS CDK refers to this concept as "constructs" where each construct is one to many with the underlying CloudFormation resources they compile to.

And similarly to resource and effect management, certain business processes may have to be done before a new construct is created as well as when an existing construct is retired. We can refer to this as "onboarding" and "deboarding". For example, teams may need to audit their permissions and run calculations about total cost of ownership before constructing new tables. So a new table isn't "just" a new table in the cloud but a higher level construct with a well articulated onboarding process and potentially a deboarding process.
