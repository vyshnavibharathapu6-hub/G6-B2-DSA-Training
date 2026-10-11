# Day 03 — Arrays (Continued)

**Training Group:** G6-B2  
**Topic:** Arrays  
**Programming Language:** Python

## 1. Two-Dimensional Arrays

A two-dimensional array stores elements in rows and columns. In Python, nested lists are commonly used to represent matrices.

### Python Code

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix[0][1])
print(matrix[2][2])
```

**Output:**
```text
2
9
```

**Explanation:**
- `matrix[0][1]` accesses the element in the first row and second column.
- `matrix[2][2]` accesses the element in the third row and third column.
- Row and column indices start from `0`.

## 2. Traversing a Two-Dimensional Array

Nested loops are used to visit every element in a matrix.

### Python Code

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]

for row in matrix:
    for element in row:
        print(element, end=" ")
    print()
```

**Output:**
```text
1 2 3
4 5 6
```

**Explanation:**
- The outer loop visits each row.
- The inner loop visits each element in the current row.
- The time complexity is O(r × c), where r is the number of rows and c is the number of columns.

## 3. Finding the Second Largest Distinct Element

The second largest distinct element is the largest value smaller than the maximum element.

### Python Code

```python
arr = [10, 20, 4, 45, 99, 99]

unique = sorted(set(arr))

if len(unique) >= 2:
    print(unique[-2])
else:
    print("No second largest element")
```

**Output:**
```text
45
```

**Explanation:**
- `set(arr)` removes duplicate values.
- `sorted()` arranges the distinct values in ascending order.
- `unique[-2]` accesses the second largest value.
- Sorting takes O(n log n) time.

## 4. Removing Duplicates from an Array

Duplicate removal means keeping only one occurrence of each value.

### Python Code

```python
arr = [1, 2, 2, 3, 4, 4, 5]

result = list(dict.fromkeys(arr))

print(result)
```

**Output:**
```text
[1, 2, 3, 4, 5]
```

**Explanation:**
- `dict.fromkeys()` keeps the first occurrence of each value.
- The original order is preserved.
- The result is converted back into a list.

## 5. Moving Zeros to the End

This operation moves all zeros to the end while preserving the relative order of non-zero elements.

### Python Code

```python
arr = [0, 1, 0, 3, 12]

result = [x for x in arr if x != 0]
result += [0] * (len(arr) - len(result))

print(result)
```

**Output:**
```text
[1, 3, 12, 0, 0]
```

**Explanation:**
- The list comprehension collects all non-zero elements.
- The remaining number of positions is filled with zeros.
- The time complexity is O(n).

## 6. Merging Two Arrays

Merging combines the elements of two arrays into one array.

### Python Code

```python
arr1 = [1, 2, 3]
arr2 = [4, 5, 6]

merged = arr1 + arr2

print(merged)
```

**Output:**
```text
[1, 2, 3, 4, 5, 6]
```

**Explanation:**
The `+` operator concatenates two lists and creates a new list. The time complexity is O(n + m), where n and m are the lengths of the two lists.

## 7. Prefix Sum

A prefix sum array stores the cumulative sum of elements up to each index. It helps answer range-sum queries efficiently after preprocessing.

### Python Code

```python
arr = [2, 4, 6, 8]

prefix = []
total = 0

for x in arr:
    total += x
    prefix.append(total)

print(prefix)
```

**Output:**
```text
[2, 6, 12, 20]
```

**Explanation:**
- The first prefix value is the first array element.
- Each following value adds the current element to the previous cumulative sum.
- Building the prefix sum takes O(n) time.

For an inclusive range from index `left` to index `right`:
- If `left == 0`, the sum is `prefix[right]`.
- Otherwise, the sum is `prefix[right] - prefix[left - 1]`.

## 8. Array Rotation

Array rotation shifts elements to the left or right by a specified number of positions.

### Python Code — Left Rotation

```python
arr = [1, 2, 3, 4, 5]
k = 2

k %= len(arr)
rotated = arr[k:] + arr[:k]

print(rotated)
```

**Output:**
```text
[3, 4, 5, 1, 2]
```

**Explanation:**
- `arr[k:]` selects elements from index `k` to the end.
- `arr[:k]` selects the first `k` elements.
- Concatenating the two slices performs the left rotation.
- The modulo operation handles rotation counts greater than the array length.

## 9. Important Array Operation Complexity

| Operation | Time Complexity |
|---|---|
| Matrix traversal | O(r × c) |
| Remove duplicates using a set/dictionary | O(n) average |
| Move zeros to the end | O(n) |
| Merge two arrays | O(n + m) |
| Build prefix sums | O(n) |
| Array rotation using slicing | O(n) |

