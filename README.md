# Zorzella Codex

## 0. Introduction

Read the whole introduction, as it gives a guide about how to read the rest of
this document.

I have been doing software development and engineering for decades, and
sometimes people ask me what they should learn to grow in their career. This is
both a reasonable question, and one that is hard to answer, since there is so
very much. So I wrote this document with a list of things that I think a
software developer may want to learn. I named it the “Zorzella Codex”, since I’m
fond of puns.

It is divided in sections, each on a subject. Some of them have subsections, but
the document is mostly flat. The sections often start with a brief introduction
and then list ideas of what to know/learn about that subject. Occasionally I
provide some links to resources I have personally used in the past that I think
are good. I sometimes also offer some answers or hints. But mostly I present
questions or challenges, and leave the task of searching for the content as an
exercise.

This is a guide for you to know about important topics you might not even know
exist (or not realize are important to learn).

The content is presented from the perspective of a generalist, “full stack”
software engineer. Certain topics will be more or less important depending on
what your (current) specialty may be. Items are marked with a combination of a
letter and a number, denoting with a **letter** the **importance** and with a
**number** the **difficulty** (or **size**) of the topic, e.g. \[A3\] or \[B7\].
The numbers from 0 to 9 denote the relative difficulty/size. The letters go from
A to E and mean this:

1. Very important and/or broadly applicable and/or basic knowledge
2. Somewhat important and/or often applicable
3. Applicable in limited situations and/or more advanced knowledge
4. niche topic and/or advanced
5. Very niche topics and/or a mere curiosity

Though the document often clusters related topics close to each other, the
content does not need to be consumed linearly – feel free to jump around between
sections and items in the sections, seeking what is most interesting and
relevant to you at the moment.

This document expects the reader to be reasonably proficient with programming;
it is not a beginner’s guide\! And note that it’d take years of concerted effort
to learn everything that is listed here.

Note: different languages or tooling often have different names for the same
things. E.g. what Java calls a “Map”, C# calls a “Dictionary”. I will often call
out the different names; or, sometimes I’ll say something like “learn about
synchronized blocks (as Java calls them)” – meaning that other languages will
likely have something like Java’s “synchronized” keyword, but may call these
something else (e.g. in this case, in C\# this is done with “lock”). Finally, I
will also try to call out things that are more language-specific, whenever I
feel that’s important.

If you want to contribute to this doc, read the “Contributing” section.

Peace,

“Z” Zorzella

## Table of Contents

1. [The Type System in Programming Languages](#1-the-type-system-in-programming-languages)
2. [General-Purpose vs Domain-Specific Languages](#2-general-purpose-vs-domain-specific-languages)
3. [Memory Allocation](#3-memory-allocation)
4. [Virtual Machines, Interpreters, Runtime Systems](#4-virtual-machines-interpreters-runtime-systems)
5. [Operators in Code](#5-operators-in-code)
6. [Integer Numbers in Code](#6-integer-numbers-in-code)
7. [Floating Point Numbers in Code](#7-floating-point-numbers-in-code)
8. [Strings in Code](#8-strings-in-code)
9. [Error Conditions / Error Handling in Code](#9-error-conditions--error-handling-in-code)
10. [Misc Programming Language Features](#10-misc-programming-language-features)
11. [Programming Languages Highlights](#11-programming-languages-highlights)
12. [Design Patterns and anti-patterns in Code](#12-design-patterns-and-anti-patterns-in-code)
13. [Dependency Injection Frameworks](#13-dependency-injection-frameworks)
14. [Data Structures](#14-data-structures)
15. [Concurrency](#15-concurrency)
16. [Hashing, Error Correction, Compression, Cryptography](#16-hashing-error-correction-compression-cryptography)
17. [System Design](#17-system-design)
18. [Identifiers](#18-identifiers)
19. [Time, Clocks, Calendars](#19-time-clocks-calendars)
20. [Security](#20-security)
21. [Serialization](#21-serialization)
22. [Documentation](#22-documentation)
23. [Internationalization and Localization (i18n and l10n)](#23-internationalization-and-localization-i18n-and-l10n)
24. [UI, GUI, Frontend Development](#24-ui-gui-frontend-development)
25. [Computer Networking](#25-computer-networking)
26. [The Internet Protocol (IP)](#26-the-internet-protocol-ip)
27. [HTTP and related protocols](#27-http-and-related-protocols)
28. [Misc Databases/Datastores Topics](#28-misc-databasesdatastores-topics)
29. [Relational Data Bases](#29-relational-data-bases)
30. [Testing](#30-testing)
31. [Query Languages](#31-query-languages)
32. [Hardware](#32-hardware)
33. [Operating Systems](#33-operating-systems)
34. [IDEs (Integrated Development Environments)](#34-ides-integrated-development-environments)
35. [Version Control Systems: git](#35-version-control-systems-git)
36. [Misc Tools for Developers](#36-misc-tools-for-developers)
37. [Project Management](#37-project-management)
38. [Build / Deployment / Production](#38-build--deployment--production)
39. [Artificial Intelligence (AI)](#39-artificial-intelligence-ai)
40. [Health](#40-health)
41. [Books and Resources](#41-books-and-resources)
42. [Contributing](#42-contributing)
43. [Version History / Changelog](#43-version-history--changelog)

## 1. The Type System in Programming Languages

Programming language types are one of the most powerful tools to manage
complexity in software. The concept looks simple on the surface, but looks are
deceiving.

- \[C4\] Understand the two types of inheritance: “behavior inheritance” and
  “interface inheritance”
- \[B5\] Understand what is meant by “prefer composition over implementation
  inheritance”
  - Understand why it’s better to use composition
  - Understand why, despite this being a well-known principle, it is so often
    violated (hint: programming languages make composition more verbose than
    inheritance)
  - Understand how to refactor code from inheritance to composition
  - Understand why this principle applies to behavior (implementation)
    inheritance and not to interface inheritance
- \[B7\] Understand the pros and cons of statically-typed languages
- \[B7\] Understand the pros and cons of dynamically-typed languages
  - Understand how dynamically-typed languages can still leverage types in
    codebase (e.g. TypeScript or Python type hints)
  - Understand why even dynamically-typed languages often end up with a type
    system (say TypeScript for JavaScript and type hints for python 3.5+)
  - Understand particularly the things that you can do with a dynamically-typed
    language that you can’t with a statically-typed one, as well as the
    downsides
- \[C6\] Understand co-variance and contra-variance
- \[C6\] Understand Liskov’s Substitution Principle
- \[C8\] Understand type parameterization
  - Understand Generics (as seen in Java, C# etc)
    - Understand Java type erasure
    - Understand C\# reification of parameter types
    - Understand the limited way you can use reified types in Kotlin
    - Understand the hacks you can do to get something similar to a reified type
      in Java
  - Understand C++ Templates
  - Understand how Generics and Templates look similar, and accomplish similar
    goals, but are fundamentally different (runtime vs compile-time)
  - Understand variance (invariance, co-variance and contra-variance) in the
    context of type parameters
    - Understand the upsides and downsides of declaration-site variance like
      Kotin’s and C\#’s `in` and `out` type parameters
    - Understand the upsides and downsides of use-site variance, like Java’s
      `? extends` and `? super` type parameters
    - Understand other kinds of variance, like TypeScript’s “automatic
      variance”, and languages that don’t have good support for variance
- \[C4\] Understand duck typing
  - Understand the pros and cons of duck typing
- \[C4\] Understand explicit narrowing and/or broadening of types, and when
  explicit casting is needed
- \[C5\] Understand the concept of type inference
- \[C6\] Understand the concept of smart casting / type specialization
- \[D4\] Understand the different ways that languages support `enum`s
  - Covering the span from C’s enum that is just a numeric constant to
    Java/Kotlin where they are actual classes, to Rust/Swift where they are even
    more capable than Java/Kotlin
- \[C4\] Understand the different ways languages refer to “this class is not
  extensible”, e.g. Java’s `final` keyword whereas in C\# they are called
  `sealed` classes (which means something different in Java, see future point)
- \[C5\] \[Kotlin/Java\] Understand what Kotlin and Java refer to as sealed
  classes
  - Understand how these can be used, say, in a `switch` statement, as a more
    powerful `enum` (as they exist in Java/Kotlin)

## 2. General-Purpose vs Domain-Specific Languages

- \[D3\] Understand why languages like C, Java, Python, Rust, C++ are known as
  General-Purpose Languages (GPLs) while SQL, HTML/CSS, Regex are
  Domain-Specific (DSLs)
- \[D3\] Understand the inexact correlation between declarative and imperative
  languages and GPLs vs DSLs
- \[D4\] Understand the distinction between DSLs and Embedded DSLs
  - Understand why Embedded DSLs leverage the host language for integration with
    tooling (e.g. IDEs, static analysis etc) whereas DSLs need bespoke
    integration

## 3. Memory Allocation

One of the most important and messiest parts of programming is memory
allocation.

- \[B5\] Understand why nearly all general-purpose languages have a stack and a
  heap sections of memory
  - Understand what kind of data goes where and why
  - Understand why the stack is so neat while the heap is messy
- \[B4\] Understand why most languages that have a heap use garbage collection
  - For ease of programming
  - For security
- \[B4\] Understand there’s a performance penalty for using garbage collection
  - How it’s easy to end up writing code that is memory-inefficient (in space
    and allocation)
  - That garbage collection has a CPU runtime cost
- \[C8\] Learn about different kinds of garbage collectors.
  - There’s several languages that implement garbage collectors using very
    similar patterns / concepts. Java’s (several) GC systems are amongst the
    most advanced and well-documented, and it’s a good starting point.
  - Understand what kind of GC “your” language is using, and what programming
    patterns work better or worse (e.g. typically a GC is good at dealing with
    short-lived objects. You should know why)
- \[D4\] Understand how swift’s “ARC” is an alternative to garbage collection
- \[D5\] Understand the difference between a C/C++ pointer and a Java/Kotlin/C\#
  object reference
  - Understand what pointer arithmetic is and why most languages other than
    C/C++ either don’t allow it at all or segregate to sections of code labelled
    “unsafe”

## 4. Virtual Machines, Interpreters, Runtime Systems

Most programming languages rely on some kind of virtual machine (or interpreter)
to run: Java, Kotlin, Python, JavaScript/TypeScript, C\# etc. Others, like Go
and Swift, rely on a “runtime system” that helps with tasks such as memory
handling (garbage collection for Go and Automatic Reference Counting for Swift).
There’s, in fact, few languages in wide use today that do not have any kind of
runtime system, notably C, C++ and Rust.

- \[C6\] Understand what virtual machines (such as the JVM or the CLR) are for
  - And what their capabilities, advantages and disadvantages
  - Understand why they are often sandboxes
- \[C4\] Understand the concept of compiling to intermediate (non-CPU-specific)
  bytecode
  - Understand how that makes programs run faster than interpreted languages
  - Understand how it makes code highly portable
  - Understand how it is most often not as fast as compiled code, particularly
    at startup time
- See also the [memory allocation](#3-memory-allocation) section

## 5. Operators in Code

- \[B4\] Understand the logical operators available in the languages you program
  in
  - Such as AND, OR, XOR, NOT
  - Understand “short-circuit” evaluation
    - E.g. why it’s ok in Java/C\# to say `a != null && a.b() == 10`
- \[C4\] Understand the bitwise operators available in the languages you program
  in
  - The same AND, OR, XOR and NOT but that operate on the bits
  - Understand when to use these vs the logical operators
- \[B4\] Understand the arithmetic operators available in the languages you
  program in
  - `+ - * / % **` etc
  - Understand why diving by 8 is cheaper than dividing by 10
- \[B6\] Understand what other operators exist in the languages you program in
- \[B7\] Understand why some languages forbid operator overloads
- \[B7\] Understand why some languages allow for operator overloads (on some
  operators)
  - Understand the pitfalls, and ways languages are trying to deal with those

## 6. Integer Numbers in Code

- \[B4\] Understand the two most common models that programming languages offer
  to store an integer number in memory: fixed-width primitives such as `int8`,
  `int16`, `int32`, `int64` or their unsigned counterparts (their names vary in
  different languages); and arbitrary-size number classes, such as integers in
  python, or `BigInteger` in Java/Kotlin/C\#
  - Understand the benefits and downsides of each, and when you’d want to use
    either
  - Understand that, even when using arbitrary-size number classes, they still
    need to rely on fixed-width number for math, and why
- \[C6\] Understand how computers (and hardware) handle math
  - Be able to put in approximate order from least to most expensive, the
    following:
    - `50 * 2`
    - `50 / 3` (integer math, no remainder)
    - `50^7`
    - `50 % 3`
    - `50 + 2`
    - `50 - 2`
- \[B6\] Understand fixed-width number in-memory representation
  - Understand 2’s complement for signed numbers
  - Understand the challenges in converting from, say an int16 to an int32 and
    the other way around
  - Understand why for signed numbers, negative values always go one more than
    positive values, e.g. an `int8` has a range from `-128` to `127` (rather
    than `-127` to `127` or `-128` to `128`).
    - Understand the challenge that is to a function that returns the absolute
      value of a number (like Java’s `Math.abs`)

## 7. Floating Point Numbers in Code

- \[B5\] Have a deep understanding of the inherent imprecision of floating point
  numbers
  - Be able to articulate why it’s always wrong to compare two floats for
    equality
  - Be able to articulate why you should never use floating point numbers to
    model, say, an amount of money
  - Understand why dividing a float by 10 will result in rounding errors
- \[C4\] Understand why it’s ok for floating point numbers and their arithmetic
  to be approximate
- \[D3\] Understand why floats are almost always signed
- \[D5\] Understand IEEE 754, and how different languages are more or less
  strict in their implementation of that spec
  - Understand that this is given “almost for free” by modern hardware
  - Understand that, contrary to integers, there can never be an overflow from
    large positive numbers to negative numbers
  - Understand positive and negative infinities
  - Understand `NaN`s

## 8. Strings in Code

Strings (aka pieces of text) are one of the most common types of data a program
has to deal with. But they are messy, and different languages handle this
messiness in very different ways.

- \[B4\] Understand how/why C exposes strings are null-terminated arrays of
  chars, whereas Java and Python’s strings are opaque
- \[C3\] For languages where strings are opaque, be able to articulate why you
  always need to provide a charset to serialize a string
- \[B4\] Understand why several languages model strings as immutable
- \[C5\] Understand why languages may model characters as having anything
  between 1 byte and 4 bytes
  - Understand why sometimes these change dynamically
- \[D4\] Understand what is string interning
  - And how some languages choose to do it automatically and some don’t
- \[B4\] Understand why languages have two ways to compare strings: value and
  reference comparator
  - E.g. understand why, in Java, you should in general not use `==` to compare
    two `String`s
- \[C6\] The variety of ways that strings are modeled points to the fact that
  there is no way to implement strings that is strictly better than others. Be
  able to articulate the pros/cons of each choice
- \[A7\] Be sure you know how the language you are using models strings in every
  one of these possible ways, and what are the pitfalls you need to watch for

## 9. Error Conditions / Error Handling in Code

Handling errors is messy, and there are multiple paradigms favored by different
languages, and, indeed, it often happens that a single code base uses different
paradigms in an inconsistent manner.

- \[B3\] Understand what Exceptions/Throwables are
  - Understand the concept of checked exceptions (as Java calls them)
- \[B5\] Understand alternatives ways that methods use to convey errors (e.g.
  error results)
- \[C4\] Understand the pros and cons of either approach
- \[B5\] Understand why Effective Java’s advice says that exceptions should be
  used for exceptional cases
- \[C5\] Understand how different languages “favor” one method of error over the
  other

## 10. Misc Programming Language Features

- \[C6\] Understand object-oriented vs procedural vs functional programing
- \[C4\] Understand imperative vs declarative programming
- \[B7\] Understand reflection
  - Understand concepts such as
    - Type erasure
    - Reification
  - Understand that reflection is a runtime concept
    - But also understand how introspection can do something similar to
      reflection, but at compile-time
- \[C5\] Understand the difference between high-level languages (like C#, Java
  and most others) and lower-level languages (like C as assembler)
- \[C7\] Understand the philosophies around languages “surface size”
  - Understand the advantages of “small” languages, like Go and C. E.g.
    - Easy to learn
    - Easy to implement a parser/compiler
    - Fewer ways to do the same thing
  - Understand the advantages of “large” languages like C# and Kotlin. E.g.
    - “First class” support for more use cases
    - can make the code much more expressive
- \[C7\] Understand the different language philosophies around
  backward-compatibility
  - What are the pros and cons of strong backwards-compatibility guarantee (of
    source code and/or intermediate code when applicable and/or standard
    libraries)
- \[B6\] Understand the value of having preconditions and postconditions in your
  code
- \[C6\] Understand the concept of invariants
- \[B8\] Understand the issues with side-effects
  - What they are and why they are so “special”
- \[B8\] Understand why immutability is so valuable

## 11. Programming Languages Highlights

_“Programming is the closest thing there is to real-life alchemy”_ – “Z”
Zorzella

Needless to say, programming languages are the most important element in a
programmer’s career. A good programmer knows their primary language(s) really
well, but they also know other languages.

What a programmer can do is shaped and limited by the language they use to
program – e.g. if a language has terrible support for threading, threading will
not be used much; if a language has clunky syntax for lambda functions, they
will be used less; etc.

It’s very useful to learn multiple languages, or to at least learn about them.
Not only you’ll be better prepared for when you need to read/write a snippet of
code in a language other than your primary one, but this will also enable you to
think in different paradigms, and appreciate strengths and weaknesses of the
language you end up using the most.

You’ll also be able to choose an appropriate language to solve a particular
problem – you must be able to justify when you would want to use each language
over the others.

Several sections before this delved into language features. Here are some
languages I find useful, and some brief thoughts about each of them,
particularly some of their “uniquesses”, for better or worse, building on the
terminology presented before.

TODO Extract this content into a separate document and restructure it

### Java

- JVM has auto-memory allocation with excellent garbage collector
- Compiles to intermediate (non-CPU-specific) bytecode, which
- The language spec is of modest in size
- Language spec has historically been very disciplined; features get added in a
  well-though-out manner that (most often) work well with the rest of the
  language
- Language, VM and standard library have been extremely backwards compatible (to
  a fault)
- It has a pretty good type system, including a pretty good generics system;
  most of the time, casting is not necessary, and, thus, whole classes of bugs
  are not common

### Kotlin

- Inherits many of the benefits from Java by virtue of running on the JVM – many
  of the plusses from the Java section apply
- Has even an even better type system than Java
  - This is particularly true about nullable types, which are built directly in
    the type system
  - sealed class hierarchies
  - `in` and `out` type parameters
  - Better type inference, leads to smart casting/type specialization
- The language spec is very large (much larger than Java), for better or worse
- Better support for “functional-style” programming with lambdas

### C / C++

C and C++ are quite different languages, but their existence is intertwined, so
they are discussed together. Differences will be pointed out.

- C and C++ are messy, but the reality is that the vast majority of the most
  performant CPU programs written today were written in C/C++. Understand why
- Understand why even “self-hosted” languages like Rust have their compiler
  trace its lineage to C/C++
- Understand C++’s philosophy of “zero-cost abstraction”
- Understand how C/C++ deals with memory allocation in such a different way from
  just about all other modern languages.
  - Understand how they even allow for tinkering with the stack
- Understand what is pointer arithmetic
- The language spec for C is small
- The language spec for C++ is large

### Rust

- Rust may finally give us a language that matches the performance you can get
  with C/C++, but with memory safety (and a much more ergonomic and modern
  syntax).
  - Understand how it does that
  - Understand how big a deal that is

### Python

- Excellent scripting language
- De facto standard for many domains, including machine learning and mathematics
  - Huge, freely-available libraries for integrating with just about anything
- Understand the downsides with python’s “semantic whitespaces”
- Slow (e.g. Java is around 10x to 50x faster than python)
  - Interpreted language
  - Extremely dynamically typed
  - “Everything is an object”
  - Global Interpreter Lock
  - This is mostly dealt with by writing the computationally expensive part in
    another language and integrating with python

### Javascript

- A very messy language, it has two important things going for it
  - It runs in (just about) every web browser
  - It is the only thing that runs in every web browser
- Having the language be single-threaded
  - Limits what you can do
  - Simplifies programming a lot
- Learn about the “callback” approach to IO and how that is well-suited for a UI
  language

### Typescript

- Compiles to javascript
- A surprisingly-good uplift to JavaScript
  - particularly considering that all JavaScript is valid TypeScript
- Excellent type system, with advanced type inference and smart casting
  - Again, surprisingly-good type system, considering that JavaScript has a weak
    and dynamic type system
- Since all JavaScript is valid TypeScript, makes gradual transition of a
  JavaScript code base to TypeScript possible

### C#

- “Greatly inspired” by Java
- Improved Java in several aspects (like generics)
- Less disciplined than Java in adding features
- A large language spec
- Offers some features that give it a performance edge on Java

### Bash

- Very messy language, but shell scripting is available just about anywhere. So
  it’s very useful to know how to write simple shell scripts

### Swift

- Compiles to bytecode.
- Interesting take on “managed memory allocation” that does not involve garbage
  collection. Learn about ARC (automatic reference counting)
  - Attempt to be a viable C replacement without the memory issues: though it is
    not as fast as C/C++, it is (along with Go) faster than most other “modern”
    languages

### Go

- Like Swift, Go is another attempt at being a viable C replacement, and it
  compiles to bytecode
- But, contrary to Swift, it uses garbage collection
  - Interestingly, it achieves a similar performance to Swift
- Explicit goal of having a small language spec
- Learn about its use of coroutines, channels
- Understand why it chose to not have exceptions
- Duck-typed

## 12. Design Patterns and anti-patterns in Code

There are several programming patterns that are used over and over again.
Learning about them will help you not only come up with good solutions to
problems you face, but also help you get up to speed with an unknown code base.

- \[C7\] Read a book that does a rigorous discussion of some patterns. My
  favorite is the good old “Design Patterns: Elements of Reusable
  Object-Oriented Software”
  [book](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612/ref=sr_1_1_sspa?crid=29YYD60CPR6OE&dib=eyJ2IjoiMSJ9.mTRaTOPYqsPcUsGD8aznte8IMQZZiYjv7_Xwyyi1iS2agVs4KLcx5qwmrKiyIxDiiaA6QbUY3MCBnb28lUrTGOw4rZYq2Lhf6z4JylQnbFuTfD6WMSKZ2izHndzfV-Ky9NmDl7WsksMgVxIlYFmG7iOkspV9gCvaWen0y-NgyAB5h9heo2aiCmVs-15_vB4oaJk39mlJ_DXQdKEmTKZAaisgf_stgMTzEpcnj8Ju6qc.UsxA9CKA92WPXqYKfZEDlzWh4BkKAfrgBstHbML-kUk&dib_tag=se&keywords=design+patterns&qid=1767328460&sprefix=design+patterns%2Caps%2C215&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1)
  – it’s a bit outdated and there’s definitely more patterns to learn, but it’s
  very well-written.
- \[C7\] Some patterns you want to be very familiar with are listed here. For
  each, you want to be able to not only describe it, but also to think of at
  least one situation where it would be the right pattern to use:
  - Singleton
  - Static Factory Method
  - Thread Locals
    - And how it’s similar to Singletons
  - MVC / MVP
  - Observer/Observable
  - Publisher/Subscriber
  - Producer/Consumer
    - And how it’s similar to Publisher/Subscriber
  - Facade
  - Builder
  - Visitor
  - Dependency Injection (DI) / Inversion of Control (IoC)
    - Understand how it makes the code more testable, More modular / flexible
      and system interactions easier to understand
    - Understand Scope Mismatch (aka Captive Dependency) the issue with object
      lifetime management (“scopes”) where you should not inject something that
      has a shorter lifetime than the injectee
    - See also
      [Dependency Injection Frameworks](#13-dependency-injection-frameworks)
      section
- \[C8\] For each of these, understand if they are sometimes (or always)
  considered an anti-pattern, and why, and what are the alternatives
  - E.g. Singletons vs Dependency Injection

## 13. Dependency Injection Frameworks

Dependency Injections frameworks are very common (for reasons we’ll explore
below) and there are some key concepts you should understand. Unfortunately, the
nomenclature used by different frameworks is not always consistent, so be warned
that things may be called here by a different name than you are used to.

- See also the “DI” bullet in the
  [Design Patterns](#12-design-patterns-and-anti-patterns-in-code) section
- \[C5\] Understand the difference between DI and a DI framework
- \[C5\] Understand why it’s common to want to use a DI framework when using DI
  - E.g. it saves a lot of boilerplate
  - E.g. it makes the code easier to refactor
  - E.g. it helps with object lifetime management (through “scopes”)
- \[C4\] Understand how DI frameworks use scopes (sometimes called something
  else) to help with Object Lifetime Management (sometimes called Instance
  Management)
- \[C5\] Learn about choices of different DI frameworks in your Language
  - \[Java\] Understand the differences between Guice, Springboot and Dagger

## 14. Data Structures

Storing and retrieving data (in memory or not) is a key part of writing
software. You will use basics (Lists, Sets, Maps) all the time, and you often
use (or reinvent) more advanced ones such as MultiMaps or Persistent Queues. And
it is good to know about the existence of super-specialized ones such as Bloom
Filters, so you know how to solve problems that might seem intractable
otherwise.

- \[A7\] Learn about the basic data structures
  - List (aka or similar to Array)
  - Set
  - Collection / Iterable / Iterators (as Java calls these)
  - Map (aka Dictionary)
  - Queue (FIFO)
  - Stack (LIFO)
  - Tree (particularly but not only binary trees)
  - Graph
    - Directed
    - Weighted
    - DAG (Directed Acyclic Graph)
- \[B7\] Learn about more advanced data structures
  - Cache
  - MultiSet
  - MultiMap
  - BiMap
  - Sorted data structures (like Lists, Sets and Trees)
  - Blocking Queue
  - Persistent Queue
  - Balanced Tree
  - Heap
- \[D7\] Learn some specialized data structures
  - B-Tree
  - Trie
  - Sparse Matrix
  - Bloom Filter
- \[C5\] Understand what state machines are
  - Understand they are not data structures, but there are similarities
  - Learn about Finite State Machines/Automata
- \[C4\] Understand some of the options in implementations of data structures,
  and when to use them
  - Array List vs a Linked List vs Double Linked List
  - HashSet vs TreeSet
  - Hash Map vs Tree Map
- \[B5\] Understand when to use a List vs Set
  - Understand how and why often Sets are implemented with an “undefined
    iteration order”. Understand what this means, and the consequences and
    pitfalls
- \[C5\] Understand the difference between a DAG (Directed Acyclic Graph) and a
  non-DAG
  - And the implications – e.g. why are DAGs much easier to handle?
- \[B4\] Learn about different ways to traverse trees
  - Depth-first search (DFS) vs breadth-first search (BFS)
  - Pre-order, in-order, post-order
- \[C7\] Learn about different algorithms to traverse graphs
- \[B5\] \[Java\] Understand what is the difference between an Array vs List
- \[C4\] Concurrency
  - Understand thread-safe vs non-thread-safe data structures
  - Note: many other concurrency-related things will be discussed in the
    Concurrency section
- \[C8\] For each data structure listed in this section, make sure you can list
  a few situations (or, for specialized one, at least one situation) where the
  data structure is ideal, and why, and how it compares with other similar data
  structures
  - E.g. when would it be better to use an array-backed list vs a linked list,
    and the other way around

## 15. Concurrency

- \[C8\] Learn about different strategies for concurrent programs, and the
  terminology around them
  - OS Threads
  - “Virtual threads” (as java calls them)
  - Callbacks
  - Continuations
  - Coroutines
  - Async/Await
  - Reactive
- \[C5\] Learn about “happens-before”.
  - Understand it well, and why it has become the industry standard across
    languages
- \[C4\] Understand how concurrency/mutexes is built on CPU’s test-and-set
  operators
  - \[E4\] Understand how it’s actually possible to implement a mutex in a CPU
    without a test-and-set
- \[C5\] Understand concurrency primitives:
  - Locks / Monitors / Mutexes
    - Understand Reentrant locks
  - Semaphores
  - Blocking Queues
  - Executors (as Java calls them)
  - `volatile` fields (as Java calls them)
  - `synchronized` blocks (as Java calls them)
    - Understand well how they acquire and release locks
    - Understand `wait` / `notify` (as Java calls them)
- \[B5\] Learn about race conditions
  - And how they relate to thread-safety of data structures
  - Learn how to get an intuition of when race conditions may be happening, and
    how to find their causes
  - Understand why immutability is such a useful tool to achieve thread-safety
- \[B4\] Learn about deadlocks
- \[C7\] Stream processing technology, like
  - ETL
  - Mapreduce
  - Flink

## 16. Hashing, Error Correction, Compression, Cryptography

These are four distinct subjects, each important to understand, but with some
interesting overlap, so I’ll cover all in this section.

- \[C5\] Learn about hashing algorithms, and the need/desire for
  - Collision resistance
  - Determinism
  - Efficiency
  - One-way-ness
- \[C5\] Learn about the need and use of cryptographically-secure hash
  algorithms / cryptographic signatures
- \[D4\] Learn about the different kinds of encryption
  - Secret Key
  - Public-Private Key
- \[D3\] Compression
  - Be familiar with how compression is implemented, at least in principle
- \[C6\] Error correction
  - Understand what error checking and correction are
    - Learn what parity checks and check digits are and how they are used
    - Learn some simple error correction in depth
      - Wonderful video on Hemming Codes from 3Blue1Brown:
        [video](https://www.youtube.com/watch?v=X8jsijhllIA&t=126s)
      - Reed-Solomon is also fun to learn
    - Understand how it’s useful and used in everything from credit card numbers
      to bank slips to QR codes

## 17. System Design

- See also the [Design Patterns](#12-design-patterns-and-anti-patterns-in-code)
  section
- \[D3\] Understand functional vs non-functional requirements
- \[C4\] Understand the value of a good API
  - Excellent resource: Josh Bloch’s excellent “How To Design A Good API and Why
    it Matters” [talk](https://www.youtube.com/watch?v=aAb7hSCtvGw)
- \[D5\] Get acquainted with some standard non-functional requirements
  - Scalability
    - Understand the difference between vertical and horizontal
    - Why are some systems better at horizontal scaling, and what do they mean
      by “infinite scaling”
  - Performance
    - Throughput
    - Latency
  - Availability
  - Reliability
  - Maintainability
  - Security
  - Usability
    - Learnability / Discoverability
    - Accessibility
    - Operability
    - User Error Protection
    - Aesthetics

## 18. Identifiers

- \[C4\] Understand the messiness of identifiers. E.g. how tricky it can be to
  have good, unique identifiers
  - Understand how UUIDs / GUIDs work, but are not adequate to all circumstances
  - Likewise for cryptographic hashes
  - Likewise for timestamps (see also the
    [Time, Clocks, Calendars](#19-time-clocks-calendars) section)
  - Understand the unique issues IDs that need to be used by end users
    - E.g. a Bank Account or a gift card redemption code
    - Understand the role of error correction / checksum
    - Understand the role of Confusable-free or Unambiguous character set like
      Crockford's Base32

## 19. Time, Clocks, Calendars

- \[C4\] Understand how messy it is to deal with time, clocks and calendars
  - Check out these “Falsehoods Programmers Believe About Time”
    [list](https://gist.github.com/timvisee/fcda9bbdff88d45cc9061606b4b923ca) –
    try to imagine why each of the statements is a falsehood
- \[C5\] Understand the need to use a testing double for clocks
- \[C4\] Understand the common ways to represent time in code
  - E.g. millis since UNIX epoch

## 20. Security

- \[C7\] Understand the concepts of authz and authz
  - How they are different
  - How they relate to each other
- \[D5\] Understand what memory exploits are
  - Buffer overflow
- \[C7\] Understand some kinds of web / HTTP exploits
  - CSRF (Cross-Site Request Forgery)
  - XSS (Cross-Site Scripting)
- \[D7\] Understand some kinds of hardware exploits
  - Rowhammer
  - Specter
- \[C6\] Understand other kinds of exploits
  - Confused deputy
- \[C3\] Understand vulnerability scanning
- \[C6\] Understand fuzzing / fuzz testing
- \[C6\] Understand the role of penetration tests

## 21. Serialization

Serialization / deserialization is used to transmit in-memory data from one
place to another, or to store it for future use. In fact, storing for future use
can also be thought of a transmitting data from the past to the future.

- \[C5\] Understand the concept of serialization/deserialization
- \[C5\] Understand different ways to implement this in code
  - That it can be achieved with manually written code
  - That is can be (and so often is) achieved using some library/tooling
  - That it can be implement to do the serialization/deserialization heavy
    lifting through generated code or using reflection
    - and what are the advantages/disadvantages of each
- \[C5\] Understand the different common serialization protocols/formats
  - protobufs (gRPC)
  - JSON
  - XML
  - others
- \[C6\] Understand the need to make serialization/deserialization backward
  compatible and forward compatible as well
  - Understand the different strategies used by the different common
    protocols/formats to achieve this
- See also the [HTTP and related protocols](#27-http-and-related-protocols)
  section

## 22. Documentation

A good software engineer will have to write lots of documentation: readable
code, code comments, design docs, etc.

- \[C5\] Understand how to leverage the different ways code is documented
  - The code itself. Particularly, readable code (say well-named
    functions/variables) is the ultimate form of documentation, as it’s the
    source of truth about what your program does
  - Comments:
    - “Structured” comments (aka “Doc Comments”, “Docstrings” etc). That’d be
      Javadoc in Java, Kdoc in Kotin, rustdoc in Rust etc. Understand why you
      always want to use a structured comment when you can instead of “regular”
      code comments
    - Regular code comments.
  - Tests. These provide a “third form of documentation” that is also
    functional. A well-written test can provide a working example of how to use
    an API, for example
  - Other docs: like Google Docs, or Wiki articles or recorded talks. They cover
    everything from requirements to design to demos
- \[C5\] Learn documentation tools/languages, like
  - Md (Markdown)
  - TEX / LaTEX
  - UML
  - javadoc/kdoc/rustdoc etc
  - Mermaid
- \[B3\] Learn how to leverage TODOs to track future work, and how to not
  overuse them
- \[C3\] Understand that when documenting a method/class, you don’t quite want
  to document what the method/class does, but you want to document the contract
  - Understand the concept of API contract
  - Understand the concept of preconditions, post-conditions, side effects etc

## 23. Internationalization and Localization (i18n and l10n)

Software that has user-visible content needs to deal with not only being
translated but also properly localized.

- \[C4\] Understand the difference between i18n and i10n
- \[C3\] Learn about Unicode
- \[C4\] Learn about character encodings in general
  - Learn about ASCII
  - Learn about UTF-8 vs UTF-16
  - Learn about other encodings
  - Understand encodings that take a fixed vs a variable number of bits
- \[C4\] Understand the difference between the memory representation of a string
  and its serialized form
- \[C4\] Understand why using string concatenation of user-visible messages
  makes l10n virtually impossible
  - Learn how translations and localizations are actually done
- \[C5\] Understand the pitfalls with the different ways to format dates (e.g.
  YYYY/MM/DD, MM/DD/YY, MM/DD/YYYY, DD/MM/YYYY, DD/MM/YY etc) and how to build a
  UI that mitigates that
- \[C6\] Understand the pitfalls with the different ways to format large numbers
  and decimal values (e.g. 100,000.00 vs 100.000,00 vs 1,00,000.00) and how to
  build a UI that mitigates that

## 24. UI, GUI, Frontend Development

- \[C7\] Learn about the unique challenges of writing UI code
- \[C7\] Learn UI-specific patterns such as Model-View-Controller (MVC) and
  Model-View-Presenter (MVP)
- \[D8\] Have a general understanding of UX concepts and challenges
  - Good watch: “How We're Redesigning Audacity For The Future”
    [video](https://www.youtube.com/watch?v=QYM3TWf_G38)
- \[C4\] Understand the concept of A/B experiments
- \[C7\] Learn HTML / CSS
- \[B6\] Understand HTML Cookies
  - Learn about SameSite Cookies
- \[C5\] Learn about Same-Origin Policy (SOP)
- \[C5\] Learn about WebSocket
- \[C5\] Learn about WebHooks
- See also the [Security](#20-security) section

## 25. Computer Networking

Computers are much more powerful when connected to each other.

- \[D5\] Understand the basics of the OSI 7-layer
  [architecture](https://en.wikipedia.org/wiki/OSI_model#Layer_architecture)
- \[C3\] Technically, there are many protocols in use to “connect computers”.
  Can you articulate why things like USB and HDMI are not considered networking,
  whereas Bluetooth, Zigbee and (of course) IP are?
- \[C3\] Understand the wired OSI layer 2 protocols that are in actual use today
  - Primarily Ethernet
    - Understand that while the RJ45 (technically the 8P8C connector) is what
      consumers think of when they think “Ethernet”, there are several
      alternatives used in the industry, from other electricity-based connectors
      to fiber optics
    - Learn about power over Ethernet, how it’s useful
  - Get to know about wired niche alternatives to the Ethernet protocol
  - You may want to learn about historical alternatives (like Token Ring and
    ATM) and why they “failed”
- \[C4\] Understand the wireless OSI Layer 2 protocols that are in actual use
  today, and how they are different from each other
  - For computers, primarily Wi-Fi (IEEE 802.11)
  - For cell phones, primarily LTE-M and NB-IoT (part of the 4G/5G specs)
  - IEEE 802.15.1 which is the Layer 2 part of the Bluetooth spec
  - Also, IEEE 802.15.4, a low-powered alternative to Wi-Fi
  - Also, LoRa another protocol for low-powered devices
- \[C6\] Understand the fundamental challenges with networking, including
  - Loss of connectivity
  - Increased Lag
    - Learn how Predictive / Optimistic behavior is often used in Frontend
      codebases to mitigate the problem this causes the user interaction
    - Learn how Predictive / Optimistic behavior cause their own set of
      problems, and why, despite that, they are still common-practice
  - Decreased throughput for computations
  - Network partitioning. Understand why that is a thorn on the side of DataBase
    replication
  - Routing
- \[C6\] Understand the concept of Flow Control
  - Why it’s needed
  - How it’s implemented (e.g. learn about leaky bucket, pushback, tokens etc)
- \[C4\] Understand the difference between streaming and message-base
  (non-streaming) protocols
  - Both unidirectional and bidirectional
- \[D4\] Understand the concept of Proxying
  - Why it’s used
  - How it’s implemented
    - How it can be implemented in different points of the OSI Layer
      - Typically, Layer 7 (application) or Layer 4 (transport). NAT (Layer 3\)
        is also common, but it’s not generally thought of as a proxy (why?)
      - Why/when you’d want to do proxying at one vs another layer
  - Complications/Limitations
- \[C5\] Understand the concept of Load Balancing
  - How it can be implemented a
  - Stickiness
- \[D4\] Understand tunneling
- \[C4\] Learn about NAT
  - Port forwarding

## 26. The Internet Protocol (IP)

To say that the Internet Protocol is massively successful is an understatement.
A few niche protocols like Zigbee and Bluetooth (for low-powered devices) do not
use IP, but even low-power alternatives like the Thread protocol does. All other
general purpose network protocols, from AppleTalk to Novell NetWare are at this
point historical curiosities.

It is in your best interest to understand the IP protocol very well.

- \[D4\] Understand how it sits in the OSI layer 3, and what that means
- \[C5\] Understand TCP and UDP
  - What they are
  - How they are different
  - When to use one vs the other
- \[D4\] Understand Ipv4 vs IPv6
  - Understand how IPv4 is still commonly-used 30 years after it was expected to
    run out of addresses, by: the clever invention of NATs; the
    repurposing/refining of network masks; the reclaiming of large chunks of
    addresses; and by IPv6
  - Understand IPv4 “Private Addresses” vs IPv6 “Unique Local Addresses” (ULA)
  - Understand NAT (Network Address Translators)
    - Understand port forwarding, and why it less common today due to the
      available alternatives

## 27. HTTP and related protocols

- \[D3\] Understand how you can make a crude HTTP/1.1 request by typing into a
  telnet session
  - Understand why TLS/SSL makes this impossible
  - Understand why HTTP/2.0+ use a binary protocol that makes this not possible
- \[D3\] Understand HTTP encryption
  - HTTPS, TLS/SSL
- \[C4\] Understand the different HTTP methods (GET, POST etc) available
  - Understand well the difference between a GET and a POST: when to use each
    and why
  - Get acquainted with the other, more obscure, methods
- \[C5\] Understand HTTP Error codes
  - When should you use a 4xx vs a 5xx error code
  - Why are there several success codes. What is each of them for?
  - What are some of the common 4xx and 5xx error codes
- \[B6\] Understand different RPC technologies: the similarities and differences
  between gRPC, REST, SOAP, GraphQL
- \[B5\] Understand gRPC
  - Why is it the most performant on serialization/deserialization
  - Why is it the most compact for data transfer
  - The difference and relation between gRPC services and protobufs
  - The pros and cons of the protobuf design choice to generate code (which is
    the opposite from most other RPC)
- \[B5\] Understand REST
  - What are the principles that underlie RESTful APIs
  - How it makes them simpler than SOAP\\
- \[C4\] Understand GraphQL
  - What problem it tries to address (e.g. expose a flexible API so clients can
    have more control)
  - What problems those choices cause (e.g. the “N+1” issue)
- See also the [UI, Gui. Frontend](#24-ui-gui-frontend-development) section
- See also the [Serialization](#21-serialization) section

## 28. Misc Databases/Datastores Topics

- \[B8\] Learn SQL. It has remained stubbornly relevant for decades, not only in
  the context of traditional, relational DBs but also in the context of data
  warehousing
- \[C8\] Understand the differences between the different kinds of databases,
  and terms associated with them:
  - RDBMS
  - Document Store
  - Data Store
  - Column-based storage
  - ACID / BASE
  - Two-phase commit
  - Data warehousing
  - Query planning and optimization
  - Indexes
  - Partitioning/Sharding/Federation
- \[C7\] Understand transactions
- \[C7\] Be familiar with different databases/datastores:
  - Postgres
  - MySQL
  - Redis
  - Cassandra
- \[D6\] Understand distributed databases
  - Understand terms such as:
    - Partitioning
    - Consensus (e.g. Paxos)
    - Strongly-consistent vs eventually-consistent
- \[C5\] Understand the concept of Normalized / denormalized data
  - Why would one want/need to have denormalized data?
  - Why would one want to try to have normalized data whenever possible?

## 29. Relational Data Bases

The following items use concepts and terminology from Postgres. Similar concepts
and features exist in other DBs, maybe with different names.

- \[A4\] Understand the costs benefits associated with having indexes
- \[C8\] Understand different kinds of indexes, how to use them, when to use
  them
  - B-Tree (default)
  - Hash
  - GIST
  - GIN
  - Etc
- \[B5\] Understand how to make modifications to schema
  - Understand which kinds of modifications require which kinds of table locks
    (read/write)
- \[C8\] Understand these terms:
  - DB tuning
  - Vacuuming
  - Range partitioning (and other kinds of partitioning)
  - Replication
- \[D5\] DB / table / schema permissions
  - Roles
  - Privileges
  - Ownership
- \[C7\] Understand query planning and optimization
  - Understand when you may want to study query plans, how to read them, and how
    you can use that to optimize your queries

## 30. Testing

- \[C4\] Understand the different kinds of testing doubles and what they are
  good for (note: testing double nomenclature is used inconsistently, using the
  one from this ToTT
  [entry](https://testing.googleblog.com/2013/07/testing-on-toilet-know-your-test-doubles.html))
  - Mock, Stub, Fake, Dummy, Spy
- \[C4\] Understand test-driven development (TDD)
  - If you haven’t done TDD, you should try it
- \[C7\] Understand the pitfalls of testing
  - E.g. what change-detector tests are and why they are a problem
- \[C7\] Understand code coverage
  - And get to understand how they are intended to be used, and how they are
    often abused, and what problems arise from that
- \[C8\] Understand the different kinds of testing (and the often conflicting
  terminology and overlap)
  - Unit tests
  - Functional Tests
  - Integration Tests
  - Load / Stress tests
  - Smoke Tests

## 31. Query Languages

There’s a few very useful query languages to learn.

- \[C3\] Learn SQL. As discussed elsewhere
- \[C3\] Learn Regular expressions
  - Useful “free-form string matching” in a variety of contexts, from
    development, to production code, to testing
  - Great resource to learn Regexp:
    [site](https://www.regular-expressions.info/tutorial.html)
- \[D3\] Learn Xpath
  - Great power tool for querying XML / HTML
  - Great resource to learn xpath:
    [site](https://www.w3schools.com/xml/xpath_intro.asp)
- \[C3\] Learn jq
  - Available through its eponymous CLI tool to query JSON
- \[D3\] Learn GraphQL. As discussed elsewhere

## 32. Hardware

This document is focused on software, and it’s easy to take hardware for
granted. And most people will work most of the time in a platform-agnostic
language. Indeed, even when writing C/C++ programs, unless you work on a
compiler, most of the specifics of the platform are abstracted from you. All
that said, it’s important to have some understanding of key hardware concepts.

- \[B5\] Understand the differences between CPUs vs GPUs
- \[D7\] Understand the messiness of bootstrapping and the role of things like
  UEFI (and the older BIOS)
- \[D6\] Learn the basics of CPU instructions
  - Understand the difference between RISC vs CISC architectures
- Get acquainted with the terminology:
  - CPU registers
  - CPU execution pipelines
  - Branch prediction / speculative execution
  - CPU caches (like L1 and L2) and why these things exist
  - Big endian vs little endian
- \[D6\] Understand why Java allows for “word tearing” of 64-bit numbers
- \[C5\] Be able to give a rough estimate for the following questions on a
  “modern computer”:
  - How many additions/comparisons can be performed in a second?
  - How long does it take to read a 32-bit register?
  - How long does it take to read 32 bits from cache? From memory? From disk?
    From the local network? From a cloud provider? From a server halfway across
    the world?
- \[B5\] Understand the difference between throughput and latency when
  considering data transfer speeds

## 33. Operating Systems

- \[C8\] Be familiar with the different OSs, e.g.
  - MacOS
  - MS Windows
  - GNU/Linux
    - Learn about Linux Distributions
  - iOS
  - Android
  - ChromeOS
  - BSD
- \[C9\] Understand UNIX, derivatives and the fragmentation
  - Understand how most OSs used today are some derivative of UNIX (sometimes
    referred to as UN\*X for trademark reasons)
  - Understand what is the role and limitation of POSIX
  - Understand the UN\*X filesystem hierarchy
  - Learn how to use pipes
  - Understand the philosophy of “everything is a file handle”
    - and how that applies to things like peripherals
    - Also to things like `/dev/random`
- \[D5\] Understand what a Real-Time OS is
  - And that is not, as commonly thought, a “real fast” OS
- \[D7\] Understand how OSs rely on CPU Privilege Levels (Protection Rings) to
  implement things like preemptive multitasking and security/isolation
  - Understand User Space vs. Kernel Space

### Filesystems

TODO: this section is under development

## 34. IDEs (Integrated Development Environments)

It is important to master tools used to develop software, and the IDE is
probably the most important

- \[A7\] Explore a few IDEs, and understand what they can do (or do better) that
  others
- \[A8\] When you settle on an IDE (or a primary one)
  - Learn what it can do
  - Learn its keyboard shortcuts to the actions you use often
  - Shape it for your needs: configure the views; add missing useful keyboard
    shortcuts; make the fonts readable for you; install useful plugins
- \[B6\] Learn how to use your IDE to perform refactoring. You will constantly
  need to refactor your code, and your IDE can help you with that task
  immensely. Though not all refactorings apply to all languages, here are some
  examples of common refactors you should know well how to perform (including
  without using the mouse):
  - Rename (variables; classes; methods etc)
  - Move (a class/file to a different package/directory; a method from a
    class/file to another; a constant)
  - Extract a method/function
  - Inline (a method/function; a local variable etc)
  - Remove a parameter to a method/function
  - Add a parameter to a method/function
  - Reorder parameters to a method/function
  - Change the type of the parameter to a method/function
  - Extract an interface/superclass (or the opposite)
  - Add/remove explicit type declarations (say to local variables)
- \[B4\] Learn how to use your IDE to navigate your repository. You want to
  efficiently navigate code, while modifying it as well as while you are trying
  to understand it. Here are some things you want to be able to do efficiently
  (including without using the mouse):
  - Go to a file by name. The same for a class and for a function/method
  - Find a string in your codebase
  - Go to the definition of a method/variable/parameter
  - Go back
  - Bookmark stuff, go to bookmarks
  - Go to last edit location
- \[B4\] Learn how to use your IDE as a text editor. So sometimes you write
  code. You want that to be efficient as well. When writing, you want the IDE to
  be helpful, not a hindrance. Here’s some thoughts:
  - Code completion. For many programming languages, your IDE can really help
    you by completing code for you (with and particularly without the use of
    AI). Sometimes I’ve seen IDEs that are configured in a way that is too eager
    to auto-complete, and cause more distraction and trouble than they are
    worth.
  - Learn how to use multi-cursors
- \[B6\] Learn how to use your IDE to step-debug your code. Learn how to run
  your program with a step-debugger, and how to use its features.
  - Learn about breakpoints, including conditional breakpoints
  - Learn how to evaluate expressions
  - Take the time to configure your project so you can run it locally, but also
    learn how to do remote debugging (i.e. connect the debugger to an
    application running in a remote computer)
  - Learn about stepping in, stepping over, stepping out, “drop to frame” (and
    its limitations), code hot-swap (and its limitations)
- \[C5\] Learn how to use your IDE to profile your system, e.g. to locate
  performance bottlenecks

TODO: link to IntelliJ and VSCode

## 35. Version Control Systems: git

At this point, git is king of source control. It’s an incredibly powerful source
control system, but with a really clunky CLI. Learn it well.

Note: below, I’ll be using the nomenclature `main` (instead of the old name
`master`) to denote the trunk.

- \[B4\] Understand what a commit actually is
  - Could you, in principle, write your own version control system based on
    commits?
- \[B4\] Understand the difference between a pull and a fetch
- \[B4\] Understand how branches are just labels, and how to create and manage
  them
- \[B4\] Here’s a good visual resource for learning git internals:
  [interactive resource](https://learngitbranching.js.org/?locale=en_US)
- \[B6\] Understand how to look at history
  - Git log
  - Git reflog. And how to use that recover from disastrous mistakes
  - Git blame
- \[C5\] Understand how to use `git diff` to explore changes. Better yet, also
  understand how to configure `git difftool` with a good diffing tool (say meld,
  or using your IDE) and how you can use that to not only see differences, but
  also make changes
- \[C5\] Understand rebasing and merging from `main` to your local branch
  - Understand the difference between running a `git rebase main` and a
    `git merge main` on your local branch, and why you probably never want to
    run the merge command
  - Understand how to efficiently deal with merge conflicts
- \[C6\] Understand the difference between git itself and GitHub (or BitBucket
  or GitLabs or some other git hosting platform)
  - Understand that in git proper there is no concept of a Pull Request, and how
    these hosting platforms implement this using branches
    - Understand why these hosting platforms decided to introduce the concept of
      a Pull Request to encapsulate the concept a unit of change (rather than
      just use git’s native unit of change, which is a commit)
    - Understand how this introduction of PRs makes it clunky to stack multiple
      unmerged changes (i.e. what is known as stacked PRs); understand why you
      still want to know how to stack changes; understand how you can still do
      this stacking manually (even if it’s clunky); learn about tools (such as
      graphene) that automate this process
  - Understand why you often need to force-push (`git push \-f`) when using a
    git hosting platform
- \[C4\] Understand why it’s much safer to always commit against a branch (i.e.
  not commit to `main` directly)
- \[C4\] Understand the options you have to merge work done in a local branch to
  main: merge commit; squash and merge; rebase and merge
- \[C4\] Understand the difference between a merge commit (that has two parents)
  and a regular commit
- \[D3\] Learn about how you can use git bisect to, say, look for the commit
  that introduces a bug

## 36. Misc Tools for Developers

As mentioned elsewhere, it is important to learn about and use well your tools.
Here’s a few tools worthy of notice (not covered elsewhere in this doc).

- \[C4\] Tmux \[Linux / macOS\]. If you use the CLI (and you should) you want to
  learn about tmux and take the time to configure it
- \[D4\] Emacs / vi. It’s good to know how to at least do basic text editing
  over a term
- \[C4\] Learn how to use a good diff tool and a good merge tool (it could be
  the same)
- \[C5\] \[macOS\] Use homebrew. You can get your Mac Terminal (which I would
  use iTerm, really) to be a much more capable CLI
- \[C7\] \[Windows\] WSL. Ok, so Windows is not POSIX-compliant, but WSL
  (despite its limitations) is a pretty awesome way to bring a lot of the Linux
  power to Windows

## 37. Project Management

Software development is a team activity that takes place over extended periods
of time. It is important to understand the principles of software project
management, even if you are not the one in charge.

- \[C4\] Understand the issues that plague software development
  - Sometimes humor is the best way to convey a point, here’s a couple of such
    examples wrt project management
    - This [video talk](https://www.youtube.com/watch?v=saCdvksej0A) is
      painfully accurate: “Ignite\! 17th Century Shipbuild and Your Failed
      Software Project”
    - How Software Projects Really Work:
      [illustration](https://www.smart-words.org/jokes/project-tree-swing.png)
- \[C6\] Understand the pre-Agile history of project management, particularly
  the Waterfall model
  - Understand how Waterfall is still practiced in a handful of high-stake niche
    applications (such as aerospace, medical devices)

### Agile

See the section on “Project Management” above. Agile was invented as a reaction
to the issues of Waterfall, which was the prevalent way to develop before.

- \[B5\] Read the [Agile Manifesto](https://agilemanifesto.org/) and the linked
  [principles of agile](https://agilemanifesto.org/principles.html)
  - In fact, put a recurring event in your calendar to read this once every 2
    years or so
- \[C4\] Understand the similarities and differences between the main Agile
  frameworks, particularly Scrum, Kanban and XP (Extreme Programming)
- \[C6\] Understand how the following concepts are meant to be used (or not) by
  Scrum, Kanban and XP
  - Story Points
    - Planning poker
  - Retrospective
  - Daily stand-up
  - Sprint planning / Iteration planning
- \[C7\] Understand how these Agile frameworks are most very often
  mis-implemented in software development (particularly in corporations), and
  what problems that causes, which is often referred to as "Agile in Name Only"
  (AINO) or "Cargo Cult Agile"
  - Understand the term “cargo cult”, and why it is used to describe this
  - Afterwards, go back and re-learn how these frameworks and their concepts are
    actually supposed to be used. Keep in mind that you may have only ever
    encountered badly-implemented Agile, so even if you think you are familiar
    with all these, you need to find a good resource to learn “proper Agile”. I
    am reluctant to recommend something I haven’t read, but I’ve heard that one
    of the best is "Extreme Programming Explained: Embrace Change" by Kent Beck
    – which, though it focuses on XP, lays out the foundation for Agile (fwiw,
    XP is considered the most radical/pure Agile)

## 38. Build / Deployment / Production

TODO: this section is under development

- Build
- Canaries
- CI/CD
- Observability
- Monitoring

## 39. Artificial Intelligence (AI)

Love it or hate it (or both) AI has already become an important part of being a
software developer. There are three “hats” you may wear while interacting with
AI:

- As a user: e.g. when you use a chatbot to ask questions about an API, or use a
  code assistant in your IDE.
- As an integrator: e.g. when you integrate an LLM into a customer service
  chatbot
- As an AI developer: e.g. when you write your own LLM, or train a neural
  network

These are quite distinct, so let’s discuss each one separately

### Artificial Intelligence: As a User

- \[B4\] Learn how to use an LLM chatbot as an assist for learning and having a
  dialogue
  - Not for the blindly trusting
- \[B4\] Understand how to ask questions to minimize hallucinations
  - And understand that hallucinations are unavoidable
- \[C4\] Understand that an LLM chatbot / code assist can be quite good at
  describing what a method does, but not nearly as good at describing what the
  contract of the method should be (which is what you want the documentation to
  be)
- \[B4\] Understand how to use AI as your augmenter, not replacer
  - If you just blindly trust it, you are essentially saying it can replace you

### Artificial Intelligence: As an Integrator

- \[C4\] Understand how to do good prompt engineering to get the results that
  you want more often than not
- \[C4\] Understand the limits of what to expect from LLMs
  - That hallucinations are inevitable

### Artificial Intelligence: As an AI Developer

- \[B4\] Understand why games are the ideal way to train a neural network
- \[B4\] Understand how things have been gamified to make them more amenable to
  be trained on
- \[C4\] Understand the following terms, how they are similar and how they are
  different
  - ANN (Artificial Neural Network)
  - LLMs (Large Language Models)
  - CNN (Convolutional Neural Network)
  - RNN (Recurrent Neural Network)
  - GANs (Generative Adversarial Network)
  - GPT (Generative Pre-trained Transformer)
  - Attention-based transformers
  - Image classifiers
  - Weights and Biases / Backpropagation / Loss Function
  - Reinforcement learning
  - Training parameters
  - GPU / TPU

## 40. Health

This may seem like a weird topic for my document, but hear me out: to be a
seasoned software engineer, you need to be able to keep doing this work for
decades, giving time for your intuition to develop and to gain more experience.

Do not take health advice from me, but do seek out professional advice\!

- Understand that one of the most common issues that derail a career is
  health-related, like developing Repetitive Stress Injuries, or back problems
  - Understand how to mitigate RSI with an ergonomic mouse or mouse-alternative
    - I am particularly fond of
      [this](https://www.amazon.com/dp/B01936N73I?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_1&th=1)
      Kensington but try different options
  - Understand how to mitigate RSI with an ergonomic keyboard
    - I am particularly fond of
      [this](https://www.amazon.com/dp/B0F5YNL62D?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_1)
      Encase (from an old Microsoft design) but try different options
    - Some people really like
      [these](https://www.amazon.com/Kinesis-Advantage2-Ergonomic-Keyboard-KB600/dp/B01KR1C5PY/ref=sr_1_5?crid=1BTDFABFB9VO3&dib=eyJ2IjoiMSJ9.ycxtNtRjp_7ChpXBXXLXyHJ7TlPz-TvZVUNdggc_AfXBi9Xkn3m9Sg2rJBaw07U8aDADVVDk0xG89iio6xLhZBG9XssMmySRxnFqzbP9N4_FBeJOKlMNKDAFtuv_BHPgWqiv4j0_NSM6s_j1Pmgd9rgr8Amqc6bPAwYIN-qPL_VbSZ6NcMZMft97QSjOn-edg9a8sE0vVkTfJmi1co_K245BbfWCRWo3ie_eAd8IK2vZ4k7DbFzbHsNpz4s-YIsnF-ShFgX16aRuYmDmt8C6Gtn5km9T_0Vu3xCLddhszjE.aC4YPtY7mqC6jbdlU9pt3da4GKlFWSqaCtvlkAVOgCw&dib_tag=se&keywords=kinesis%2Bkeyboard&qid=1767931529&s=electronics&sprefix=kinesis%2Celectronics%2C264&sr=1-5&th=1)
      Kinesis keyboards; if they are to type regular text, I think they are
      awesome, but many programs have structured their keyboard shortcuts around
      the standard keyboard, and I found it clunky to use those
    - Some people swear by Dvorak keyboards. Again, as in the case above, many
      programs have structured their keyboard shortcuts around the standard
      keyboard, and I found it clunky to use those
  - Consider options with standing desks (or best, rising desks)
    - These days it’s not \_that\_ expensive to buy a rising desk, and many
      employers will even reimburse for ergonomic equipment. I use an
      [uplift](https://www.upliftdesk.com/?srsltid=AfmBOoqtnpgtSQKgZ90EU7shDgFSl-_VzNbgxLPL4uBbdWddXmZHdtDw),
      and I’m really happy with that
  - Go out of your way to learn keyboard shortcuts for common tasks. Beyond the
    health benefits, you’ll be more productive\!
  - You’ll likely spend a lot of time sitting down or at your desk
    - Learn about desk exercises
    - Figure out ways to incorporate physical activity in your workday
  - Do all these before you develop a health problem; it’s much harder after the
    problem manifests

## 41. Books and Resources

- “The Art Of Computer Programming” Knuth
  - One of the most compelling books I’ve ever read. Even the dated stuff is
    fascinating (like, a lot of book 2 is about algorithms to retrieve data from
    tape. Still relevant to your work? Unlikely. But awesome to read\!)
- “Design Patterns: Elements of Reusable Object-Oriented Software”
  [book](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612/ref=sr_1_1_sspa?crid=29YYD60CPR6OE&dib=eyJ2IjoiMSJ9.mTRaTOPYqsPcUsGD8aznte8IMQZZiYjv7_Xwyyi1iS2agVs4KLcx5qwmrKiyIxDiiaA6QbUY3MCBnb28lUrTGOw4rZYq2Lhf6z4JylQnbFuTfD6WMSKZ2izHndzfV-Ky9NmDl7WsksMgVxIlYFmG7iOkspV9gCvaWen0y-NgyAB5h9heo2aiCmVs-15_vB4oaJk39mlJ_DXQdKEmTKZAaisgf_stgMTzEpcnj8Ju6qc.UsxA9CKA92WPXqYKfZEDlzWh4BkKAfrgBstHbML-kUk&dib_tag=se&keywords=design+patterns&qid=1767328460&sprefix=design+patterns%2Caps%2C215&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1)
- Effective Java
  [book](https://www.amazon.com/Effective-Java-Joshua-Bloch/dp/0134685997/ref=sr_1_1?crid=11178DR3IEOMC&dib=eyJ2IjoiMSJ9.aEVmSGt9ra24VmlN-_LvktnyVdqdspa55_edw62NBSPexJX_-zu4CGuVvGA-WJTgQ2NEuFwpTs1vCNaNPigmKYFwxOfL2Z77abywUFer8fk2XQBaIsJ3TfuCVyilEw1INFIXZ-uyCrWncYV83Q2QjQ.LlgcEp5MMhvABIBs6uvqDLVAZJc7NpBD-8whsfwEtas&dib_tag=se&keywords=effective+java+4th+edition&qid=1767994280&sprefix=effective+java+%2Caps%2C240&sr=8-1)
- Effective TypeScript
  [book](https://www.amazon.com/Effective-TypeScript-Specific-Ways-Improve/dp/1098155068/ref=sr_1_1?crid=2J0FPORE2IDKS&dib=eyJ2IjoiMSJ9.3kCLpeeLsIL18j2GgNNS-XQ0btG0lak74ElAxyAWJU9atrjBInzjAoVHOHQQggwqOOHbw6Djc1wzien30a0hkLurIPPrAQA_-G3ol1DaiFFnCCjDA9pLoETKGH1GpPc6_9dM5ErmxIKdF7KB_J9phWeEEIGeN3ZZGW_2XerYtAHWeoeBTrkS3EYJw_4PtAQ16BU4A5paTangQDSstA2uVn9LqRBK0hqtc9GW0ifdGbM.-arxdgttWG0hW4tqZW1LsjY3-hkdhin4mTA97yLCl88&dib_tag=se&keywords=effective+typescript&qid=1767994345&sprefix=effective+typ%2Caps%2C190&sr=8-1)
- Testing on The Toilet blog

## 42. Contributing

This document is large and ambitious, and I expect it to need corrections and
revisions. I’m not an expert in every language and every subject, and – despite
my best efforts to check that all the information is correct – there’s a lot of
opportunity for error, and I’m happy to get input. Depending on what kind of
change you want to propose, follow the appropriate option below:

1. For typos, grammatical mistakes: just send a PR.
2. If there is objectively-incorrect information (say I claim that C is an
   interpreted language): just send a PR. If the error is subtle, please include
   a justification in the PR description
3. If you think that some item’s “importance/complexity” classification is a bit
   wrong, leave it be: these are subjective and approximate. If you think one is
   very wrong, and you think you got a good argument, again, send a PR with a
   justification
4. For larger changes, ideas of important topics I may have missed, changes to
   subjective/opinion etc I suggest you start a conversation first – this could
   be through a PR if that is the easiest way to explain your idea, or though an
   issue report

For any of these, keep PRs as small as reasonable: do not fix more than one
thing, and keep each change constrained to a small section of the doc, if at all
possible.

## 43. Version History / Changelog

2026 Jan 10 – Version 1 (by Zorzella)
