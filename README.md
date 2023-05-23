# writings

Opinionated writings about software engineering and [Scala](https://github.com/scala)

## Topics

* Software engineering
  * [Linting and formatting](linting-and-formatting.md)
  * Bikeshedding
  * Dogfooding
  * [Semantics over mechanics](semantics-over-mecahnics.md)
* Object-oriented programming
  * Static vs OOP as a matter of currying
  * Dispatch
* Functional programming
  * What is functional programming?
  * Why functional programming?
    * Consistency
  * `map` as a springboard for FP
  * As the conclusion of good OOP
  * What is a kind?
    * By analogy
  * Typeclass guide
      * Just the superclass layout
  * Big data type classes
  * What is a functor?
  * What is a monad?
  * Error stories
    * Error accumulation
    * First one wins
* Scala
  * Why Scala?
    * Gateway
    * See above
  * Syntactic sugar for Java
    * How does `apply` work?
    * How do symbolic operators work?
  * [Scala's OOP/FP spectrum](scala-spectrum.md)
    * Moving target, always improving
  * [Differences with Java](scala-differences-with-java.md)
  * Type signature conventions
    * Walled garden
    * Typescript
  * Recursion is overrated
  * Brace hate
  * Collections tour
    * Mutable vs immutable
    * Common types
    * Common methods
  * [Selecting Scala libraries](selecting-scala-libraries.md)
    * Java vs Scala vs `cats`
  * Should I wrap a Java library?
  * Maintainable style
    * As a function of the team
  * Implicits
  * Scala 2 vs Scala 3
  * Scala 2 versions
  * Modeling
    * Service vs data class
    * Pure vs side-effect traits
    * Function side (simple vs `F`)
  * A roadmap for learning
  * What are ADTs?
    * As a form of dispatch
  * Pipelining
    * `.pipe`, F#, `mouse`
  * Pattern matching
    * On values/strings is an anti-pattern
  * Stronger F-types and ADT exhaustion prevent under-encoding
  * Combinators reduce the surface area for typos/bugs
    * Not my problem (just like `F`, map)
  * Type inference
    * Enhancements to Java, C, C#
    * Least upper bounds
    * Limitations
  * Type parameter annotations
    * Covriance
    * Contravariance
  * What is `ammonite`?
  * Notable people
  * [What's up with Flink and AWS KDA?](scala-and-flink.md)
* [`cats`](https://github.com/typelevel/cats)
  * Learning `cats` after `cats-effect`
  * IO vs `F`
  * `cats-effect` vs `zio`
  * How `syntax` works
  * `map` vs `fmap`
  * Vanilla reasons
    * `NonEmptyList`
    * Postfix `.some`
* SBT
  * Composable SBT files
    * [Use local plugins to encapsulate settings](use-local-sbt-plugins-to-encapsulate-settings.md)
  * [Annotate your plugins](annotate-your-sbt-plugins.md)
* Git
  * What is rebasing?
  * [Repository conventions](repository-conventions.md)
* GitHub
  * [Publishing JARs into the Package Registry](github-package-registry.md)
  * [Testing GitHub Actions workflows](testing-gha-workflows.md)
* AWS
  * [Notes about DynamoDB](dynamodb.md)

## General concepts

- Syntactic sugar
- Linting
- Dependency injection
- Attention is finite
  - Visual distractions
- Dangerous things should look obnoxious
- Things that are the same should look the same
- Things that are different should look different
- Identity vs mechanics
- Agile is like communism
- Static vs dynamic typing
- Conflation
- Everything is a queue
- Just iterate
  - Comparing the cost of prevention before the cost of change
- Isomorphism
- Agency problem
- Externalities
- Market problems
- Null was a mistake

## Great tools
- Tableau
- Postman for REST APIs
- Mergify
- Scala Steward/update bots
