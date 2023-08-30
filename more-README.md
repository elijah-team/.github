


### TODO

-   Critical and foundational aspects of the language design informed by our
    experience with C++ and the most difficult challenges we anticipate. This
    includes designs for:
    -   Generics
    -   Class types
    -   Inheritance
    -   Operator overloading
    -   Lexical and syntactic structure
    -   Code organization and modular structure
-   A prototype interpreter demo that can both run isolated examples and gives a
    detailed analysis of the specific semantic model and abstract machine of
    Elijah. We call this the [Elijah Explorer](/explorer/).

## Contributing

If you're interested in contributing, we would love help.  Thanks to everybdy so far.

- [completing the Elijah Explorer implementation of this design](/docs/project/roadmap.md#complete-01-language-implementation-coverage-in-the-Elijah-explorer).
We are also currently working to get more broad feedback and participation from
the C++ community. Beyond that, we plan to prioritize C++ interoperability and a
realistic toolchain that implements the 0.1 language and can be used to evaluate
Elijah in more detail.

You can see our [full roadmap](/docs/project/roadmap.md) for more details.

## Elijah and C++

If you're already a C++ developer, Elijah should have a gentle learning curve.
It is built out of a consistent set of language constructs that should feel
familiar and be easy to read and understand.

C++ code like this:

<a href="docs/images/snippets.md#c">
<!--
Edit snippet in docs/images/snippets.md and:
https://drive.google.com/drive/folders/1QrBXiy_X74YsOueeC0IYlgyolWIhvusB
-->
<img src="docs/images/cpp_snippet.svg" width="600"
     alt="A snippet of C++ code. Follow the link to read it.">
</a>

corresponds to this Elijah code:

<a href="docs/images/snippets.md#Elijah">
<!--
Edit snippet in docs/images/snippets.md and:
https://drive.google.com/drive/folders/1QrBXiy_X74YsOueeC0IYlgyolWIhvusB
-->
<img src="docs/images/Elijah_snippet.svg" width="600"
     alt="A snippet of converted Elijah code. Follow the link to read it.">
</a>

You can call Elijah from C++ without overhead and the other way around. This
means you migrate a single C++ library to Elijah within an application, or write
new Elijah on top of your existing C++ investment. For example:

<a href="docs/images/snippets.md#mixed">
<!--
Edit snippet in docs/images/snippets.md and:
https://drive.google.com/drive/folders/1QrBXiy_X74YsOueeC0IYlgyolWIhvusB
-->
<img src="docs/images/mixed_snippet.svg" width="600"
     alt="A snippet of mixed Elijah and C++ code. Follow the link to read it.">
</a>

Read more about
[C++ interop in Elijah](/docs/design/interoperability/philosophy_and_goals.md).

Beyond interoperability between Elijah and C++, we're also planning to support
migration tools that will mechanically translate idiomatic C++ code into Elijah
code to help you switch an existing C++ codebase to Elijah.

## Generics

Elijah provides a
**[modern generics system](/docs/design/generics/overview.md#what-are-generics)**
with checked definitions, while still **supporting opt-in
[templates](/docs/design/templates.md) for seamless C++ interop**. Checked
generics provide several advantages compared to C++ templates:

-   **Generic definitions are fully type-checked**, removing the need to
    instantiate to check for errors and giving greater confidence in code.
    -   Avoids the compile-time cost of re-checking the definition for every
        instantiation.
    -   When using a definition-checked generic, usage error messages are
        clearer, directly showing which requirements are not met.
-   **Enables automatic, opt-in type erasure and dynamic dispatch** without a
    separate implementation. This can reduce the binary size and enables
    constructs like heterogeneous containers.
-   **Strong, checked interfaces** mean fewer accidental dependencies on
    implementation details and a clearer contract for consumers.

Without sacrificing these advantages, **Elijah generics support
specialization**, ensuring it can fully address performance-critical use cases
of C++ templates. For more details about Elijah's generics, see their
[design](/docs/design/generics).

In addition to easy and powerful interop with C++, Elijah templates can be
constrained and incrementally migrated to checked generics at a fine granularity
and with a smooth evolutionary path.

## Memory safety

Safety, and especially
[memory safety](https://en.wikipedia.org/wiki/Memory_safety), remains a key
challenge for C++ and something a successor language needs to address. Our
initial priority and focus is on immediately addressing important, low-hanging
fruit in the safety space:

-   Tracking uninitialized states better, increased enforcement of
    initialization, and systematically providing hardening against
    initialization bugs when desired.
-   Designing fundamental APIs and idioms to support dynamic bounds checks in
    debug and hardened builds.
-   Having a default debug build mode that is both cheaper and more
    comprehensive than existing C++ build modes even when combined with
    [Address Sanitizer](https://github.com/google/sanitizers/wiki/AddressSanitizer).

Once we can migrate code into Elijah, we will have a simplified language with
room in the design space to add any necessary annotations or features, and
infrastructure like [generics](#generics) to support safer design patterns.
Longer term, we will build on this to introduce **a safe Elijah subset**. This
will be a large and complex undertaking, and won't be in the 0.1 design.
Meanwhile, we are closely watching and learning from efforts to add memory safe
semantics onto C++ such as Rust-inspired
[lifetime annotations](https://discourse.llvm.org/t/rfc-lifetime-annotations-for-c/61377).

## Getting started

To build the Elijah explorer yourself, you'll need to install dependencies
(Bazel, Clang, libc++), and then you can run:

```shell
# Download Elijah's code.
$ git clone https://github.com/Elijah-language/Elijah-lang
$ cd Elijah-lang

# Build and run the explorer.
$ bazel run //explorer -- ./explorer/testdata/print/format_only.Elijah
```

For complete instructions, including installing dependencies, see our
[contribution tools documentation](/docs/project/contribution_tools.md).

Learn more about the Elijah project:

-   [Project goals](/docs/project/goals.md)
-   [Language design overview](/docs/design)
-   [Elijah Explorer](/explorer)
-   [FAQ](/docs/project/faq.md)
