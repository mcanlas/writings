---
updated: May 2022
---
# Differences between Scala and Java

Scala and Java are both JVM languages but have a lot of syntactical and cultural differences. Here is a short list of some of them (without getting too deeply into functional programming).

## How to read type signatures

In Scala (and functional programming), types and the signatures of functions are foundational. When reading a type like "this function requires `A`" or "this function returns `A`", both imply that `A` is never null. Code written by and for the Scala ecosystem operates with this assumption.

## Generic types

In Java, generic types usually start at `T`. In Scala, generic types start at `A`.

Generic types that have some semantic value still use their preferred letters (e.g. `K` for map key, `V` for map value, `F` for functor, etc).

## Type annotations and type inference

Java has supported local type inference since Java 10. Scala code makes heavy use of type inference for local and private code.

## Null

Never use `null`. Always use `Option` or a stronger error type.

## Reassignment

In Java, variables can have their values assigned again after initialization. In Scala, this is nominally supported with `var` declarations, but is highly discouraged. Use `val` and immutable workflows instead.

## Collections and mutability

Scala has its own set of collections. Use of Java collections is highly discouraged.

Scala collections come in two flavors: mutable and immutable. Always use the immutable ones (until you have a specific reason not to).

Because the collections are immutable, they will always return new copies of data when using their methods. When Scala programmers casually mention "updating" a collection, they still mean returning new, immutable copies.

## Throwing/catching exceptions

Exceptions are primarily used for two different use-cases: managing control flow and communicating exceptional/rare behavior. Many types exist in Scala that can handle control flow, such as `Option`, `Try`, and `Either`. Rare edge cases continue to use exceptions, but only if they are truly extraordinary, as in "my JVM is dying" (rare), but not "illegal argument" (not rare).

Additionally, exceptions are not checked, in favor of using code that is has no exceptions (e.g. is functionally pure).

## Interfaces

They're called `trait`s in Scala.

## Static methods

What would be static class methods in Java are methods on a `companion object` in Scala.

## Enums

Java has a first-class `enum` mechanism. Scala `2.x` also has an `Enumeration` mechanism, but almost no one should be using this. In practice, the entire domain of enums is supplanted by `algebraic data types` or ADTs. When a Scala programmer casually says "enum", they mean ADTs.

Scala 3 has an `enum` keyword. This is fine to use, since it is syntactic sugar for ADTs.

## Builder pattern/improper construction

To whatever extent possible, Scala programmers try to make the idea of "improperly constructed" instances impossible. DSLs that use a builder-style pattern will either demand requirements with static typing or start from an already valid empty/default value.

## Regarding interop with Java

Occasionally, Scala code will be written that needs to interface directly with Java components. That code may break some conventions listed above, but will likely be hidden behind a well-defined interface.
