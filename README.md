# python concepts
# 🐍 Python Basics — Quick Start Guide
## 1. ✅ Installing & Running Python

```bash
python --version        # Check version
python                  # Start REPL (interactive shell)
python myscript.py      # Run a script
```

## 2. 📝 Hello World
```python
print("Hello, World!")
```

## 3. 🔤 Variables & Data Types
```python
name = "Alice"          # str
age = 25                # int
height = 5.9            # float
is_student = True       # bool
nothing = None          # NoneType
print(type(name))  # <class 'str'>
```
## 4. 📚 Basic Data Structures
### ➤ List (Mutable, Ordered)
```python
fruits = ["apple", "banana", "cherry"]
fruits.append("orange")
print(fruits[0])        # "apple"
```
### ➤ Tuple (Immutable, Ordered)
```python
point = (3, 4)
print(point[1])         # 4
```
### ➤ Dictionary (Key-Value Pairs)
```python
person = {"name": "Bob", "age": 30}
print(person["name"])   # "Bob"
```
### ➤ Set (Unique Elements, Unordered)
```python
colors = {"red", "green", "blue"}
colors.add("yellow")
```
## 5. 🖊️Input and Output
```python
name = input("What's your name? ")
print("Hello,", name)
age = int(input("Age? "))
print(f"Name: {name}, Age: {age}")
```
## 6. 🔄 Operators
```python
# Arithmetic:
+  -  *  /  // (floor)  % (mod)  ** (power)
# Comparison:
==  !=  >  <  >=  <=
# Logical:
and  or  not
# Example:
x = 10
y = 3
print(x // y)   # 3 (floor division)
print(x % y)    # 1 (remainder)
print(x ** y)   # 1000 (10^3)
```
## 7. 🚦 Control Flow
### ➤ if / elif / else
```python
age = 18
if age < 13:
    print("Child")
elif age < 20:
    print("Teen")
else:
    print("Adult")
```
### ➤ for Loop
```python
for i in range(5):        # 0 to 4
    print(i)

for fruit in fruits:
    print(fruit)
```
## ➤ while Loop
```python
count = 0
while count < 3:
    print(count)
    count += 1
```
## ➤ break & continue
```python
for i in range(10):
    if i == 3:
        continue   # skip 3
    if i == 7:
        break      # stop at 7
    print(i)
```    
## 8. 🧩 Functions
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))   # "Hello, Alice!"

def greet(name="Stranger"):
    print(f"Hi, {name}!")

greet()          # "Hi, Stranger!"
greet("Bob")     # "Hi, Bob!"

def describe_pet(name, animal="dog"):
    print(f"{name} is a {animal}")

describe_pet(animal="cat", name="Whiskers")
```
## 9. 📁 Importing Modules
```python
import math
print(math.sqrt(16))   # 4.0

from datetime import date
today = date.today()
print(today)
```
## 10. 📂 Working with Files
```python
with open("file.txt", "r") as f:
    content = f.read()
    print(content)

with open("output.txt", "w") as f:
    f.write("Hello, file!")
```    

## 11. 🐞 Error Handling (try / except)
```python
try:
    num = int(input("Enter a number: "))
    print(10 / num)
except ValueError:
    print("That's not a valid number!")
except ZeroDivisionError:
    print("Can't divide by zero!")
except Exception as e:
    print("Something went wrong:", e)
```
## 12. 🧪 Example: Simple Program
```python
# Guess the number game
import random

number = random.randint(1, 10)
guess = None

while guess != number:
    guess = int(input("Guess a number (1-10): "))
    if guess < number:
        print("Too low!")
    elif guess > number:
        print("Too high!")
    else:
        print("You got it!")
```

## 📌 Quick Tips
Use # for comments.
Use """docstrings""" to document functions.
Lists are mutable, tuples are not.
Strings are immutable.
Use == to compare values, is to compare identity.
Python uses 0-based indexing.

## List comprehensions
Classes & OOP
Virtual environments (venv)
Popular libraries: requests, pandas, matplotlib
🎁 Bonus: Useful Built-in Functions
```python
len(list)        # length
str(), int(), float()  # type conversion
range(start, stop, step)
sorted(list)     # returns new sorted list
list.sort()      # sorts in-place
max(), min()
sum(list)
```

## 🐍 Python 3.13 (Released October 2024)
### 1. Faster Startup & Smaller Core Interpreter
Optimized startup time by lazy-loading modules.
Reduced interpreter size by making some stdlib modules optional (e.g., tkinter, idlelib).
### 2. Per-Interpreter GIL (Global Interpreter Lock)
Experimental support for multiple interpreters with independent GILs.
Enables true parallelism in multi-core scenarios (via interpreters module).
Still evolving — not for production yet.
### 3. Improved Error Messages
Even more helpful tracebacks and syntax error hints.
Better suggestions for typos in variable/function names.
### 4. Deprecated and Removed Features
Py_UNICODE APIs removed (use Py_UCS4 or wchar_t).
imghdr, sndhdr modules deprecated.
## 🐍 Python 3.12 (Released October 2023)
### 1. PEP 701: Syntactic Formalization of F-Strings
F-strings now support arbitrary expressions, including multi-line, comments, and backslashes:
```python
name = "Alice"
message = f"""
    Hello {name},
    Welcome to Python 3.12!
    {f"Today is {import datetime; datetime.date.today()}"}
"""
```
### 2. PEP 684: Per-Interpreter GIL (Preview)
Foundation for true multi-core concurrency in future versions.
### 3. New Type System Improvements
type can now be parameterized without importing from typing:
```python
def parse_data( dict[str, int]) -> list[str]:
    ...
```    
### 4. Exception Groups & except* (PEP 654)
Handle multiple exceptions raised concurrently (great for asyncio/tasks):
```python
try:
    raise ExceptionGroup("issues", [ValueError("bad"), TypeError("wrong")])
except* ValueError as eg:
    print("Value errors:", eg.exceptions)
except* TypeError as eg:
    print("Type errors:", eg.exceptions)
```    
### 5. New tomllib Module
Parse TOML files natively (read-only):
```python
import tomllib
with open("config.toml", "rb") as f:
    config = tomllib.load(f)
```    
## 🐍 Python 3.11 (Released October 2022)
### 1. Faster CPython (10–60% Speedup)
Major performance improvements via “Faster CPython” project.
### 2. Exception Notes (add_note())
Add contextual info to exceptions:
```python
try:
    raise ValueError("Invalid input")
except ValueError as e:
    e.add_note("Occurred while parsing user data.")
    raise
```    
### 3. typing.Self
For annotating methods that return an instance of their own class:
```python
from typing import Self

class MyClass:
    def clone(self) -> Self:
        return MyClass()
```        
### 4. tomllib precursor — tomli was standard before 3.12
## 🐍 Python 3.10 (Released October 2021)
1. Structural Pattern Matching (match/case)
```python
match status:
    case 400:
        return "Bad request"
    case 404:
        return "Not found"
    case _:
        return "Something else"
```        
### 2. Union Types with |
```python
def func(x: int | str) -> None:
    ...
```    
### 3. Better Error Messages
More precise location of syntax errors.
## 🐍 Python 3.9 (Released October 2020)
1. Dictionary Merge & Update Operators
```python
d1 = {'a': 1}
d2 = {'b': 2}
d3 = d1 | d2   # {'a': 1, 'b': 2}
d1 |= d2       # d1 updated in-place
```
### 2. str.removeprefix() / str.removesuffix()
```python
text = "HelloWorld"
print(text.removeprefix("Hello"))  # "World"
```
### 3. Built-in Generic Types
```python
def process(items: list[str]) -> dict[str, int]:
    ...
```    
## 🐍 Python 3.8 (Released October 2019)
### 1. Walrus Operator (:=)
```python
if (n := len(data)) > 10:
    print(f"List is too long ({n} elements)")
```    
### 2. Positional-Only Parameters (/)
```python
def greet(name, /, greeting="Hello"):
    print(f"{greeting}, {name}")
```    
### 3. f'{expr=}' Debugging Shortcut
```python
x = 42
print(f"{x=}")  # prints: x=42
```
✅ Tips for Staying Updated
Use pyenv or asdf to test multiple Python versions.
Read What’s New in Python for each release.
Follow PEPs for upcoming features.
## 🚀 Looking Ahead: Python 3.14 (Expected Oct 2025)
Further GIL improvements.
More JIT optimizations (via Faster CPython project).
Possibly: first-class syntactic support for pattern matching enhancements.
Let me know if you want code examples, migration tips, or a deep dive into a specific feature!