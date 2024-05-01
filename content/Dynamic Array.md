---
title: Dynamic Array
tags:
  - "#DS"
---
**Basic interface**

```cpp
template <typename T>
class Vector {
public:
    // constructors
    Vector();
    Vector(int size);
    Vector(int size, const T& initial);
    Vector(const Vector& other);
    Vector(Vector&& other);

    // assignment operators
    Vector& operator=(const Vector& other);
    Vector& operator=(Vector&& other);

    // destructor
    ~Vector();

    // accessors
    T& operator[](int index);
    const T& operator[](int index) const;
    T& at(int index);
    const T& at(int index) const;
    T& front();
    const T& front() const;
    T& back();
    const T& back() const;
    T* data();
    const T* data() const;

    // capacity
    int size() const;
    int capacity() const;
    bool empty() const;

    // modifiers
    void reserve(int new_capacity);
    void resize(int new_size);
    void push_back(const T& value);
    void pop_back();
    template <typename... Args>
    void emplace_back(Args&&... args);
    void clear();

    // Iterator support
    T* begin();
    const T* begin() const;
    T* end();
    const T* end() const;
};
```
