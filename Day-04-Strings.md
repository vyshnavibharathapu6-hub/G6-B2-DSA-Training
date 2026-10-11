# Day 04 — Strings

**Training Group:** G6-B2  
**Topic:** Strings  
**Programming Language:** Python

## 1. Introduction to Strings

A string is a sequence of characters enclosed in single or double quotes. Strings in Python are immutable, meaning their characters cannot be changed directly after creation.

```python
s = "Python"

print(s)
print(s[0])
print(len(s))
```

**Output:**
```text
Python
P
6
```

## 2. String Slicing

Slicing extracts a part of a string using the syntax `string[start:end]`. The ending index is excluded.

```python
s = "Programming"

print(s[0:4])
print(s[4:])
print(s[::-1])
```

**Output:**
```text
Prog
ramming
gnimmargorP
```

## 3. Common String Methods

Python provides built-in methods to manipulate and examine strings.

```python
s = "hello world"

print(s.upper())
print(s.capitalize())
print(s.replace("world", "Python"))
print(s.count("l"))
```

**Output:**
```text
HELLO WORLD
Hello world
hello Python
3
```

## 4. Check Whether a String Is a Palindrome

A palindrome reads the same forward and backward, ignoring any differences you choose to normalize.

```python
s = "madam"

if s == s[::-1]:
    print("Palindrome")
else:
    print("Not Palindrome")
```

**Output:**
```text
Palindrome
```

## 5. Count Vowels in a String

Vowels are the letters `a`, `e`, `i`, `o`, and `u`.

```python
s = "programming"
count = 0

for ch in s.lower():
    if ch in "aeiou":
        count += 1

print("Vowels:", count)
```

**Output:**
```text
Vowels: 3
```

## 6. Reverse a String

String slicing with `[::-1]` returns a reversed copy of a string.

```python
s = "hello"
rev = s[::-1]

print(rev)
```

**Output:**
```text
olleh
```

## 7. String Comparison

Strings can be compared using operators such as `==` and `!=`. Comparisons are case-sensitive.

```python
a = "Python"
b = "python"

print(a == b)
print(a.lower() == b.lower())
```

**Output:**
```text
False
True
```

## 8. String Traversal

Traversal means accessing each character in a string one by one.

```python
s = "CODE"

for ch in s:
    print(ch)
```

**Output:**
```text
C
O
D
E
```
