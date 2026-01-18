# Languages

We'll discuss some General Programming Languages that are important as of 2020s
in their historical context. This document makes most sense when read from the
beginning.

The "popularity", we'll use the
[TIOBE index](https://www.tiobe.com/tiobe-index/). We'll focus on the top
General Programming Languages, with a couple of exceptions.

The idea here is that understanding the historical context, you may be able to
better understand the phylosophies/limitations/strengths/shortcomings of each
language.

## C (1970s)

We'll start our journey with the "C" language, created in the 1970s. You can
think of it as an alternative to writing assembler, that is more portable, more
readable, more maintainable, but that still gives you a very close abstraction
to the actual hardware. In most cases (and with a good compiler optimizer) you
can get C to run as fast as assembler; and, for all practical purposes, probably
faster.

The language spec is quite small, even if you count the C-preprocessor.

But, for "modern" standards, C is quite weird, and, with its manual memory
allocation and deallocation, very easy to write code that is buggy and
vulnerable to exploits. You can also do pretty much anything you can do in
assembler – you can even mess with the memory stack (not just the heap).

The language syntax is messy, and the C-preprocessor makes it even messier.

But it's not a mere historical artifact: the world today still runs on C: it is
arguably the most important/consequential programming languages ever created.

Compilation has these four steps:

1. pre-processor: essentially converts C code into C code, e.g. like a very
   capable "search-and-replace".
2. parser: reads C code and creates an in-memory AST representation of it
3. compiler/optimizer: compiles the AST into machine code (for a particular CPU
   architecture etc), producing "obj" binary files
4. linker: gets multiple "obj" files and creates an executable file (or some
   other thing, such as a shared library file)

## C++ (1980s)

Our next stop is C++, which brought object orientation to C, allowing for code
to be more modular, where parts can hide their internals from code at large. C++
established object orientation as the dominant programming paradigm for decades
to come.

C++ is very compatible with C: C++ code can call C; C code can call C++ (with
some effort); their binary formats are compatible, and their compiled "obj"
files are also compatible and can be linked.

C++ has a much larger spec than C, and much larger standard library. It also
introduced  
many advanced features like operator overloads and (later on) templating.

The language is even messier than C, though, but it its motto has been of
“zero-cost abstraction” – i.e. have ways to create abstractions without
incurring performance penalties.

Templating is a good example of a “zero-cost abstraction”: it accomplishes
something similar to "generics", but contrary to how this is implemented in most
other languages, this is not a runtime abstraction – everything about templating
is dealt with at compile-time.

Note that while the C language itself has not changed as much, C++ has evolved
dramatically, and many features of C++ (such as templates) were added years or
decades after the language first came out.

## Java (1990s)

Java's primary goal was the idea of "write once, run anywhere", i.e. to make the
compiled code portable. For that, it used the concept of an intermediate binary
form, that was not tied to a particular CPU architecture.

There were, of course, interpreted languages that allowed for portability, but
Java could achieve much better performance than those, since it was a compiled
language. And, soon after, it got even better when the JVM runtime got a smart
Just-In-Time compiler that could optimize code for a particular hardware on the
fly.

Java didn't invent all the innovations I'm about to list, but it definitely
popularized them, and got them all bundled in a nice cohesive ecosystem. Here's
a list of innovations:

- memory management with a garbage collection
- memory safety (e.g. no way to access un-owned memory, zero-initialization of
  memory)
- portability (both source code and compiled code)
- threading support built in the language, including the "happens-before"
  semantic that eventually got adopted by pretty much every other language
- good standard library support for collections
- good standard library support for networking (including HTTP)
- good language support for internationalizable Strings
- packages/imports for visibility and namespacing/organization
- good language support for exceptions

The list goes on.

It also was familiar: it borrowed much syntax from C/C++, but at the same time
it fixed many of the warts.

Java evolution was also very well-managed: features were introduced in a way
that (most of the time) played well with the rest of the language, the language,
binary and runtime were kept very backwards-compatible.

All in all, it got so many things right it ended up crowding out many other
languages (Smalltalk, Eiffel etc).

With the boom of the internet, it was the right language for the right time,
which propelled Java to the top-5 in its first year, where it still stays.

Essentially, if you needed something ultra-fast, you chose C/C++, otherwise
Java... well, except for JavaScript. Let's cover that next.

Funny thing about Java, though – it was really meant to be a language of choice
for desktop applications, but it really took on as a server-side language. And
it didn't get much traction in the desktop... until Android, that is...

## Javascript (1990s)

JavaScript was introduced just a bit after Java. The name itself is widely
considered to be a marketing ploy by Netscape.

It is an interpreted, initially only meant for running in the browser, adding
simple functionality to static web pages.

Over time, it became more capable, and browsers became more capable, and people
started figuring out ways to make JavaScript do very complex things.

The language is messy and full of warts, but it has two things going for it that
kept it as a top language for decades:

- it can run in (just about) every web browser
- it is the only language that can run in (just about) every web browser

With the success of the web, and until if/when some other language comes along
that runs on every browser, expect JavaScript to stay very relevant.

JavaScript is also one of the few languages that is optimized for being a
language for building UI. Noteworthy:

- it plays very well with an event-driven world, which is very suitable for UI
  development
- the "(pretty much) all I/O is async" model of JavaScript also allows it to be
  single-threaded, which simplifies many things (e.g. no need for thread-safe
  data structures). And, despite the limitations that comes along with it being
  single-threaded, JavaScript is still very capable

Eventually, JavaScript also started playing a role on servers. We'll cover this
topic a little more when we talk about TypeScript.

## C# (2000s)

Microsoft saw the success of Java as a threat, and released C# as a version of
Java they could control.

C# copied many of Java's features, but they also built on some of the lessons
that could be learned by looking at Java's shortcomings, including fixing some
issues and adding some features to allow for better performance, e.g.:
pass-by-reference and value types (structs), which allows for writing code that
is less taxing on the garbage collector.

It also moved fast, rapidly adding features, including support for generics.
Java had to catch up with many of these innovations (including generics). And,
in some cases (e.g. the struts) it is still actively working on this
catching-up.

Despite its beginnings as a part of the Microsoft ecosystem, it gradually became
available in more platforms; eventually (2016) the language was open-sourced,
and it has some highly-visible usage (e.g. in Unity).

Note how the basic C syntax has been a dominant force: e.g. the following line
of code is valid in C, C++, Java, JavaScript and C# (e.g. all languages we
discussed so far):

```
for (int i = 0; i < 10; i++) {
```

## Python (1990s, 2000s)

Python first appeared in the late eighties, but note that the syntax kept
evolving in a way that wasn't always backwards compatible. The last big
non-backwards-compatible change, was with Python 3.0, released in 2008.

It is a very capable scripting language, and its roots as open-source from the
beginning helped it gain traction.

It focused on what was perceived to be clutter in the code, ditching semicolons
and curly-braces, and also (at first) any kind of type declaration (a feature
added late with Python 3).

Python has displaced other contenders for scripting, like Perl, Visual Basic,
Lua, Tcl/TK, and Lisp.

The scripting nature holds it back in performance, but makes for a compelling
interactive experimentation model. It became beloved in academics, including
math departments, and it slowly climbed the popularity index to the top, riding
on its de-facto position as being _the_ language for gluing and interacting with
Artificial Intelligence.

## Kotlin (2010s)

Sometimes billed as a "better Java", it is fully compatible with Java, runs on
the JVM and benefits from the entire Java ecosystem of libraries and tooling. It
also got a big boost from replacing Java as the recommended language to write
Android code.

It is very feature rich, and (a bit like C#, but in a very different way) is
causing Java itself to modernize.

## Rust (2010s)

To be honest, it feels sad that, decades years after both C and C++ were
introduced, and despite all of their shortcomings, C/C++ are the only choices
used to write Operating Systems. That is because none of the "alternatives"
could match it in performance.

Then comes along Rust, with the goal to be a way to write code that needs to
have the kind of control/performance that C/C++ provides, but with a clean
syntax, and memory safety guarantees.

As Rust starts to be used in the Linux Kernel (and modern OSs like Fuchsia and
RedoxOS), it is proving that its model works, and is being adopted more broadly
as a replacement, not only of C/C++, but also of the alternatives (like Go and
Swift).

If its model continues to be validated, Rust is likely to be one of the most
consequential languages for the foreseeable future.

## TypeScript (2010s)

Considering JavaScript's position as "the browser language", and considering
JavaScript's shortcomings, TypeScript is meant to make JavaScript more readable
and maintainable, while still being JavaScript.

With the introduction of types and other construct cleanups, it also makes it a
more viable server-side language - though being interpreted and single-threaded
means it is not a performant language.
