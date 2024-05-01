---
title: std::variant
tags:
  - "#cpp"
---

### Summary
`std::variant` is a type-safe union and was added as part of C++17. It's a class template that can
hold values of different types but only one at a time. It is similar to `std::any` but it can only
hold types that are specified in the template parameters.

Before `std::variant`, developers would use unions to hold different types. However, unions are
unsafe because they don't keep track of the type of the value they hold. This means that you can
accidentally read the wrong type of value from a union. `std::variant` solves this problem by
keeping track of the type of the value it holds.

### Typical usage

#### database query results
consider a function that performs a database query. It might return the query results on success,
an error message on failure, or a boolean value indicating no results found. This function could
return a std::variant holding either query results, a string, or a boolean.

```cpp
std::variant<QueryResults, std::string, bool> query_db(const std::string& query) {
  // ...
}
```

#### Abstract syntax tree
Another typical usage of std::variant is to hold different kinds of nodes in a tree-like data
structure, like an abstract syntax tree (AST) in a compiler. Each node could be a different
std::variant representing different types of statements or expressions in the language.

### Examples

#### Basic usage
```cpp
#include <iostream>
#include <variant>

int main() {
  std::variant<int, float> v;
  v = 12;
  std::cout << std::get<int>(v) << '\n';
  v = 3.14f;
  std::cout << std::get<float>(v) << '\n';
}
```
#### std::bad_variant_access
Calling `std::get` with the wrong type will throw a `std::bad_variant_access` exception.
```cpp
std::variant<int, float> v;
try {
  std::cout << std::get<float>(v) << '\n';
} catch (const std::bad_variant_access& e) {
  std::cout << e.what() << '\n';
}
```

#### std::get_if
Use `std::get_if` to get a pointer to the value held by a variant.
```cpp
std::variant<int, float> v;
if (auto pval = std::get_if<int>(&v)) {
  std::cout << *pval << '\n';
} else {
  std::cout << "v does not hold an int\n";
}
```

#### std::holds_alternative
You can use `std::holds_alternative` to check if a variant holds a specific type.
```cpp
std::variant<int, float> v;
if (std::holds_alternative<int>(v)) {
  std::cout << "v holds an int\n";
} else {
  std::cout << "v does not hold an int\n";
}
```
