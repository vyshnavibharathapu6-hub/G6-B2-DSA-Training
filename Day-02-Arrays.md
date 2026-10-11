# Day 02 — Arrays

**Training Group:** G6-B2  
**Topic:** Arrays  
**Programming Language:** Python

## 1. Introduction to Arrays

An array is a data structure used to store multiple elements in an ordered sequence. In Python, lists are commonly used for array-based problems because they can store multiple values and support indexing.

### Example

```python
arr = [10, 20, 30, 40, 50]

print(arr)
print(arr[0])
print(arr[2])
```

**Output:**
```text
[10, 20, 30, 40, 50]
10
30
```

**Explanation:**
- `arr` stores multiple elements.
- Indexing starts from `0`.
- `arr[0]` accesses the first element.
- `arr[2]` accesses the third element.

## 2. Array Traversal

Traversal means visiting each element of an array one by one.

### Python Code

```python
arr = [10, 20, 30, 40, 50]

for i in range(len(arr)):
    print(arr[i])
```

**Output:**
```text
10
20
30
40
50
```

**Explanation:**
- `len(arr)` returns the number of elements.
- `range(len(arr))` generates the valid indices.
- Each element is accessed using its index.

## 3. Insertion of an Element

Insertion means adding a new element to an array. Python lists provide the `insert()` method to add an element at a specified index.

### Python Code

```python
arr = [10, 20, 40, 50]

arr.insert(2, 30)

print(arr)
```

**Output:**
```text
[10, 20, 30, 40, 50]
```

**Explanation:**
- `insert(index, value)` adds an element at the given index.
- Existing elements from that position are shifted to the right.

## 4. Deletion of an Element

Deletion means removing an element from an array. The `pop()` method removes an element at a specified index and returns it.

### Python Code

```python
arr = [10, 20, 30, 40, 50]

arr.pop(2)

print(arr)
```

**Output:**
```text
[10, 20, 40, 50]
```

**Explanation:**
- `pop(2)` removes the element at index `2`.
- The remaining elements retain their order.

## 5. Searching in an Array

Searching is the process of finding whether a particular element exists in an array.

### Python Code — Linear Search

```python
arr = [10, 20, 30, 40, 50]
target = 30

for i in range(len(arr)):
    if arr[i] == target:
        print("Found at index", i)
        break
else:
    print("Not found")
```

**Output:**
```text
Found at index 2
```

**Explanation:**
- Each element is compared with the target.
- If a match is found, its index is displayed.
- If no element matches, the `else` block prints `Not found`.

**Time Complexity:** O(n) in the worst case.

## 6. Finding the Maximum and Minimum

The maximum is the largest element, while the minimum is the smallest element in an array.

### Python Code

```python
arr = [25, 10, 45, 5, 30]

print("Maximum:", max(arr))
print("Minimum:", min(arr))
```

**Output:**
```text
Maximum: 45
Minimum: 5
```

**Explanation:**
- `max(arr)` returns the largest element.
- `min(arr)` returns the smallest element.
- Both operations take O(n) time for a list of n elements.

## 7. Reversing an Array

Reversing means arranging the elements in the opposite order.

### Python Code

```python
arr = [10, 20, 30, 40, 50]

arr.reverse()

print(arr)
```

**Output:**
```text
[50, 40, 30, 20, 10]
```

**Explanation:**
- `reverse()` reverses the list in place.
- It modifies the existing list instead of creating a new one.

## 8. Sorting an Array

Sorting means arranging elements in ascending or descending order.

### Python Code

```python
arr = [40, 10, 50, 20, 30]

arr.sort()
print("Ascending:", arr)

arr.sort(reverse=True)
print("Descending:", arr)
```

**Output:**
```text
Ascending: [10, 20, 30, 40, 50]
Descending: [50, 40, 30, 20, 10]
```

**Explanation:**
- `sort()` arranges elements in ascending order by default.
- `sort(reverse=True)` arranges elements in descending order.
- Python's list sorting takes O(n log n) time in the worst case.

## 9. Finding the Sum of Array Elements

The sum of an array is the total obtained by adding all its elements.

### Python Code

```python
arr = [10, 20, 30, 40, 50]

total = sum(arr)

print("Sum:", total)
```

**Output:**
```text
Sum: 150
```

**Explanation:**
The `sum()` function adds all the numeric elements in the list. Its time complexity is O(n).

## 10. Time Complexity of Common Array Operations

| Operation | Typical Time Complexity |
|---|---|
| Access by index | O(1) |
| Traversal | O(n) |
| Linear search | O(n) |
| Insert at the beginning | O(n) |
| Delete from the beginning | O(n) |
| Append at the end | O(1) amortized |
| Sorting | O(n log n) |

These complexities describe typical Python list behavior for the stated operations.
