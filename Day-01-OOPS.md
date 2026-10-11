# Day 01 — Object-Oriented Programming (OOPS)

**Training Group:** G6-B2  
**Topic:** Object-Oriented Programming  
**Programming Language:** Python

## 1. Introduction to OOPS

Object-Oriented Programming (OOPS) is a programming paradigm that organizes programs using classes and objects. It supports code reusability, modularity, and easier maintenance.

The four major principles of OOPS are:
- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

## 2. Class and Object

### Class
A class is a blueprint or template used to create objects. It defines attributes (data) and methods (functions) that describe the behavior of its objects.

### Object
An object is an instance of a class. It can access the attributes and methods defined in that class.

### Python Code

```python
class Student:
    def display(self):
        print("Welcome to DSA Training")

s1 = Student()
s1.display()
```

**Output:**
```text
Welcome to DSA Training
```

**Explanation:**
- `class Student` defines a class named Student.
- `display()` is a method of the class.
- `s1 = Student()` creates an object.
- `s1.display()` calls the method using the object.

## 3. Constructor and `__init__()`

A constructor initializes an object's attributes when the object is created. In Python, the `__init__()` method is commonly used for initialization.

### Python Code

```python
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def display(self):
        print("Name:", self.name)
        print("Marks:", self.marks)

s1 = Student("Ravi", 90)
s1.display()
```

**Output:**
```text
Name: Ravi
Marks: 90
```

**Explanation:**
- `__init__()` initializes the object's data.
- `self` refers to the current object.
- `self.name` and `self.marks` store instance attributes.
- Different objects can hold different values.

## 4. Encapsulation

Encapsulation is the concept of combining data and methods within a class. It helps control how an object's data is accessed and modified.

In Python, a name beginning with double underscores, such as `__marks`, is name-mangled to discourage direct access. This is not strict private access control.

### Python Code

```python
class Student:
    def __init__(self, marks):
        self.__marks = marks

    def display(self):
        print("Marks:", self.__marks)

s1 = Student(95)
s1.display()
```

**Output:**
```text
Marks: 95
```

**Explanation:**
- `__marks` is a name-mangled attribute.
- `display()` accesses the attribute through a class method.
- Encapsulation helps organize data and related operations.

## 5. Inheritance

Inheritance allows one class to acquire attributes and methods from another class. The existing class is called the parent class, and the inheriting class is called the child class.

### Python Code

```python
class Animal:
    def eat(self):
        print("Animal is eating")

class Dog(Animal):
    def bark(self):
        print("Dog is barking")

d = Dog()
d.eat()
d.bark()
```

**Output:**
```text
Animal is eating
Dog is barking
```

**Explanation:**
- `Animal` is the parent class.
- `Dog` is the child class.
- `Dog(Animal)` indicates inheritance.
- The child class can use the inherited `eat()` method.

### Types of Inheritance
1. Single inheritance — one child inherits from one parent.
2. Multiple inheritance — one child inherits from multiple parents.
3. Multilevel inheritance — a class inherits from a child class in a chain.
4. Hierarchical inheritance — multiple child classes inherit from one parent.
5. Hybrid inheritance — a combination of inheritance types.

## 6. Polymorphism

Polymorphism means “many forms.” It allows a common method or interface to produce different behavior depending on the object or implementation.

### Python Code

```python
class Dog:
    def sound(self):
        print("Bark")

class Cat:
    def sound(self):
        print("Meow")

d = Dog()
c = Cat()

d.sound()
c.sound()
```

**Output:**
```text
Bark
Meow
```

**Explanation:**
- Both classes define a method named `sound()`.
- The method produces different outputs for different objects.
- This example demonstrates polymorphism through a common method interface.

## 7. Abstraction

Abstraction hides implementation details and exposes essential functionality. In Python, abstract classes and methods can be created using the `abc` module.

### Python Code

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side * self.side

s = Square(4)
print(s.area())
```

**Output:**
```text
16
```

**Explanation:**
- `ABC` is used to define an abstract base class.
- `@abstractmethod` declares a method that concrete subclasses must implement.
- `Square` implements the `area()` method.
- The area is calculated as side × side.

## 8. Method Overriding

Method overriding occurs when a child class provides its own implementation of a method already defined in its parent class.

### Python Code

```python
class Animal:
    def sound(self):
        print("Animal makes a sound")

class Dog(Animal):
    def sound(self):
        print("Dog barks")

d = Dog()
d.sound()
```

**Output:**
```text
Dog barks
```

**Explanation:**
The `Dog` class overrides the `sound()` method inherited from `Animal`. When called on a `Dog` object, the child class implementation is executed.

## 9. The `self` Keyword

`self` refers to the current instance of a class. It is used to access instance attributes and methods. It is a conventional parameter name in Python instance methods.

### Python Code

```python
class Student:
    def __init__(self, name):
        self.name = name

    def display(self):
        print(self.name)

s1 = Student("Ravi")
s1.display()
```

**Output:**
```text
Ravi
```

**Explanation:**
`self.name` refers to the `name` attribute belonging to the current object. When `s1.display()` is called, Python passes `s1` as the instance argument automatically.

## 10. Class Variables and Instance Variables

**Class variable:** A variable shared by instances through the class.

**Instance variable:** A variable associated with an individual object.

### Python Code

```python
class Student:
    college = "SR University"

    def __init__(self, name):
        self.name = name

s1 = Student("Ravi")
s2 = Student("Priya")

print(s1.name)
print(s2.name)
print(s1.college)
```

**Output:**
```text
Ravi
Priya
SR University
```

**Explanation:**
- `college` is a class variable shared through the class.
- `name` is an instance variable.
- Each object can have its own name while using the same college value.
