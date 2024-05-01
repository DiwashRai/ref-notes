---
title: ""
tags:
  - random
---
**Basic interface**

```cpp
template <typename K, typename V>
class HashMap {
public:
    // constructors
    HashMap();

    // destructor
    ~HashMap();

    // accessors
    V& operator[](const K& key);
    const V& operator[](const K& key) const;
    V& at(const K& key);
    const V& at(const K& key) const;
    bool contains(const K& key) const;

    // capacity
    int size() const;
    bool empty() const;

    // modifiers
    void insert(const K& key, const V& value);
    void remove(const K& key);
    void clear();
};
```