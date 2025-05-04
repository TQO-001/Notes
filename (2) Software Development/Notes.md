# **Python Notes**

> A compact, professional reference covering syntax, patterns, and Python-specific features.

---

## **1. Python Basics**

|Concept|Description|
|---|---|
|Comments|Use `#` for single-line comments|
|Variables|Dynamically typed (`x = 5`)|
|Naming Conventions|snake_case for variables and functions|

```python
# Single-line comment
x = 5
my_variable = "Hello"
```

---

## **2. Data Types**

### 2.1 Primitives

|Type|Example|
|---|---|
|int|`x = 10`|
|float|`y = 3.14`|
|str|`name = "John"`|
|bool|`is_valid = True`|

```python
x = 42
pi = 3.14
name = "Alice"
active = False
```

---

### 2.2 Collections

> Python collections group multiple values together into a single data structure.  
> They are used to store, organize, and manage data efficiently.

|Type|Example|
|---|---|
|list|`[1, 2, 3]`|
|tuple|`(1, 2, 3)`|
|dict|`{"a": 1, "b": 2}`|
|set|`{1, 2, 3}`|

```python
nums = [1, 2, 3]
coords = (10, 20)
person = {"name": "Alice", "age": 30}
unique = {1, 2, 3}
```

> **Tip:**  
> Lists are mutable; tuples are immutable.

---

## **3. Functions**

|Concept|Syntax|
|---|---|
|Define function|`def func():`|
|Return value|`return`|
|Parameters|Inside parentheses|

```python
def greet(name):
    return f"Hello, {name}"
```

---

### 3.1 Lambda Functions

> Short anonymous functions defined with `lambda`.

```python
add = lambda x, y: x + y
print(add(2, 3))  # 5
```

---

### 3.2 Higher Order Functions

> Functions that take other functions as arguments or return them.

```python
def shout(text):
    return text.upper()

def greet(func):
    return func("hello")

print(greet(shout))  # HELLO
```

---

### 3.3 *args and **kwargs

> Special syntax used in function definitions to accept a variable number of arguments.  
> `*args` collects extra positional arguments as a tuple.  
> `**kwargs` collects extra keyword arguments as a dictionary.

```python
def example(*args, **kwargs):
    print(args)
    print(kwargs)

example(1, 2, a=3, b=4)
```

---

## **4. Conditional Logic**

|Syntax|Example|
|---|---|
|if|`if x > 0:`|
|elif|`elif x == 0:`|
|else|`else:`|

```python
if score > 90:
    print("A")
elif score > 80:
    print("B")
else:
    print("C")
```

---

## **5. Loops**

### 5.1 For Loops

```python
for item in [1, 2, 3]:
    print(item)
```

---

### 5.2 While Loops

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

> **Tip:**  
> Use `break` to exit early; use `continue` to skip to the next iteration.

---

## **6. Exception Handling**

> Exception handling allows your program to respond gracefully when errors occur.  
> `try` runs a block of code, and `except` catches and handles exceptions if any arise.

---

### 6.1 Try / Except

```python
try:
    x = 5 / 0
except ZeroDivisionError:
    print("Cannot divide by zero.")
```

---

### 6.2 Raising Exceptions

```python
def check_positive(x):
    if x < 0:
        raise ValueError("Negative value not allowed")
```

---

### 6.3 Custom Exceptions

```python
class CustomError(Exception):
    pass

raise CustomError("Something went wrong")
```

---

## **7. File I/O**

---

### 7.1 Basic Open / Close

> Opening a file gives you a file object for reading (`'r'`), writing (`'w'`), or appending (`'a'`).  
> Always remember to manually close the file to free system resources.

```python
f = open('file.txt', 'r')
content = f.read()
f.close()
```

---

### 7.2 With Context Manager (Best Practice)

> Using `with open()` is the recommended method to handle files.  
> It automatically closes the file after the block ends, even if errors occur.

```python
with open('file.txt', 'r') as f:
    content = f.read()
```

---

### 7.3 Writing to Files

> Writing mode `'w'` creates a new file or overwrites an existing one.  
> Use `file.write()` to save text content to disk.

```python
with open('file.txt', 'w') as f:
    f.write("Hello World")
```

---

## **8. Object-Oriented Programming (OOP)**

---

### 8.1 Classes and Objects

```python
class Dog:
    def __init__(self, name):
        self.name = name

dog = Dog("Fido")
```

---

### 8.2 Attributes and Methods

```python
class Car:
    def __init__(self, brand):
        self.brand = brand

    def drive(self):
        print(f"{self.brand} is driving.")

car = Car("Toyota")
car.drive()
```

---

### 8.3 Inheritance

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    def bark(self):
        print("Woof!")

dog = Dog()
dog.speak()
dog.bark()
```

---

### 8.4 Polymorphism

```python
class Cat:
    def sound(self):
        print("Meow")

class Dog:
    def sound(self):
        print("Woof")

for animal in (Cat(), Dog()):
    animal.sound()
```

---

### 8.5 Encapsulation (Private Variables)

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance  # private

    def get_balance(self):
        return self.__balance
```

---

### 8.6 Special Methods (`__str__`, `__repr__`)

```python
class Book:
    def __init__(self, title):
        self.title = title

    def __str__(self):
        return f"Book: {self.title}"

book = Book("Python 101")
print(book)
```

---

## **9. Decorators**

---

### 9.1 Function Decorators

```python
def decorator(func):
    def wrapper():
        print("Before function")
        func()
        print("After function")
    return wrapper

@decorator
def say_hello():
    print("Hello")

say_hello()
```

---

### 9.2 Chaining Decorators

```python
@decorator1
@decorator2
def my_function():
    pass
```

---

### 9.3 Decorators with Arguments

```python
def repeat(n):
    def decorator(func):
        def wrapper(*args, **kwargs):
            for _ in range(n):
                func(*args, **kwargs)
        return wrapper
    return decorator

@repeat(3)
def greet():
    print("Hello")

greet()
```

---

## **10. Generators and Iterators**

---

### 10.1 Generator Functions

```python
def countdown(n):
    while n > 0:
        yield n
        n -= 1
```

---

### 10.2 Generator Expressions

```python
squares = (x*x for x in range(5))
```

---

### 10.3 Iter() and Next()

```python
nums = [1, 2, 3]
it = iter(nums)
print(next(it))
```

---

## **11. Context Managers**

---

### 11.1 Custom Context Managers

```python
class MyContext:
    def __enter__(self):
        print("Enter")
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        print("Exit")

with MyContext():
    print("Working inside context")
```

---

### 11.2 Using `contextlib`

```python
from contextlib import contextmanager

@contextmanager
def simple_context():
    print("Enter")
    yield
    print("Exit")

with simple_context():
    print("Doing work")
```

---

## **12. Modules and Packages**

Python encourages modular programming by letting you break your code into **modules** and **packages**, making your programs easier to manage, test, and reuse.

---

### **12.1 Importing Modules**

A **module** is simply a Python file (`.py`) containing functions, classes, or variables you can import into other scripts.

```python
import math
print(math.sqrt(16))  # 4.0
```

✅ You can also use:

```python
from math import sqrt
print(sqrt(16))
```

🔹 Rename during import:

```python
import math as m
print(m.pi)
```

---

### **12.2 Writing Your Own Module**

To create a custom module, save reusable code in a `.py` file.

```python
# utils.py
def add(x, y):
    return x + y
```

Use it in another file:

```python
# main.py
import utils
print(utils.add(2, 3))  # 5
```

📌 Python will search for `utils.py` in the current directory and `sys.path`.

---

### **12.3 Packages**

A **package** is a folder containing a special `__init__.py` file and one or more module files.

```bash
myproject/
│
├── __init__.py       # Marks the directory as a package
├── module1.py
└── module2.py
```

You can then import modules like:

```python
from myproject import module1
module1.function()
```

Or even:

```python
from myproject.module1 import function
```

📦 `__init__.py` can be empty, or it can contain initialization code for the package.

---

### **12.4 Absolute vs Relative Imports**

- **Absolute** (recommended for most use):
    
    ```python
    from myproject.module1 import some_func
    ```
    
- **Relative** (within a package):
    
    ```python
    from .module1 import some_func
    from ..subpackage import other_func
    ```
    

> ⚠️ Relative imports only work inside packages, not top-level scripts.

---

### **12.5 Built-in vs. Third-Party Modules**

- **Built-in**: come with Python (`math`, `os`, `sys`, `datetime`, etc.)
    
- **Third-party**: install via pip (`requests`, `numpy`, `pandas`, etc.)
    

```bash
pip install requests
```

```python
import requests
```

---

### ✅ Best Practices

- Keep module names lowercase (`utils.py`, not `Utils.py`)
    
- Avoid naming conflicts with built-in modules (e.g., don’t name a file `math.py`)
    
- Use meaningful and consistent naming across your package
    

---

### 📂 Visualizing a Python Package Directory Structure

Here's a typical directory structure for a Python project:

```bash
myproject/
├── myproject/
│   ├── __init__.py
│   ├── module1.py
│   └── module2.py
├── tests/
│   ├── test_module1.py
│   └── test_module2.py
├── README.md
├── requirements.txt
└── setup.py
```

- `myproject/`: The main package directory containing your modules.
    
- `tests/`: A directory for your test modules, mirroring the structure of your main package.
    
- `README.md`: A markdown file containing information about your project.
    
- `requirements.txt`: A file listing the dependencies of your project.
    
- `setup.py`: A script for installing your package.
    

This structure helps in organizing your code and makes it easier to maintain and scale your project.

---

## **13. Virtual Environments**

---

### 13.1 venv Basics

```bash
python -m venv env
```

---

### 13.2 Activating/Deactivating

|OS|Command|
|---|---|
|Windows|`env\Scripts\activate`|
|Unix/Mac|`source env/bin/activate`|

```bash
deactivate
```

---

### 13.3 Installing Packages in venv

```bash
pip install package_name
```

---

## **14. Extras**

---

### 14.1 Type Hinting

```python
def greet(name: str) -> str:
    return f"Hello, {name}"
```

---

### 14.2 Dataclasses

```python
from dataclasses import dataclass

@dataclass
class Point:
    x: int
    y: int
```

---

### 14.3 Comprehensions

```python
squares = [x*x for x in range(5)]
```

---

### 14.4 map(), filter(), reduce()

```python
from functools import reduce

print(list(map(lambda x: x*2, [1, 2, 3])))
print(list(filter(lambda x: x%2 == 0, [1, 2, 3, 4])))
print(reduce(lambda x, y: x+y, [1, 2, 3, 4]))
```

---

### 14.5 Advanced *args, **kwargs

```python
def func(a, *args, b=10, **kwargs):
    pass
```

---

