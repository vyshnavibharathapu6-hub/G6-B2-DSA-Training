# Day 05 — Strings (Continued)

**Training Group:** G6-B2  
**Topic:** String Manipulation  
**Programming Language:** Python

## 1. Count Character Frequency

Character frequency means counting how many times each character appears in a string.

```python
s = "banana"

for ch in set(s):
    print(ch, s.count(ch))
```

**Explanation:** `count()` returns the number of occurrences of a character. Using `set(s)` avoids processing the same character repeatedly, though the display order is not guaranteed.

## 2. Remove Spaces from a String

The `replace()` method can remove spaces from a string.

```python
s = "hello world python"
result = s.replace(" ", "")

print(result)
```

**Output:**
```text
helloworldpython
```

## 3. Check Whether Two Strings Are Anagrams

Two strings are anagrams if they contain the same characters with the same frequencies, ignoring order.

```python
a = "listen"
b = "silent"

if sorted(a) == sorted(b):
    print("Anagrams")
else:
    print("Not Anagrams")
```

**Output:**
```text
Anagrams
```

**Explanation:** `sorted()` arranges each string's characters in order, making it possible to compare their contents.

## 4. Count Words in a String

The `split()` method separates a string into words using whitespace by default.

```python
s = "Python is easy to learn"
words = s.split()

print("Word count:", len(words))
```

**Output:**
```text
Word count: 5
```

## 5. Find the First Non-Repeating Character

A non-repeating character appears only once in the string.

```python
s = "aabbcdde"

for ch in s:
    if s.count(ch) == 1:
        print(ch)
        break
```

**Output:**
```text
c
```

**Explanation:** The loop checks each character in order and prints the first one whose frequency is one. This simple approach can take O(n²) time.

## 6. Convert a String to a List of Characters

The `list()` function converts a string into a list containing its individual characters.

```python
s = "hello"
chars = list(s)

print(chars)
```

**Output:**
```text
['h', 'e', 'l', 'l', 'o']
```

## 7. Join Strings

The `join()` method combines strings from an iterable using a chosen separator.

```python
words = ["Python", "is", "powerful"]
result = " ".join(words)

print(result)
```

**Output:**
```text
Python is powerful
```

