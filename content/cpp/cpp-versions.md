---
title: C++ Versions
tags:
-   cpp
---

# C++ evolution through the years

## Pre 98
**Early evolution**:
-    Bjarne Stroustrup started development of C++ in 1979 at Bell Labs as an enhancement to the C
language. It was originally named C with Classes but later it was renamed C++ in 1983.

**C with class**:
-    **Classes**: Introduced user-defined types that encapsulate data and related functions.
-    **Objects**: Allows creation of objects from classes.
-    **Data abstraction**: Enabled separation of interface(public members) and implementation(private
members).
-    **Member functions**: Functions that can be defined within the class definition and can access
the class's private and public members.
-    **Inheritance**: Creation of new classes based on existing classes.
-    **Constructors & destructors**
-    **Operator overloading**
-    **Type checking** during compilation
-    **Inline functions**

## C++ 98
The first standardised version of the C++ language. Provided a consistent definition of the
language that all compilers could adhere to.

**Features**:
-    **Templates**: Allowed definition of generic classes and functions making code more reusable
and flexible.
-    **STL**: The standard template library - a powerful library of template classes and functions.
-    **Namespaces**: Help organise code and prevent naming conflicts.
-    **Exceptions**: Provide a way to handle error conditios separate to the main flow of program
control.
-    **New casts**: (dynamic_cast, static_cast, reinterpret_cast, const_cast) Safer and more precise
alternative to C-style casts.
-    **Boolean type**: 'true' and 'false'
-    **RTTI**: Run-Time Type Information. Allows information about object's type to be retrieved
during runtime.
-    **'auto_ptr' Smart Pointer**: Early version of the smart pointer
-    **Internationalisation support**: Provided by the `<locale>` library.

## C++ 03
Essentially a 'bug fix' version of C++98. Did no introduce any major new features but focused on
correcting issues and ambiguities identified in C++98 standard.

The few minor features included were:
-    **Value initialisation**: Used to ensure objects are intialised even if no explicit initialiser
is provided.
-    **Library extensions**: STL was expanded with new functions and existing ones improved.
-    **Exception specifications**: Clarifications to how exception specs worked. Included "throw
nothing" by using `throw()`.
-    **Keyword `export`**: Difficult to implement and seldom used. Was since removed in C++11.

## C++ 11
Major update to C++ that had a host of new features and improvements. It was a significant
milestone in the evolution of C++ and made the language more modern, safer and expressive. It
changed the way programmers wrote code and improved perfomance of C++ applications.

The changes were significant enough that people refer to modern C++ as a different language to
compared to pre-C++11.

-    **Rvalue references and Move semantics**: Allows 'moving' resources instead of copying them.
Can significantly imporove performance, particularly with alrge data structures.
-    **Smart pointers**: New memory management tools: `shared_ptr`, `unique_ptr` and `weak_ptr`
-    **Auto keyword**: Allows automatic type deduction which can make code more readable and easier
to maintain.
-    **Nullptr keyword**: Replaces the ambiguous `NULL`.
-    **Range-based for loops**: Simpler syntax to iterate over collections.
-    **Initialiser lists**: A new way to initialise objects allowing more compact and intuitive code.
-    **Lambda expressions**: Feature borrowed from functional languages that make it easier to use
function objects.
-    **Concurrency support**: Native support for multithreading including threads, locks and condition
variables.
-    **Type inference**: The `decltype` keyword was introduced, which deduces the type of an
expression
-    **Strongly typed enums**: `enum class` was introduced which is more type-safe than normal enums.
-    **Deleted and defaulted functions**: Allows for default generation of constructor and assignment
functions and to delete them when not required.
-    **Variadic templates**: Allows creation of functions and classes with arbitrary number of
template parameters in a type-safe way.
-    **User defined literals**: Enables more readable code by allowing user defined literals.

## C++ 14
A more minor release in comparison to C++11.

-    **Generalised lambda expressions**: Allows lambdas to deduce the return type of functions and
introduced generalised capture, which allows capturing of variables by move.
-    **Binary literals**: Allows binary literals to be specified using the `0b` prefix.
-    **Function return type deduction**: The compiler can now deduce the return type of a function.
-    **Extended constexpr**: Extended `constexpr` to allow more functions to be evaluated at compile
time.
-    **Variable templates**: Allows definition of variables using template parameters.
-    **Relaxed constraints on constexpr functions**: constexpr functions can now include loops,
switches etc, allowing for more complex compile time computations.
-    **Deprecation of auto_ptr**: `auto_ptr` deprecated and replaced by `unique_ptr`
-    **Generic lambdas**: lambas can take auto type parameters, making them polymorphic.
-    **Standard user-defined literals**: Allows defining of new literal ==suffixes==. It is now
possible to represent 5 seconds with something like `5_s` now.
-    **\[\[deprecated]] Attribute**: Can no mark code as deprecated to show code should not be used.
-    **Improved STL**: addtional extensions to the STL.

## C++ 17
Neither a small or large update to C++. Many new language features introduced, library components,
and improved performance in certain areas.

C++17 contiued the modernisation of C++, focusing not just on performance but also on simplifying
the language, improving its consistency, and making it more expressive. Its impact on performance
and idiomatic C++ are seen in the adoption of new practices that leverage these features, which
provide more compile-time checks, clearer intentions, and better abstractions.

-    **Structured bindings**: allows declaration of multiple variables initialised from a tuple or
struct in a single statement. Makes code more compact and readable.
-    **If and Switch with initialiser**: can now declare a variable in the same statement as an if or
switch, reducing scope and making code cleaner.
-    **Inline variables**: Similar to inline functions, inline variables can be defined in headers
and included in multiple files without violating one definition rule.
-    **Fold expressions**: simplifies usage of variadic templates by allowing operations to be
performed on all elements of a parameter pack.
-    **constexpr if (Compile-time if)**: allows conditional compilation based on template parameters,
eliminating the need for template specialisations in many cases.
-    **Template arugment deduction for class templates**: allows template class instantiation without
explicitly specifying the template arguments.
-    **std::optional, std::variant, and std::any**: provides better ways to handle optional values,
variant types, and type-safe unions respectively.
-    **Improved and expanded STL**: numerous additions such as the filesystem library, parallel
algorithms, new string conversion functions and more...
-    **Nested namespaces**: allows nesting of namespaces in a single statement.
-    **Removal of deprecated features**: removed features such as std::auto_ptr, std::random_shuffle,
and the register keyword.
-    **New attributes**: new standard attributes like \[\[fallthrough]], \[\[nodiscard]],
and \[\[maybe_unused]] were added to communicate intent more clearly.
-    **Direct list initialisation of enums**: allows more type-safe code by allowing enums to be
directly list-initialised.

## C++ 20
A major update that brought an abundance of powerful and expressive features to the language. It
is considered one of the most significant updates to the C++ standard, comparable to C++11 in the
breadth and depth of its changes. C++20 strides towards making the language safer, simpler more
efficient, and more expressive, resulting in better performance and more idiomatic code.

-    **Concepts**: new form of compile-time duck typing. Represents named set of requirements such as
syntactic requirements, semantic requirements, and type requirements.
-    **Ranges**: new library that provides components for handling ranges of values. Builds upon the
iterator concept allowing for more expressive code.
-    **Coroutines**: Generalisation of subroutines. Used for computations that can be suspended and
resumed. This can lead to more efficient and simpler asynchronous code.
-    **Modules**: New way to package code which can lead to faster compilation times, improved
encapsulation and isolation, ease of use, and better tooling.
-    **Three-way comparison (Spaceship) operator `<=>`**: Simplifies writing comparison operators for
user defined typed.
-    **Calendar & Timezone library**: New standard library to handle dates, times, and timezones.
-    **Format library**: New type-safe printf-like library for text formatting.
-    **Expanded constexpr**: more of the STL can be used in constexpr contexts.
-    **New standard attributes**: Likely and unlikely attributes were added to give the programmer the
ability to provide compiler with branch prediction information.
-    **constexpr dynamic allocation**: Allows dynamic allocation in consexpr contexts with limitations
to ensure compuations are still performed at compile time.
-    **Feature-test macros:**: Macros that test whether a certain feature is available in current C++
environment.
-    **std::span**: A new object to provide a lightweight, non-owning reference to a sequence, or a
part of a sequence.

## C++ 23
The latest update to C++. Seems like this update fully achieves what C++20 set out to do. This
probably means it does not count as one of the land mark C++ updates, but still not a small one.

**Core language changes:**
-    **Deducing `this`**:
-    **if consteval**:
-    **Attributes for lambdas**:
-    **std::size_t literals**:
-    **auto(x) decay-copy in the language**:
-    **#elifdef, #elifndef, and #warning**:
-    **std::unreachable**:
-    **Assumptions**:
-    **Named universal character escapes**:
-    **Trim whitespace before line splicing**:
-    **static operator()**:

**C++ Standard Library:**
-    **String formatting improvements**:
-    **STL modules**:
-    **std::flat_(multi)map and std::flat_(multi)set**:
-    **std::mdspan**:
-    **std::generator**:
-    **basic_string::contains and basic_string_view::contains**:
-    **construct string_view from nullptr**:
-    **basic_string::resize_and_overwrite()**:
-    **Monadic interface for std::optional**:
-    **std::stacktrace**:
-    **Changes to Ranges library**:
-    **Changes to Views library**:
-    **std::expected**:
-    **std::move_only_function<>**:
-    **std::spanstream**:
-    **std::byteswap**:
-    **std::to_underlying**:
-    **Associative containers heterogeneous erasure**:

**Others (not sure)**:
-    **std::out_ptr, std::inout_ptr**:
-    **constexpr std::unique_ptr**:
-    **std::print**:
-    **Formatted ranges**:
-    **std::is_scoped_enum**:
-    **Multi-dimenstional index operator**:
-    **constexpr for cmath**:
