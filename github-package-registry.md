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

## Wonky IntelliJ support

Edit: It started working for me now, not sure why. But you can dump the environment as sbt loads.

```scala
sys.env.foreach(println)
```

It seems that IntelliJ has problems loading environment variables (where creds could be stored) from its instance of SBT.

- [JetBrains issue, unable to find creds](https://youtrack.jetbrains.com/issue/SCL-15375/IntelliJ-IDEA-unable-to-find-credentials-for-Artifactory)
- [JetBrains issue, can't read env](https://youtrack.jetbrains.com/issue/SCL-18821)

### June '23

Informal testing on a new laptop. If the Mac user account was logged in with the environment variable NOT in the profile, IntelliJ won't find it. Is it descending from some parent shell session and inhering those stale values? Updates to profile (which work for new terminal shells) will not reflect in IntelliJ launches until after logging off and back on again.
