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

## Enforcement

These approaches are not mutually exclusive

### On-demand

Pros:

- Developers have the most fine-grained control of when formatting happens
  - Could be early, could be late, could be in a formatting commit, could be implicitly done per working commit
  - Could be via IDE (format on save or format on demand) or via CLI

Cons:

- Developers must remember to do it
  - Forgetting to do it may be "costly" if you walk away from your continuous integration, expecting code to be tested when it is actually blocked by lack of compliance
- Paying for some cost of compilation per run

### Pre-commit hooks

Pros:

- Zero mental overhead, formatting will always happen
- Diff from formatting adherence more likely to be bundled with working commits (lessening the likelihood of "format only" commits)

Cons:

- Incurs some runtime overhead for every commit
  - May differ greatly on if the linter/formatter needs compilation to work properly

### Blocking before continuous integration

Continuous integration tools can be set up to merely check if code adheres to formatting rules and therefore block on further testing if this condition is not met

Pros:

- Forms an explicit, strictly enforced gate on the way to integrate code into the primary branch
- Offloads the cost of compiling and running formatters to CI nodes

Cons:

- Enforcement happens later in the development process
  - Many times, developers forget to format and then walk away from their automatic testing, only to find out that tests never ran

### Automatic commits

Pros:

- Zero mental overhead, everything is taken care of for you
- No local compilation cost, since formatters are never required to be run locally

Cons

- Requires continuous integration setup
- Requires a bot committer (or impersonating someone) with push access
- Developers must pull down changes made by the bot in order to push up subsequent changes
