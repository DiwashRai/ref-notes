---
title: "CMake"
tags:
-   tools
---

## building and existing project cheatsheet

vcpkg toolchain file if needed:
```
cmake -B <build dir> -S <source dir> -DCMAKE_BUILD_TYPE=Debug -DCMAKE_TOOLCHAIN_FILE=<path to vcpkg>/scripts/buildsystems/vcpkg.cmake
cmake --build <build dir>
```

## Modern CMake in a nutshell

- Declare your module with ADD_LIBRARY or ADD_EXECUTABLE  
- Declare your build flags with TARGET_xxx()  
- Declare your dependencies with TARGET_LINK_LIBRARIES  
  - Works for linking directly to libary
  - and for linking to module with a project with interface
- Specify what is public and private

### Global setup

- Use at least version 3.0
- Some flags should still be declared at the top level that you want everywhere. E.g. -Wall -Werror

```cmake
cmake_minimum_required(VERSION 3.0)

if (MSVC)
    add_compile_options(/W3 /WX)
else()
    add_compile_options(-W -Wall -Werror)
endif()
```

### Delcare your module

```cmake
add_library(mylib
    src/file1.cpp
    src/file2.cpp
    ...)
```

### Declare your flags

```cmake
target_include_directories(mylib PUBLIC include)
target_include_directories(mylib PRIVATE src)

if (SOME_SETTING)
    target_compile_definitions(mylib
            PUBLIC WITH_SOME_SETTING)
endif()
```

### Declare your dependencies

```cmake
# Public (interface) dependencies
target_link_libraries(mylib PUBLIC abc)

# Private (implementation) dependencies
target_link_libraries(mylib PRIVATE xyz)
```

### Header-only libraries

```cmake
add_library(mylib INTERFACE)

target_include_directories(mylib INTERFACE include)

target_link_libraries(mylib INTERFACE Boost::Boost)
```

## Anti-patterns

- Don't use macros that affect all targets
  - INCLUDE_DIRECTORIES()
  - ADD_DEFINITIONS()
  - LINK_LIBRARIES
- Don't use TARGET_INCLUDE_DIRECTORIES() with a path outside your module
- Don't use TARGET_LINK_LIBRARIES() without specifying PUBLIC, PRIVATE or INTERFACE
- Don't use TARGET_COMPILE_OPTIONS() to set flats that affect the ABI

