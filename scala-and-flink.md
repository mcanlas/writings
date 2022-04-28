---
updated: May 2022
---

# What's up with Scala and Flink and AWS KDA?

## Apache Flink

Flink is written mostly in Java, but has Scala parts. The latest supported Scala version is 2.12.

Flink as a cluster runtime used to force users to a specific Scala version. As of [the newly released Flink 1.15](https://github.com/apache/flink/releases/tag/release-1.15.0), this is no longer the case. On a cluster with Flink 1.15 installed, you can call the Java parts of Flink using any version of Scala.

## AWS Kinesis Data Analytics (KDA)

AWS's runtime for Flink runs Flink 1.13 and therefore limits users to Scala 2.12.

## Further reading

- [Scala Free in One Fifteen](https://flink.apache.org/2022/02/22/scala-free.html)
- [Amazon Kinesis Data Analytics now supports Apache Flink v1.13](https://aws.amazon.com/about-aws/whats-new/2021/10/amazon-kinesis-data-analytics-apache-flink-version-1-13/)

## Thanks

Thanks to coworker Nick Burkard for providing the above guidance.
