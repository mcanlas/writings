---
updated: Nov 2022
---
# Publishing JARs into the GitHub Package Registry

- JARs produced by SBT projects can also be published to the `GitHub Package Registry`, which exists per repo
  - A plug-in like [`sbt-github-actions`](https://github.com/djspiewak/sbt-github-actions) is useful for streamlining the process with GHA
- A personal access token (`classic` flavor) is required FOR BOTH writing to AND reading from a registry
  - Create a personal access token (classic) from your account-wide settings
  - The token's package-level read/write settings apply to all repos :exploding_head:
  - Save the token as a GHA secret on to...
    - The repo that creates the JAR
    - As well as any repos that consume the JAR
    - And your local development environment
- SBT build settings will need to be configured to summon the token from the environment, to support both local development and GHA
