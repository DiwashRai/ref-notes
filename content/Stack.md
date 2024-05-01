---
title: Stack
tags:
  - "#DS"
---
**Basic interface**

```cpp
template <typename T>
class Stack {
public:
    // constructors
    Stack();
    Stack(const Stack& other);
    Stack(Stack&& other);

    // assignment operators
    Stack& operator=(const Stack& other);
    Stack& operator=(Stack&& other);

    // destructor
    ~Stack();

    // accessors
    const T& top();

    // capacity
    std::size_t size() const;
    bool empty() const;

    // modifiers
    void push(const T& value);
    void pop();
    template <typename... Args>
    void emplace(Args&&... args);
    void clear();

private:
    Vector<T> data;
};
```
