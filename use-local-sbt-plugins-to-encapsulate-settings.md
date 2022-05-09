---
updated: May 2022
---
# Use local SBT plugins to encapsulate settings

SBT plugins come in two major varieties. The first type is external (generally third-party) plugins included in the `plugins.sbt` file. The second type is plugins locally defined within the project that uses them.

Use locally defined plugins to encapsulate build settings in SBT projects.

## Mechanics

As with all SBT plugins, the loading of a plugin provides an opportunity to inject settings that are shared across projects. In the example below, settings for Scala 3 are automatically injected, making this plugin require zero configuration other than its existence in the repository.

```scala
// in project/Scala3Plugin.scala
import sbt.Keys._
import sbt._

/**
object Scala3Plugin extends AutoPlugin {

  override def trigger: PluginTrigger =
    AllRequirements

  override val buildSettings: Seq[Setting[_]] = Seq(
    scalaVersion := "3.1.2",
    scalacOptions ++= Seq("-indent", "-rewrite")
  )
}
```

## See also

- [Official SBT documentation about creating plugins](https://www.scala-sbt.org/1.x/docs/Plugins.html)
