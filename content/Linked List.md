---
title: Linked List
tags:
  - "#DS"
---
**Basic interface**

```cpp
template <typename T>
class LinkedList {
public:
    // constructors
    LinkedList();
    LinkedList(const LinkedList& other);
    LinkedList(LinkedList&& other);

    // assignment operators
    LinkedList& operator=(const LinkedList& other);
    LinkedList& operator=(LinkedList&& other);

    // destructor
    ~LinkedList();

    // accessors
    T& front();
    const T& front() const;
    T& back();
    const T& back() const;

    // capacity
    std::size_t size() const;
    bool empty() const;

    // modifiers
    void push_front(const T& value);
    void push_back(const T& value);
    void pop_front();
    void pop_back();
    void clear();

    void insert(int index, const T& value);
    void remove(int index);

private:
    struct Node {
        T data;
        Node* next;
        Node* prev;
    };

    Node* head;
    Node* tail;
    int theSize;
}
```
