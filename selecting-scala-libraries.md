---
updated: May 2022
---
# Selecting Scala libraries

Just as [Scala exists on a spectrum](scala-spectrum.md), so do the libraries that orbit it.

## The spectrum

Select libraries based on the following criteria, in ascending order of preference (worst is first).  General library selecting advice still applies. Go for libraries that are up-to-date, well-documented, and widely in-use.  Additionally, choose the library that makes the most sense for your team and requirements. No sense in choosing a highly functional library if your team does not have any experience with FP and isn't willing to block on learning upfront.

TODO pretty picture, ascending

### F-tier: Plain Java library

The weakest kind of library for Scala use is a plain old Java library, one that likely never thought of Scala as a potential consumer. These typically use mutable Java collections and nullable types.

If you are committed to using such a library, it would be worth making a thin Scala wrapper/interface around it so that the unpalatable parts of the Java ecosystem stay isolated and abstracted away from the core Scala logic.

Looks like:

- SBT library dependency does not use "Scala major version syntax" (since it is not compiled against a version of scala)
- Uses `null` and throws exceptions
- Methods with side-effects are unmarked

### C-tier: Libraries written in Scala

Better than a Java library is one that is written specifically for the Scala community to consume. Libraries like this will typically demonstrate many Scala best practices (but without `cats`). They may target specific versions of Scala but may also be cross-compiled to multiple versions.

Exposure to any underlying Java mechanisms should be minimal if any. Generally, the more generic the code, the more well-thought-out the framework is.

Looks like:

- Heavy use of core Scala types like `Option[_]` and collections like `List[_]`
- Can be added to SBT using "Scala major version syntax"

### A-tier: Libraries with `cats`

Libraries that require `cats` will interop with it in some way, typically by having new data structures and evidence for the typeclasses to go with them. Correctness with types will be among the top priorities 

Looks like:

- Highly generic code
- Clearly labeled `cats` typeclass support
- Clearly documents unsafe/unprincipled aspects of code
- Error channels are always encoded as data

### S-tier: Libraries with effect types

Libraries with side-effects will usually model them with something like `cats-effect` or `ZIO` or even both. Every potential action is safe unless marked `unsafe` otherwise. And resources are always well-scoped and cleaned up after use

Looks like:

- Specifies which effect framework it supports (or both)
- Correctly brackets resource usage

## Specific libraries

TODO
