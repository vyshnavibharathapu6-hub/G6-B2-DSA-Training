# Day 10 – Recursion in Searching and Sorting (Practice)

## 1. Introduction

Recursion is a technique in which a function calls itself to solve a problem. It consists of a base case that stops recursion and a recursive case that reduces the problem.

Today, the focus is on practicing recursive searching and sorting algorithms using Python.

## 2. Recursive Linear Search

### Definition
Linear Search checks each element one by one until the target is found or the list ends. In its recursive version, the function checks one element and calls itself for the next index.

### Python Code
```python
def linear_search(arr, key, index=0):
    if index == len(arr):
        return -1
    if arr[index] == key:
        return index
    return linear_search(arr, key, index + 1)

arr = [10, 20, 30, 40, 50]
print(linear_search(arr, 30))
```

**Output:**
```text
2
```

**Time Complexity:** \(O(n)\)

## 3. Recursive Binary Search

### Definition
Binary Search repeatedly divides a sorted array into halves to find the target element.

### Python Code
```python
def binary_search(arr, low, high, key):
    if low > high:
        return -1

    mid = (low + high) // 2

    if arr[mid] == key:
        return mid
    if key < arr[mid]:
        return binary_search(arr, low, mid - 1, key)
    return binary_search(arr, mid + 1, high, key)

arr = [10, 20, 30, 40, 50]
print(binary_search(arr, 0, len(arr) - 1, 50))
```

**Output:**
```text
4
```

**Time Complexity:** \(O(\log n)\)

**Important:** Binary Search works only when the array is sorted.

## 4. Merge Sort Using Recursion

### Definition
Merge Sort divides an array into two halves, recursively sorts both halves, and merges them into a sorted array.

### Python Code
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
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    return result + left[i:] + right[j:]

print(merge_sort([8, 3, 5, 1, 4]))
```

**Output:**
```text
[1, 3, 4, 5, 8]
```

**Time Complexity:** \(O(n \log n)\)

## 5. Quick Sort Using Recursion

### Definition
Quick Sort selects a pivot and separates the elements into smaller and larger groups. It recursively sorts both groups.

### Python Code
```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr

    pivot = arr[-1]
    left = [x for x in arr[:-1] if x <= pivot]
    right = [x for x in arr[:-1] if x > pivot]

    return quick_sort(left) + [pivot] + quick_sort(right)

print(quick_sort([7, 2, 9, 1, 5]))
```

**Output:**
```text
[1, 2, 5, 7, 9]
```

**Time Complexity:**
- Best/Average: \(O(n \log n)\)
- Worst: \(O(n^2)\)

## 6. Comparison of Algorithms

| Algorithm | Purpose | Time Complexity |
|---|---|---|
| Linear Search | Finds an element | \(O(n)\) |
| Binary Search | Finds an element in a sorted array | \(O(\log n)\) |
| Merge Sort | Sorts elements | \(O(n \log n)\) |
| Quick Sort | Sorts elements | Average \(O(n \log n)\) |

## 7. Key Learnings

- Practiced recursive function calls and base cases.
- Understood recursive searching and sorting.
- Learned how Binary Search reduces the search space.
- Practiced the divide-and-conquer approach in Merge Sort and Quick Sort.
- Improved Python coding and problem-solving skills.

## 8. Conclusion

Day 10 focused on practicing recursion in searching and sorting algorithms. Implementing Linear Search, Binary Search, Merge Sort, and Quick Sort helped strengthen my understanding of recursion, algorithm logic, and time complexity.

**Language:** Python

**Category:** Data Structures and Algorithms (DSA)
