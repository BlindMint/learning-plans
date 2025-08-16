# Comprehensive Guide to Learning Python 3

## Chapter 1: The World of Variables and Operators

### What are Variables?

Variables store data in memory, acting as named containers.

**Example**:

```javascript
name = "Alice"  # String variable
age = 25  # Integer variable

```

### Naming a Variable

- Use letters, numbers, underscores; start with a letter or underscore.
- Case-sensitive, no reserved words (e.g., `if`, `while`).

**Example**:

```javascript
user_name = "Bob"  # Valid
userName = "Carol"  # Different variable
# 1st_var = 10  # Invalid, starts with number

```

### The Assignment Sign

`=` assigns a value to a variable.

**Example**:

```javascript
score = 100
score = score + 50  # Updates score

```

### Basic Operators

- Arithmetic: `+`, `-`, `*`, `/`, `//` (floor division), `%` (modulus), `**` (exponent).
- Comparison: `==`, `!=`, `>`, `<`, `>=`, `<=`.
- Logical: `and`, `or`, `not`.

**Example**:

```javascript
a = 10
b = 3
print(a + b)  # 13
print(a // b)  # 3
print(a > b)  # True
print(a == b and b < 5)  # False

```

### More Assignment Operators

- `+=`, `-=`, `*=`, `/=`, `%=`, `//=`, `**=`.

**Example**:

```javascript
x = 5
x += 3  # x = 8
x **= 2  # x = 64
print(x)

```

**Script**: Save as `variables_operators.py` and modify values to experiment.

## Chapter 2: Data Types in Python

### Integers

Integers (int) are whole numbers without decimal points, supporting unlimited precision in Python 3. They are used for counting, indexing, and arithmetic operations.

#### Key Features

- **Unlimited Range**: No size limit (e.g., 2**1000 is valid).
- **Arithmetic Operations**: Supports +, -, *, / (returns float), // (floor division), % (modulus), ** (exponent).
- **Bitwise Operations**: & (AND), | (OR), ^ (XOR), ~ (NOT), << (left shift), >> (right shift).
- **Built-in Functions**: abs(), pow(), divmod(), bin(), hex(), oct().

#### Example Script (integers.py):

```
# Basic arithmetic
x = 42
y = 5
print(f"Sum: {x + y}")  # Sum: 47
print(f"Floor division: {x // y}")  # Floor division: 8
print(f"Modulus: {x % y}")  # Modulus: 2
print(f"Power: {x ** 2}")  # Power: 1764

# Bitwise operations
a = 10  # Binary: 1010
b = 4   # Binary: 0100
print(f"AND: {a & b}")  # AND: 0 (0000)
print(f"OR: {a | b}")   # OR: 14 (1110)
print(f"Shift left: {a << 1}")  # Shift left: 20 (10100)

# Built-in functions
print(f"Absolute: {abs(-42)}")  # Absolute: 42
print(f"Binary: {bin(42)}")  # Binary: 0b101010
print(f"Divmod: {divmod(42, 5)}")  # Divmod: (8, 2)
```

#### Notes

- Use // for integer division to avoid float results.
- Bitwise operations are useful for low-level programming or optimizing certain algorithms.
- Experiment with large numbers (e.g., 10**100) to test Python’s precision.

### Float

Floats (float) represent numbers with decimal points or in scientific notation (e.g., 1.23e-4). They are used for measurements, calculations requiring precision, and scientific computations.

#### Key Features

- **Precision**: Limited by IEEE 754 double-precision (about 16-17 decimal digits).
- **Arithmetic**: Same operators as integers, but results are floats.
- **Special Values**: float('inf'), float('-inf'), float('nan').
- **Built-in Functions**: round(), math.floor(), math.ceil() (from math module).
- **Comparison Issues**: Floating-point arithmetic can introduce small errors (e.g., 0.1 + 0.2 != 0.3).

#### Example Script (floats.py):

```
import math

# Basic arithmetic
pi = 3.14159
radius = 2.5
print(f"Area: {pi * radius ** 2:.2f}")  # Area: 19.63
print(f"Division: {10 / 3}")  # Division: 3.3333333333333335

# Special values
infinity = float('inf')
print(f"Is infinite? {math.isinf(infinity)}")  # Is infinite? True
print(f"NaN: {float('nan')}")  # NaN: nan

# Rounding
num = 2.56789
print(f"Round: {round(num, 2)}")  # Round: 2.57
print(f"Floor: {math.floor(num)}")  # Floor: 2
print(f"Ceil: {math.ceil(num)}")  # Ceiling: 3

# Precision issues
print(f"0.1 + 0.2 = {0.1 + 0.2}")  # 0.30000000000000004
print(f"Fixed comparison: {round(0.1 + 0.2, 1) == 0.3}")  # True
```



#### Notes

- Use decimal.Decimal for exact decimal arithmetic if needed (e.g., financial calculations).
- Be aware of precision when comparing floats; use math.isclose() for approximate equality.
- Test special values like inf and NaN in calculations to understand edge cases.

# String Operators and Methods in Python 3

Strings in Python are versatile and come with a rich set of built-in methods for manipulation. The `.lower()` method is one of many string methods that transform or query string data. Below is an in-depth exploration of string methods, including `.lower()`, other common methods, and their practical applications. Examples are provided for each to help you incorporate them into your Python scripts.

## Overview of String Methods
String methods are functions that operate on string objects to perform tasks like case conversion, searching, formatting, splitting, joining, and more. Strings are immutable, so methods that transform strings return new strings rather than modifying the original.

### `.lower()`
Converts all characters in a string to lowercase. Useful for case-insensitive comparisons or standardizing text.

**Example**:
```python
text = "Hello, WORLD!"
print(text.lower())  # hello, world!
```

## Other Common String Methods

### Case Conversion
- **`.upper()`**: Converts all characters to uppercase.
  **Example**:
  ```python
  text = "Python Programming"
  print(text.upper())  # PYTHON PROGRAMMING
  ```

- **`.title()`**: Capitalizes the first character of each word.
  **Example**:
  ```python
  text = "python is fun"
  print(text.title())  # Python Is Fun
  ```

- **`.capitalize()`**: Capitalizes the first character of the string, lowercases the rest.
  **Example**:
  ```python
  text = "hELLO world"
  print(text.capitalize())  # Hello world
  ```

- **`.swapcase()`**: Swaps case of each character (uppercase to lowercase and vice versa).
  **Example**:
  ```python
  text = "PyThOn"
  print(text.swapcase())  # pYtHoN
  ```

### Searching and Checking
- **`.find(sub)`**: Returns the lowest index of substring `sub`, or `-1` if not found.
  **Example**:
  ```python
  text = "Python is awesome"
  print(text.find("is"))  # 7
  print(text.find("java"))  # -1
  ```

- **`.index(sub)`**: Like `.find()`, but raises `ValueError` if substring not found.
  **Example**:
  ```python
  text = "Python is awesome"
  print(text.index("Python"))  # 0
  # print(text.index("java"))  # Raises ValueError
  ```

- **`.count(sub)`**: Counts occurrences of substring `sub`.
  **Example**:
  ```python
  text = "banana"
  print(text.count("a"))  # 3
  ```

- **`.startswith(prefix)`**: Checks if string starts with `prefix`.
  **Example**:
  ```python
  text = "Hello, World!"
  print(text.startswith("Hello"))  # True
  ```

- **`.endswith(suffix)`**: Checks if string ends with `suffix`.
  **Example**:
  ```python
  text = "example.txt"
  print(text.endswith(".txt"))  # True
  ```

- **`.isalpha()`**: Checks if all characters are alphabetic.
  **Example**:
  ```python
  print("Python".isalpha())  # True
  print("Python3".isalpha())  # False
  ```

- **`.isdigit()`**: Checks if all characters are digits.
  **Example**:
  ```python
  print("123".isdigit())  # True
  print("12a3".isdigit())  # False
  ```

- **`.isalnum()`**: Checks if all characters are alphanumeric.
  **Example**:
  ```python
  print("Python2023".isalnum())  # True
  print("Python 2023".isalnum())  # False
  ```

- **`.isspace()`**: Checks if all characters are whitespace.
  **Example**:
  ```python
  print("   \t".isspace())  # True
  print("  text  ".isspace())  # False
  ```

### Modifying Strings
- **`.strip(chars)`**: Removes leading/trailing characters (defaults to whitespace).
  **Example**:
  ```python
  text = "   spaces   "
  print(text.strip())  # spaces
  print("...hello...".strip("."))  # hello
  ```

- **`.lstrip(chars)`**: Removes leading characters.
  **Example**:
  ```python
  print("   text".lstrip())  # text
  ```

- **`.rstrip(chars)`**: Removes trailing characters.
  **Example**:
  ```python
  print("text   ".rstrip())  # text
  ```

- **`.replace(old, new)`**: Replaces all occurrences of `old` with `new`.
  **Example**:
  ```python
  text = "I like Java"
  print(text.replace("Java", "Python"))  # I like Python
  ```

- **`.join(iterable)`**: Joins elements of an iterable with the string as separator.
  **Example**:
  ```python
  words = ["Hello", "World"]
  print(" ".join(words))  # Hello World
  print(",".join(words))  # Hello,World
  ```

- **`.split(sep)`**: Splits string into a list based on separator `sep` (defaults to whitespace).
  **Example**:
  ```python
  text = "apple,banana,orange"
  print(text.split(","))  # ['apple', 'banana', 'orange']
  ```

- **`.rsplit(sep)`**: Splits from the right.
  **Example**:
  ```python
  text = "a.b.c"
  print(text.rsplit(".", 1))  # ['a.b', 'c']
  ```

- **`.splitlines()`**: Splits string at line breaks.
  **Example**:
  ```python
  text = "Line 1\nLine 2"
  print(text.splitlines())  # ['Line 1', 'Line 2']
  ```

### Formatting
- **`.format(*args, **kwargs)`**: Formats string using placeholders.
  **Example**:
  ```python
  print("Hello, {}".format("Alice"))  # Hello, Alice
  print("Score: {score:.2f}".format(score=95.678))  # Score: 95.68
  ```

- **F-Strings** (preferred, Python 3.6+): Embed expressions directly.
  **Example**:
  ```python
  name = "Bob"
  print(f"Welcome, {name}! Score: {95.678:.2f}")  # Welcome, Bob! Score: 95.68
  ```

- **`.center(width, fillchar)`**: Centers string in a field of `width`, padded with `fillchar` (default space).
  **Example**:
  ```python
  print("Python".center(10, "*"))  # **Python**
  ```

- **`.ljust(width, fillchar)`**: Left-justifies string, padded with `fillchar`.
  **Example**:
  ```python
  print("Python".ljust(10, "-"))  # Python----
  ```

- **`.rjust(width, fillchar)`**: Right-justifies string.
  **Example**:
  ```python
  print("Python".rjust(10, "-"))  # ----Python
  ```

- **`.zfill(width)`**: Pads string with zeros on the left to reach `width`.
  **Example**:
  ```python
  print("42".zfill(5))  # 00042
  ```

### Encoding and Decoding
- **`.encode(encoding)`**: Converts string to bytes using specified encoding (e.g., `utf-8`).
  **Example**:
  ```python
  text = "Hello"
  print(text.encode("utf-8"))  # b'Hello'
  ```

- **`.decode(encoding)`**: Used on bytes to convert back to string (not a string method, but related).
  **Example**:
  ```python
  data = b"Hello"
  print(data.decode("utf-8"))  # Hello
  ```

## Practical Example Script
Save as `string_methods.py` to test various string methods:
```python
text = "  Python Programming!  "
name = "Alice"
score = 95.678

# Case conversion
print(text.lower())  # python programming!
print(text.upper())  # PYTHON PROGRAMMING!
print(text.title())  # Python Programming!
print(text.strip().capitalize())  # Python programming!

# Searching
print(text.find("Pro"))  # 8
print(text.count("n"))  # 3
print(text.startswith("  Py"))  # True
print("123".isdigit())  # True

# Modifying
print(text.strip())  # Python Programming!
print(text.replace("Programming", "Coding"))  # Python Coding!
words = text.split()
print(" ".join(words))  # Python Programming!

# Formatting
print(f"User: {name}, Score: {score:.2f}")  # User: Alice, Score: 95.68
print(name.center(10, "*"))  # **Alice***

# Encoding
encoded = text.encode("utf-8")
print(encoded)  # b'  Python Programming!  '
```

## Notes
- **Immutability**: String methods return new strings; the original remains unchanged.
- **Chaining**: Methods can be chained (e.g., `text.strip().lower().replace(" ", "_")`).
- **Performance**: For large strings or frequent operations, consider efficiency (e.g., `.join()` is faster than string concatenation in loops).
- **Documentation**: Python’s official docs (`help(str)` or `dir(str)` in Python) list all methods.

Experiment with `string_methods.py` to combine methods and test edge cases (e.g., empty strings, special characters).

### Type Casting

Type casting converts data between types using int(), float(), str(), list(), tuple(), etc. It’s essential for ensuring compatibility in operations.

#### Key Features

- **Explicit Conversion**: Required for mixed-type operations.

- **Lossy Casting**: Casting may truncate or raise errors (e.g., int("abc") fails).

- Common Conversions

  :

  - int(x): Truncates floats, parses strings of digits.
  - float(x): Converts integers or strings to floats.
  - str(x): Converts numbers to strings.
  - list(x), tuple(x): Converts sequences to lists or tuples.

#### Example Script (type_casting.py):

```
# Number conversions
num_str = "123.45"
num_float = float(num_str)  # 123.45
num_int = int(num_float)   # 123
print(f"Float: {num_float}, Int: {num_int}")  # Float: 123.45, Int: 123

# Sequence conversions
text = "Python"
char_list = list(text)  # ['P', 'y', 't', 'h', 'o', 'n']
char_tuple = tuple(text)  # ('P', 'y', 't', 'h', 'o', 'n')
print(f"List: {char_list}")
print(f"Tuple: {char_tuple}")

# Error handling
try:
    invalid = int("abc")
except ValueError:
    print("Cannot convert 'abc' to int")

# Practical example: user input
age = int(input("Enter age: "))  # Convert input string to int
print(f"Next year, you’ll be {age + 1}")
```

#### Notes

- Always validate inputs when casting from strings to avoid exceptions.
- Use try/except for robust user input handling.
- Experiment with converting between lists and tuples to understand sequence conversions.

### List

Lists are ordered, mutable collections that store elements of any type. They’re ideal for dynamic data storage and iteration.

#### Key Features

- **Mutability**: Elements can be added, removed, or changed.
- **Indexing/Slicing**: Zero-based indexing and slicing (lst[start:end:step]).
- **Methods**: append(), extend(), insert(), remove(), pop(), clear(), index(), sort(), reverse().
- **List Comprehension**: Concise syntax for creating lists (e.g., [x**2 for x in range(5)]).
- **Nested Lists**: Support lists within lists for multi-dimensional data.

#### Example Script (lists.py):

```
# Basic operations
fruits = ["apple", "banana", "cherry"]
fruits.append("date")  # ['apple', 'banana', 'cherry', 'date']
fruits[1] = "blueberry"  # Update
print(fruits[0:2])  # ['apple', 'blueberry']

# Methods
fruits.extend(["elderberry", "fig"])  # ['apple', 'blueberry', 'cherry', 'date', 'elderberry', 'fig']
fruits.remove("cherry")  # ['apple', 'blueberry', 'date', 'elderberry', 'fig']
print(fruits.index("date"))  # 2
fruits.sort()
print(fruits)  # ['apple', 'blueberry', 'date', 'elderberry',', 'fig']

# List comprehension
squares = [x**2 for x in range(5)]
print(squares)  # [0, 1, 4, 9, 16]

# Nested lists
matrix = [[1, 2, 3], [4, 5, 6]]
print(matrix[1][2])  # 6
```

#### Notes

- Use list comprehension for efficient list creation.
- Be cautious with nested lists; modifying a nested list affects the original.
- Test methods like pop() (removes and returns element) and clear() (empties list).

### Tuple

Tuples are ordered, immutable collections, often used for fixed data or as dictionary keys.

#### Key Features

- **Immutability**: Cannot change elements after creation.
- **Indexing/Slicing**: Same as lists.
- **Methods**: Limited to count() and index().
- **Packing/Unpacking**: Supports tuple packing (t = 1, 2) and unpacking (a, b = t).
- **Memory Efficiency**: Tuples use less memory than lists.

#### Example Script (tuples.py):

```
# Basic operations
coords = (10, 20, 30)
print(coords[1])  # 20
print(coords[0:2])  # (10, 20)

# Methods
print(coords.count(20))  # 1
print(coords.index(30))  # 2

# Packing and unpacking
point = 5, 15  # Packing
x, y = point   # Unpacking
print(f"X: {x}, Y: {y}")  # X: 5, Y: 15

# Nested tuples
data = ((1, 2), (3, 4))
print(data[0][1])  # 2
```

#### Notes

- Use tuples for immutable data or when memory efficiency matters.
- Tuples can be dictionary keys (unlike lists).
- Experiment with unpacking in functions (e.g., def get_point(): return 1, 2).

### Dictionary

Dictionaries (dict) store key-value pairs, where keys are immutable (e.g., strings, numbers, tuples) and values can be any type. They’re ideal for fast lookups and mappings.

#### Key Features

- **Mutability**: Add, update, or remove key-value pairs.
- **Access**: Use dict[key], .get() (safer, returns None if key missing).
- **Methods**: keys(), values(), items(), pop(), popitem(), update(), clear().
- **Dictionary Comprehension**: Create dictionaries concisely (e.g., {x: x**2 for x in range(5)}).
- **Default Values**: Use .setdefault() or collections.defaultdict.

#### Example Script (dictionaries.py):

```
# Basic operations
person = {"name": "Alice", "age": 25, "city": "New York"}
print(person["name"])  # Alice
person["age"] = 26     # Update
person["job"] = "Engineer"  # Add
print(person.get("salary", 0))  # 0 (default if key missing)

# Methods
print(person.keys())    # dict_keys(['name', 'age', 'city', 'job'])
print(person.values())  # dict_values(['Alice', 26, 'New York', 'Engineer'])
print(person.items())   # dict_items([('name', 'Alice'), ...])
person.pop("city")      # Remove 'city'
print(person)           # {'name': 'Alice', 'age': 26, 'job': 'Engineer'}

# Dictionary comprehension
squares_dict = {x: x**2 for x in range(5)}
print(squares_dict)  # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}

# Default values
counts = {}
counts.setdefault("a", 0)  # Set default
counts["a"] += 1
print(counts)  # {'a': 1}
```

#### Notes

- Use .get() to avoid KeyError.
- Iterate with .items() for key-value pairs (e.g., for k, v in dict.items():).
- Test nested dictionaries (e.g., {"a": {"b": 1}}) for complex data structures.

## Practical Notes

- **Scripts**: Save each example as separate files (integers.py, floats.py, etc.) to test individually. Combine concepts in a chapter4_combined.py script to experiment with interactions (e.g., casting a list to a tuple, using a dictionary to store float calculations).
- **Error Handling**: Use try/except for type casting or dictionary access to handle invalid inputs.
- **Performance**: Lists are faster for iteration, dictionaries for lookups, tuples for memory efficiency.
- **Experimentation**: Modify values, test edge cases (e.g., empty lists, negative floats, missing dictionary keys), and combine data types (e.g., list of dictionaries).

This expanded guide provides a foundation for mastering Python’s data types. Use the example scripts to build and modify your own programs, exploring how these types interact in real-world scenarios.

# Comprehensive Guide to Learning Python 3 (Extended from Chapter 5)

## Chapter 3: Making Your Program Interactive

### Input()

Captures user input as a string. Optionally accepts a prompt.

**Example**:

```javascript
age = input("Enter your age: ")
print(f"You are {age} years old.")

```

### Print()

Outputs to console, supports multiple arguments, separators, and end characters.

**Example**:

```javascript
name = "Alice"
score = 95
print("Name:", name, "Score:", score, sep=" | ", end="!\n")  # Name: | Alice | Score: | 95!

```

### F-Strings

Formatted string literals (f-strings) embed expressions inside `f"..."`. Introduced in Python 3.6, they’re concise and readable.

**Example**:

```javascript
name = "Bob"
age = 30
print(f"{name} is {age} years old.")  # Bob is 30 years old.
print(f"Next year, {name} will be {age + 1}.")  # Expression in f-string
print(f"Score: {score:>10.2f}")  # Right-align, 2 decimal places: "Score:      95.00"

```

### Triple Quotes

Define multi-line strings, useful for docstrings or long text.

**Example**:

```javascript
message = """Dear User,
Welcome to Python!
Enjoy coding."""
print(message)

```

### Escape Characters

Special characters: `\n` (newline), `\t` (tab), `\\` (backslash), `\"` (quote).

**Example**:

```javascript
print("Quote: \"Python is fun!\"\n\t- Someone")  # Escaped quote, newline, tab
print(r"Raw string: C:\new\test")  # Raw string ignores escapes

```

**Script**: Save as `interactive_extended.py` to test f-strings, print options, and escapes.

## Chapter 4: Making Choices and Decisions

### Condition Statements

Control program flow based on conditions.

### If Statement

Executes block if condition is true, supports `elif` for multiple conditions.

**Example**:

```javascript
score = 85
if score >= 90:
    print("A")
elif score >= 80:
    print("B")
else:
    print("C")

```

### Inline If (Ternary Operator)

Compact conditional expression.

**Example**:

```javascript
age = 20
status = "Adult" if age >= 18 else "Minor"
print(f"Status: {status}")

```

### For Loop

Iterates over sequences (lists, strings, ranges). Supports `else` block, executed if loop completes normally.

**Example**:

```javascript
for char in "Python":
    print(char, end=" ")  # P y t h o n
else:
    print("\nDone!")  # Executes after loop

```

### While Loop

Repeats while condition is true. Supports `else` block like `for`.

**Example**:

```javascript
count = 1
while count <= 3:
    print(f"Count: {count}")
    count += 1
else:
    print("Loop finished!")

```

### Break

Exits loop immediately.

**Example**:

```javascript
for i in range(10):
    if i == 5:
        break
    print(i, end=" ")  # 0 1 2 3 4

```

### Continue

Skips to next iteration.

**Example**:

```javascript
for i in range(5):
    if i % 2 == 0:
        continue
    print(i, end=" ")  # 1 3

```

### Try, Except

Handles exceptions. Use specific exceptions for precise error handling, `else` for code that runs if no exception, and `finally` for cleanup.

**Example**:

```javascript
try:
    num = int(input("Enter a number: "))
    result = 100 / num
except ValueError:
    print("Please enter a valid number.")
except ZeroDivisionError:
    print("Cannot divide by zero.")
else:
    print(f"Result: {result}")
finally:
    print("Operation complete.")

```

**Script**: Save as `control_flow_extended.py` to experiment with loops, conditionals, and exception handling.

## Chapter 5: Functions and Modules

### What are Functions?

Reusable code blocks that perform specific tasks.

### Defining Your Own Functions

Use `def`, support parameters, return values, and default arguments.

**Example**:

```javascript
def calculate_area(length, width=1):  # Default argument
    return length * width

print(f"Area: {calculate_area(5)}")  # Area: 5
print(f"Area: {calculate_area(5, 3)}")  # Area: 15

```

### Variable Scope

- Local: Defined inside function.
- Global: Defined outside, use `global` keyword to modify.
- Nonlocal: Used in nested functions to modify enclosing scope.

**Example**:

```javascript
x = 10  # Global
def outer():
    x = 20  # Enclosing
    def inner():
        nonlocal x
        x = 30  # Modifies enclosing x
    inner()
    print(f"Enclosing x: {x}")  # Enclosing x: 30
outer()
print(f"Global x: {x}")  # Global x: 10

```

### Importing Modules

Access standard or third-party libraries. Use `as` for aliases, `from` for specific imports.

**Example**:

```javascript
import random as rnd
from math import pi
print(f"Random number: {rnd.randint(1, 10)}")
print(f"Circle area: {pi * 5 ** 2:.2f}")

```

### Creating Our Own Module

Save as `utils.py`:

```javascript
def multiply(a, b):
    return a * b

CONSTANT = 42

```

Use in `main.py`:

```javascript
import utils
print(f"Product: {utils.multiply(4, 5)}")  # Product: 20
print(f"Constant: {utils.CONSTANT}")  # Constant: 42

```

**Scripts**: Save as `functions_extended.py` for functions/scope, `utils.py` for module, and `main.py` for module import.

## Chapter 6: Working with Files

### Opening and Reading Text Files

Use `with` for automatic file closure. Modes: `"r"` (read), `"w"` (write), `"a"` (append).

**Example**:

```javascript
with open("data.txt", "r", encoding="utf-8") as file:
    content = file.read()
    print(content)

```

### Using a For Loop to Read Text Files

Efficient for large files, processes line by line.

**Example**:

```javascript
with open("data.txt", "r", encoding="utf-8") as file:
    for line in file:
        print(line.rstrip())  # Remove trailing whitespace

```

### Writing to a Text File

Overwrites with `"w"`, appends with `"a"`. Use `writelines()` for lists.

**Example**:

```javascript
lines = ["First line\n", "Second line\n"]
with open("output.txt", "w", encoding="utf-8") as file:
    f.writelines(lines)

```

### Opening and Reading Text Files by Buffer Size

Read fixed-size chunks, ideal for large files.

**Example**:

```javascript
with open("data.txt", "r", encoding="utf-8") as file:
    while chunk := file.read(1024):
        print(chunk, end="")

```

### Opening, Writing Binary Files

Use `"rb"` or `"wb"` for images, etc.

**Example**:

```javascript
with open("source.jpg", "rb") as source:
    data = source.read()
with open("dest.jpg", "wb") as f:
    dest.write(data)

```

### Deleting and Renaming Files

Use `os` module, handle errors.

**Example**:

```javascript
import os
try:
    os.rename("old_data.txt", "new_data.txt")
    os.remove("temp.txt")
except FileNotFoundError:
    print("File not found.")

```

**Scripts**: Save as `file_operations.py` for file handling. Create `data.txt` and test binary files with small images.
