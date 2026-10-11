# Day 06 — Two Pointers and Sliding Window

**Training Group:** G6-B2  
**Topics:** Two Pointers and Sliding Window  
**Programming Language:** Python

## 1. Two Pointers Technique

The Two Pointers technique uses two indices to process an array or string efficiently. The pointers may start at opposite ends or move through the sequence at different speeds.

### Example: Check Whether a String Is a Palindrome

```python
s = "madam"
left = 0
right = len(s) - 1

while left < right:
    if s[left] != s[right]:
        print("Not Palindrome")
        break
    left += 1
    right -= 1
else:
    print("Palindrome")
```

**Output:**
```text
Palindrome
```

**Explanation:**
- `left` starts at the first character.
- `right` starts at the last character.
- The characters are compared while the pointers move inward.
- Time complexity: O(n).

## 2. Two Sum in a Sorted Array

This technique can find two numbers that add up to a target in a sorted array.

```python
arr = [1, 2, 4, 6, 8]
target = 10
left = 0
right = len(arr) - 1

while left < right:
    total = arr[left] + arr[right]

    if total == target:
        print(left, right)
        break
    elif total < target:
        left += 1
    else:
        right -= 1
```

**Output:**
```text
1 4
```

**Explanation:** If the sum is too small, move the left pointer right. If it is too large, move the right pointer left. This works because the array is sorted.

**Time complexity:** O(n).

## 3. Sliding Window Technique

Sliding Window processes a continuous section of an array or string. Instead of recalculating every window from scratch, the technique updates the current window as it moves.

### Example: Maximum Sum of a Subarray of Size K

```python
arr = [2, 1, 5, 1, 3, 2]
k = 3

window_sum = sum(arr[:k])
max_sum = window_sum

for i in range(k, len(arr)):
    window_sum += arr[i] - arr[i - k]
    max_sum = max(max_sum, window_sum)

print(max_sum)
```

**Output:**
```text
9
```

**Explanation:**
- Calculate the sum of the first `k` elements.
- Add the new element entering the window.
- Subtract the element leaving the window.
- Track the maximum sum.

**Time complexity:** O(n).

## 4. Variable-Size Sliding Window

A variable-size window expands or shrinks according to a condition. For example, it can find the smallest subarray whose sum is at least a target, when all array elements are positive.

```python
arr = [2, 3, 1, 2, 4, 3]
target = 7
left = 0
total = 0
min_len = len(arr) + 1

for right in range(len(arr)):
    total += arr[right]

    while total >= target:
        min_len = min(min_len, right - left + 1)
        total -= arr[left]
        left += 1

print(min_len if min_len <= len(arr) else 0)
```

**Output:**
```text
2
```

**Explanation:** Expand the window by moving `right`. Once the sum reaches the target, shrink from the left to find the shortest valid window. This method relies on positive elements.

**Time complexity:** O(n).

