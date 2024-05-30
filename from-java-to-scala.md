---
updated: May 2024
---
# From Java to Scala

A collection of topics and anti-patterns most commonly found by Java engineers transitioning to Scala and functional programming

## Null

For methods or APIs to signal the potential absence of a value, the proper type to use is `Option[_]`. `null` should not exist in any pure Scala code.

## Primitive types

What is referred to in Java as "primitive types" is analogous to built-in "value types" in Scala. Other than for very specific high-performance scenarios, no attention is called to whether something is "boxed" or "primitive".

For example, using the Java type `Integer` (or any other Java primitive types within Scala code) would be a mistake when the preferred value type is `Int`

## Recursion

Recursion comes up frequently in the Scala learning process, but isn't at all required for day-to-day coding. In fact, most, if not all, cases of recursion can be replaced with more straight-forward folds or traversals.

In the rare case that recursion is required, prefer tail recursion when possible.
