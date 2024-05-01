---
title: Deque
tags:
  - "#DS"
---
**Basic interface**

```cpp
template <typename T>
class Deque {
public:
    // constructors
    Deque();
    Deque(const Deque& other);
    Deque(Deque&& other);

    // destructor
    ~Deque();

    // accessors
    T& front();
    const T& front() const;
    T& back();
    const T& back() const;
    T& operator[](int index);
    const T& operator[](int index) const;
    T& at(int index);
    const T& at(int index) const;

    // capacity
    int size() const;
    bool empty() const;

    // modifiers
    void push_front(const T& value);
    void push_back(const T& value);
    void pop_front();
    void pop_back();
    void emplace_front(const T& value);
    void emplace_back(const T& value);
    void clear();
};
```
