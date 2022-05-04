---
updated: May 2022
---
# Annotate your SBT plug-ins

## Problem

SBT plugins files (`plugins.sbt`) are frequently managed as a write-only dumping ground, leading to unused plugins as the project evolves. This is an under-articulation of [semantics over mechanics](semantics-over-mecahnics.md).

Example:

```scala
addSbtPlugin("org.scalameta" % "sbt-scalafmt" % "2.4.6")
addSbtPlugin("ch.epfl.scala" % "sbt-scalafix" % "0.10.0")
addSbtPlugin("io.github.davidgregory084" % "sbt-tpolecat" % "0.3.1")
```

## Solution

Annotate each plugin with a comment, describing its reason for existence. When the reason is no longer true or relevant, then the plugin can safely be removed.

```scala
// for automatic formatting
addSbtPlugin("org.scalameta" % "sbt-scalafmt" % "2.4.6")

// for automatic linting
addSbtPlugin("ch.epfl.scala" % "sbt-scalafix" % "0.10.0")

// for best practices compiler flags
addSbtPlugin("io.github.davidgregory084" % "sbt-tpolecat" % "0.3.1")
```

