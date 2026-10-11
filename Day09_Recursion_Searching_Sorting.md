# Day 09 – Recursion in Searching and Sorting

## 1. Introduction to Recursion

Recursion is a programming technique in which a function calls itself to solve a problem by breaking it into smaller subproblems.

### Important Terms
- **Base Case:** The condition that stops recursion.
- **Recursive Case:** The part where the function calls itself.
- **Call Stack:** Stores information about active function calls.

### Example
```python
def count(n):
    if n == 0:
        return
    print(n)
    count(n - 1)

count(5)
```

**Output:**
```text
5
4
3
2
1
```

## 2. Recursion in Searching

### A. Binary Search Using Recursion

**Definition:** Binary Search finds an element in a sorted array by repeatedly dividing the search range into two halves.

**Steps:**
1. Find the middle element.
2. If it matches the target, return its index.
3. If the target is smaller, search the left half.
4. Otherwise, search the right half.
5. Stop when the element is found or the range becomes empty.

**Python Code:**
```python
def binary_search(arr, low, high, key):
    if low > high:
        return -1

    mid = (low + high) // 2

    if arr[mid] == key:
        return mid
    elif key < arr[mid]:
        return binary_search(arr, low, mid - 1, key)
    else:
        return binary_search(arr, mid + 1, high, key)

arr = [10, 20, 30, 40, 50]
print(binary_search(arr, 0, len(arr) - 1, 40))
```

**Output:**
```text
3
```

**Time Complexity:** \(O(\log n)\)

**Note:** Binary Search requires a sorted array.

## 3. Recursion in Sorting

### A. Merge Sort

**Definition:** Merge Sort is a divide-and-conquer sorting algorithm that divides an array into smaller parts, sorts them, and merges them.

**Steps:**
1. Divide the array into two halves.
2. Recursively sort each half.
3. Merge both sorted halves.
4. Continue until the complete array is sorted.

**Python Code:**
```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])

    result = []
    i = j = 0

    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    return result + left[i:] + right[j:]

print(merge_sort([5, 2, 8, 1, 3]))
```

**Output:**
```text
[1, 2, 3, 5, 8]
```

**Time Complexity:** \(O(n \log n)\)

### B. Quick Sort

**Definition:** Quick Sort is a divide-and-conquer algorithm that selects a pivot and separates elements into smaller and larger groups.

**Steps:**
1. Select a pivot element.
2. Place smaller elements before the pivot.
3. Place larger elements after the pivot.
4. Recursively sort both groups.

**Python Code:**
```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr

    pivot = arr[-1]
    left = [x for x in arr[:-1] if x <= pivot]
    right = [x for x in arr[:-1] if x > pivot]

    return quick_sort(left) + [pivot] + quick_sort(right)

print(quick_sort([5, 2, 8, 1, 3]))
```

**Output:**
```text
[1, 2, 3, 5, 8]
```

**Time Complexity:**
- Best/Average Case: \(O(n \log n)\)
- Worst Case: \(O(n^2)\)

## 4. Difference Between Searching and Sorting

| Searching | Sorting |
|---|---|
| Finds a particular element | Arranges elements in order |
| Example: Binary Search | Examples: Merge Sort, Quick Sort |
| Returns an element or its position | Returns an ordered collection |

## 5. Advantages of Recursion

- Makes complex problems easier to divide into smaller problems.
- Useful in tree traversal and divide-and-conquer algorithms.
- Can make code shorter and easier to understand.

## 6. Limitations of Recursion

- Uses additional call-stack memory.
- Too many recursive calls can cause a recursion-depth error.
- Missing a base case can cause recursion to continue indefinitely.

## 7. Summary

On Day 09, I learned recursion fundamentals and explored its applications in searching and sorting. I practiced recursive Binary Search, Merge Sort, and Quick Sort using Python, strengthening my understanding of base cases, recursive calls, and algorithm complexity.

**Technologies:** Python, Data Structures and Algorithms (DSA)
