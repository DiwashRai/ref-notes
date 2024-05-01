---
title: Heap
tags:
  - "#DS"
---
**Basic interface**

```cpp
template <typename T>
class Heap {
public:
    // constructors
    Heap();
    Heap(const Heap& other);
    Heap(Heap&& other);

    // assignment operators
    Heap& operator=(const Heap& other);
    Heap& operator=(Heap&& other);

    // destructor
    ~Heap();

    // accessors
    T& top();
    const T& top() const;

    // capacity
    int size() const;
    bool empty() const;

    // modifiers
    void push(const T& value);
    void pop();
    void emplace(const T& value);
    void clear();
};
```
