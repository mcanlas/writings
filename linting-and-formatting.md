---
updated: May 2022
---
# Linting and formatting

## TL;DR

Use linters and code formatters.

## Background

As code bases and their teams grow, so does the surface area for two problems: adherence to best practices and consistent formatting. Both can be addressed in code review, but this can become tedious at scale. Also, code reviews can get bogged down by long discussions about superficial things like formatting (see "bikeshedding"). One potential solution is to address both of these problems using automatic tooling.

## Pros

- Relieves code reviews and pull requests of the noisy discussions around conventions
- Makes issues of formatting less personal and more team-centric
- Programmatic analysis of code scales infinitely (regardless of the size of the codebase and the number of codebases)

## Cons

- Places the burden of adherence onto the commit author, early in the process 
- For edge cases where a certain deviation in formatting is more clear
  - Will require some sort of "turn off automatic formatting here" mode
  - Or cannot be done (i.e. the formatter will reformat, leaving you with something suboptimal)

## What's the difference between linting and formatting?

## Why is it called "linting"?

There used to be a tool called `lint` for `C` that was used to catch small errors, in the same way a lint trap catches small fibers in a dryer.

## Static analysis

- Regular expressions
