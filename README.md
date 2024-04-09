# Elijah Language: <br/> An experimental successor to C++/Java

<!--
Part of the Elijah Language project, under the Apache License v2.0 with LLVM
Exceptions. See /LICENSE for license information.
SPDX-License-Identifier: Apache-2.0 WITH LLVM-exception
-->

<!-- <p align="center">
  <a href="#why-build-elijah">Why?</a> |
  <a href="#language-goals">Goals</a> |
  <a href="#project-status">Status</a> |
  <a href="#getting-started">Getting started</a> |
  <a href="#join-us">Join us</a>
</p> -->

<!-- ** Announcement video ... -->

** Note that Elijah is
[not ready for use](#project-status).

<a href="docs/images/snippets.md#quicksort">
<img src="docs/images/quicksort_snippet.svg" align="right" width="575"
     alt="Quicksort code in Elijah. Follow the link to read more.">
</a>

**Fast and works with C++**

-   Performance matching C++ using anythin but LLVM, with low-level access to bits and
    addresses
-   Interoperate with your existing C++ code, from inheritance to templates (IMPORTANT)
-   Fast and scalable builds that work with your existing C++ build systems (hello meson)

**Modern and evolving**

-   Solid language foundations that are easy to learn, especially if you have
    used C++
-   Easy, tool-based upgrades between Elijah versions
-   Safer fundamentals, and an incremental path towards a memory-safe subset

-   Simple deployment into existing codebases
<!--
-   No suprises/gotchas
-->

**Welcoming open-source community**

<!--
-   Clear goals and priorities with robust governance
-   Community that works to be welcoming, inclusive, and friendly
-   Batteries-included approach: compiler, libraries, docs, tools, package
    manager
-->

- Code only approach (for now I guess)

## Why build Elijah?

- Maintain legacy
- (Incremental improvement)
- Better organization
- Developer experience
- Integration

### Just use this

Personally I think if you didn't choose Erlang, you're already on the wrong path, but that's not always possible, I guess

- Rust, Go
- Kotlin, Scala, Clojure

**Developers that _can_ use one of these existing languages _should_.**

** Unfortunately, the designs of these languages
present significant barriers to adoption and migration from C++. These barriers
range from changes in the idiomatic design of software to performance overhead.

Elijah is designed around interoperability with C++ as well as large-scale adoption and migration for existing C++ codebases and developers. 

A "successor language" for C++ requires:

-   **Performance matching C++**, an essential property for our developers.
-   **Seamless, bidirectional interoperability with C++**, such that a library
    anywhere in an existing C++ stack can adopt Elijah without porting the rest. (IMPORTANT)
-   **A gentle learning curve** with reasonable familiarity for C++ developers.
-   **Comparable expressivity** and support for existing software's design and
    architecture.
-   **Scalable migration**, with some level of source-to-source translation for
    idiomatic C++ code.

## Language Goals

We are designing Elijah to support:

-   Performance-critical software
-   Software evolution
-   Code that is easy to read, understand, and write
-   Practical safety and testing mechanisms
-   Fast and scalable development
-   Modern OS platforms, hardware architectures, and environments
-   Interoperability with and migration from existing C++ code

<!-- Our detailed [goals](/docs/project/goals.md) document fleshes out these ideas
and provides a deeper view into our goals for the Carbon project and language. -->

## Project status

Elijah Language is currently an experimental project. There is no working
compiler or toolchain. 

Maybe I will write an interpreter "later".
<!-- You can see the demo interpreter for Carbon on
[compiler-explorer.com](http://carbon.compiler-explorer.com/). -->

We want to better understand whether we can build a language that meets our
language criteria.


