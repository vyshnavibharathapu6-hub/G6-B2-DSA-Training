# Day 08 — Searching and Sorting

## 1. Binary Search

Binary Search finds an element in a **sorted array** by repeatedly dividing the search range into half.

**Time Complexity:** O(log n)

```python
arr = [10, 20, 30, 40, 50]
target = 30

low = 0
high = len(arr) - 1

while low <= high:
    mid = (low + high) // 2

    if arr[mid] == target:
        print("Found at index", mid)
        break
    elif arr[mid] < target:
        low = mid + 1
    else:
        high = mid - 1
```

**Output:**
```text
Found at index 2
```

## 2. Insertion Sort

Insertion Sort builds a sorted array by taking one element at a time and inserting it into its correct position.

**Time Complexity:** O(n²)

```python
arr = [5, 3, 4, 1, 2]

for i in range(1, len(arr)):
    key = arr[i]
    j = i - 1

    while j >= 0 and arr[j] > key:
        arr[j + 1] = arr[j]
        j -= 1

    arr[j + 1] = key

print(arr)
```

**Output:**
```text
[1, 2, 3, 4, 5]
```

## 3. Merge Sort

Merge Sort uses the **divide-and-conquer** technique. It divides the array, sorts each part, and merges the sorted parts.

**Time Complexity:** O(n log n)

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

    result.extend(left[i:])
    result.extend(right[j:])
    return result

print(merge_sort([5, 2, 4, 1, 3]))
```

**Output:**
```text
[1, 2, 3, 4, 5]
```

## 4. Sorting Complexity

| Algorithm | Best/Average/Worst (general) |
|---|---|
| Bubble Sort | O(n²) |
| Selection Sort | O(n²) |
| Insertion Sort | O(n²) |
| Merge Sort | O(n log n) |
| Binary Search | O(log n) |

*Note: Binary Search is a searching algorithm, not a sorting algorithm. The array must already be sorted.*
