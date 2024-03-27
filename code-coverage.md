---
updated: March 2024
---
# Code coverage

A common method of enhancing unit tests is to measure what paths of code are exercised by using "code coverage" tools.

## Scoverage

The most common way with Scala projects is to use [an SBT plugin for scoverage](https://github.com/scoverage/sbt-scoverage) 

### Caveats

- When using the sbt command `coverage` (or `coverageOn`), consider it "mutable" for any subsequent steps that may require compilation, since the code is now instrumented with coverage tracking.
- Be sure to `clean` the build environment when attempting to assemble or publish a project, to assert that all instrumented code is removed
- Consider NOT using code coverage when doing integration style tests over (locally) published artifacts or Docker images; they should not be instrumented.
  - Code that is [mistakenly instrumented](https://github.com/scoverage/sbt-scoverage/issues/306) may result in a `FileNotFoundException`, in the code's attempt to look for instrumentation resources
