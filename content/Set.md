---
title: Set
tags:
  - "#DS"
---
**Basic interface**

```cpp
template <typename T>
class Set {
public:
    // constructors
    Set();

    // destructor
    ~Set();

    // modifiers
    void insert(const T& value);
    void remove(const T& value);
    void clear();

    // Operations
    bool contains(const T& value) const;
    T* find(const T& value) const;
    int count(const T& value) const;

    // capacity
    int size() const;
    bool empty() const;
};
```
