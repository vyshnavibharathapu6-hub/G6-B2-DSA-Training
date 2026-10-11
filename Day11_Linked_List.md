# Day 11 – Singly Linked List (SLL)

## 1. Introduction

A Singly Linked List (SLL) is a linear data structure made up of nodes. Each node contains data and a reference to the next node.

The last node points to `None`.

### Structure

```text
10 → 20 → 30 → None
```

## 2. Creating a Node in Python

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

head = Node(10)
head.next = Node(20)
head.next.next = Node(30)
```

## 3. Traversal of SLL

Traversal means visiting and printing each node from the beginning to the end.

```python
def traverse(head):
    current = head
    while current:
        print(current.data, end=" ")
        current = current.next

traverse(head)
```

**Output:**
```text
10 20 30
```

## 4. Key Points

- Each node contains data and a next reference.
- `head` points to the first node.
- The last node points to `None`.
- Nodes are connected using references.

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

def traverse(head):
    temp = head
    while temp:
        print(temp.data, end=" ")
        temp = temp.next

def insert_begin(head, data):
    new = Node(data)
    new.next = head
    return new

def insert_end(head, data):
    new = Node(data)
    if not head:
        return new
    temp = head
    while temp.next:
        temp = temp.next
    temp.next = new
    return head

def insert_pos(head, data, pos):
    if pos < 1:
        return head
    if pos == 1:
        return insert_begin(head, data)
    temp = head
    for _ in range(pos - 2):
        if not temp:
            return head
        temp = temp.next
    if not temp:
        return head
    new = Node(data)
    new.next = temp.next
    temp.next = new
    return head

def delete_begin(head):
    return head.next if head else None

def delete_end(head):
    if not head or not head.next:
        return None
    temp = head
    while temp.next.next:
        temp = temp.next
    temp.next = None
    return head

def delete_value(head, key):
    if not head:
        return None
    if head.data == key:
        return head.next
    temp = head
    while temp.next and temp.next.data != key:
        temp = temp.next
    if temp.next:
        temp.next = temp.next.next
    return head

def search(head, key):
    temp = head
    while temp:
        if temp.data == key:
            return True
        temp = temp.next
    return False

head = Node(10)
head.next = Node(20)
head.next.next = Node(30)

traverse(head)
print()
head = insert_begin(head, 5)
head = insert_end(head, 40)
head = insert_pos(head, 15, 3)
head = delete_begin(head)
head = delete_end(head)
head = delete_value(head, 20)
print(search(head, 30))
traverse(head)
```
