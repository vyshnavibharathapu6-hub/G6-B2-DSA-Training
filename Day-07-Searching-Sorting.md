# Day 07 — Searching and Sorting

**Training Group:** G6-B2  
**Topics:** Linear Search, Binary Search, Bubble Sort, Selection Sort  
**Programming Language:** Python

## 1. Linear Search

Linear Search checks each element one by one until the target is found or the array ends. It works on both sorted and unsorted arrays.

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

**Time Complexity:** O(n)

## 2. Binary Search

Binary Search repeatedly divides the search interval into halves. The array must be sorted.

```python
arr = [10, 20, 30, 40, 50]
target = 40
left = 0
right = len(arr) - 1

while left <= right:
    mid = (left + right) // 2

    if arr[mid] == target:
        print("Found at index", mid)
        break
    elif arr[mid] < target:
        left = mid + 1
    else:
        right = mid - 1
else:
    print("Not found")
```

**Output:**
```text
Found at index 3
```

**Time Complexity:** O(log n)

## 3. Bubble Sort

Bubble Sort compares adjacent elements and swaps them if they are in the wrong order. Repeated passes place larger elements toward the end.

```python
arr = [5, 2, 4, 1, 3]

for i in range(len(arr)):
    for j in range(len(arr) - i - 1):
        if arr[j] > arr[j + 1]:
            arr[j], arr[j + 1] = arr[j + 1], arr[j]

print(arr)
```

**Output:**
```text
[1, 2, 3, 4, 5]
```

**Time Complexity:** O(n²) in the average and worst cases.

## 4. Selection Sort

Selection Sort finds the smallest element in the unsorted portion and swaps it into the next correct position.

```python
arr = [64, 25, 12, 22, 11]

for i in range(len(arr)):
    min_idx = i

    for j in range(i + 1, len(arr)):
        if arr[j] < arr[min_idx]:
            min_idx = j

    arr[i], arr[min_idx] = arr[min_idx], arr[i]

print(arr)
```

**Output:**
```text
[11, 12, 22, 25, 64]
```

**Time Complexity:** O(n²)

## 5. Searching and Sorting Complexity

| Algorithm | Time Complexity |
|---|---|
| Linear Search | O(n) |
| Binary Search | O(log n) |
| Bubble Sort | O(n²) |
| Selection Sort | O(n²) |

