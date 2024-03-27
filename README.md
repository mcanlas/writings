# writings

Opinionated writings about software engineering and [Scala](https://github.com/scala)

## Topics

* Software engineering
  * [Linting and formatting](linting-and-formatting.md)
  * Bikeshedding
  * Dogfooding
  * [Semantics over mechanics](semantics-over-mecahnics.md)
  * Testing
    * [Integration testing with Docker](integration-testing-with-docker.md)
* Data management
  * [Soft deletes](soft-deletes.md)
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
  * Mind types
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
  * [Best practices](scala-best-practices.md)
  * [What's up with Flink and AWS KDA?](scala-and-flink.md)
  * [Notable employees at Disney Streaming](disney-streaming.md)
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
  * [Code coverage](code-coverage.md)
* Git
  * What is rebasing?
  * [Repository conventions](repository-conventions.md)
* GitHub
  * [Publishing JARs into the Package Registry](github-package-registry.md)
  * [Testing GitHub Actions workflows](testing-gha-workflows.md)
* Infrastructure
  * [Structured onboarding](structured-onboarding.md)
* AWS
  * [AWS account architecture](aws-account-architecture.md)
  * [Notes about DynamoDB](dynamodb.md)
* Docker
* Rate-limiting of public resources

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
  - Queue for merge
    - Feels like overkill but makes more sense when team traffic/coordination/babysitting cost goes up
- Scala Steward/update bots
- IntelliJ
- DataGrip
- Gatling
- Terraform/IAC
- 1password enterprise
  - e.g. backoffice or artifactory creds, github tokens

## Work things
- internal conferences
- cross team guilds
- book club
- classes
- slack
  - YELLING channel
  - code rage (not at coworkers)
  - memes
  - per language
  - by office/geo
- meta managers
  - team directory (aws cost tagging)
  - service directory (aws cost tagging)
  - runtime wrapper (link to service directory)
    - logging, observability
  - IAC scale (terraform workspace wrapper)
- service api or data shape registries
  - code gen, artifact publishing
- artifactory
  - caching public artifacts
  - storing yours for internal sharing
