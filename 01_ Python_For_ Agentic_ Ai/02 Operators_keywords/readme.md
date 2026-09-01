<div align="center">

# ⚙️ Operators & Keywords

### The Complete Python Operators & Keywords Guide

*A simple, easy-to-follow guide to operators, operands, and reserved keywords in Python — with copy-paste-ready code examples. Basics first, advanced operators kept separate at the end.*

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white)
![Level](https://img.shields.io/badge/Level-Beginner%20to%20Advanced-4CAF50?style=flat-square)
![Focus](https://img.shields.io/badge/Focus-Operators%20%26%20Keywords-FF9800?style=flat-square)
![License](https://img.shields.io/badge/License-Free%20to%20Learn-informational?style=flat-square)

</div>

---

## 📖 About This Guide

This guide has three simple parts:

- **Part 1 — Basic Operators:** the ones you'll use in almost every line of Python you write.
- **Part 2 — Advanced Operators:** the ones you'll use less often, but every Python developer needs eventually.
- **Part 3 — Keywords:** Python's reserved words.

Every topic comes with a short, plain-English explanation and a runnable code example — copy it into your own `.py` file and try it.

---

## 📚 Table of Contents

**Part 1 — Basic Operators (Beginner)**
1. [What Is an Operator? What Is an Operand?](#1-what-is-an-operator-what-is-an-operand)
2. [Unary vs Binary Operators](#2-unary-vs-binary-operators)
3. [Arithmetic Operators](#3-arithmetic-operators)
4. [Comparison (Equality) Operators](#4-comparison-equality-operators)
5. [Logical Operators](#5-logical-operators)
6. [Assignment Operators](#6-assignment-operators)
7. [Quick Comparison — Basic Operators](#7-quick-comparison--basic-operators)

**Part 2 — Advanced Operators**
8. [Identity Operators — `is`, `is not`](#8-identity-operators--is-is-not)
9. [Membership Operators — `in`, `not in`](#9-membership-operators--in-not-in)
10. [Bitwise Operators](#10-bitwise-operators)
11. [The Walrus Operator `:=`](#11-the-walrus-operator-)
12. [Operator Precedence](#12-operator-precedence)

**Part 3 — Keywords**
13. [Python Keywords](#13-python-keywords)

**Reference**
14. [Full Comparison Table — Every Operator](#14-full-comparison-table--every-operator)
15. [Quick Revision](#15-quick-revision)
16. [📚 Further Reading](#16--further-reading)

---

# Part 1 — Basic Operators (Beginner)

## 1. What Is an Operator? What Is an Operand?

<svg viewBox="0 0 600 420" xmlns="http://www.w3.org/2000/svg" font-family="Arial, Helvetica, sans-serif">
  <defs>
    <marker id="arrowhead" markerWidth="8" markerHeight="8" refX="4" refY="4" orient="auto">
      <path d="M0,0 L8,4 L0,8 z" fill="#555555"/>
    </marker>
  </defs>
  <rect x="0" y="0" width="600" height="420" fill="#F2F2F2"/>
  <text x="300" y="55" text-anchor="middle" font-size="38" font-weight="800" fill="#3F3F3F">Operand vs. operator</text>
  <text x="205" y="112" text-anchor="middle" font-size="21" fill="#555555">Operators</text>
  <line x1="155" y1="128" x2="255" y2="128" stroke="#7A7A7A" stroke-width="1.5"/>
  <line x1="155" y1="128" x2="190" y2="176" stroke="#7A7A7A" stroke-width="1.5" marker-end="url(#arrowhead)"/>
  <line x1="255" y1="128" x2="222" y2="176" stroke="#7A7A7A" stroke-width="1.5" marker-end="url(#arrowhead)"/>
  <text x="130" y="255" text-anchor="middle" font-size="76" font-weight="900" fill="#C0392B">x</text>
  <text x="205" y="255" text-anchor="middle" font-size="70" font-weight="900" fill="#2471A3">+</text>
  <text x="280" y="255" text-anchor="middle" font-size="76" font-weight="900" fill="#C0392B">y</text>
  <text x="352" y="255" text-anchor="middle" font-size="66" font-weight="900" fill="#2471A3">=</text>
  <text x="430" y="255" text-anchor="middle" font-size="76" font-weight="900" fill="#229954">z</text>
  <line x1="130" y1="318" x2="280" y2="318" stroke="#7A7A7A" stroke-width="1.5"/>
  <line x1="130" y1="318" x2="130" y2="270" stroke="#7A7A7A" stroke-width="1.5" marker-end="url(#arrowhead)"/>
  <line x1="280" y1="318" x2="280" y2="270" stroke="#7A7A7A" stroke-width="1.5" marker-end="url(#arrowhead)"/>
  <text x="205" y="345" text-anchor="middle" font-size="21" fill="#555555">Operands</text>
  <line x1="410" y1="318" x2="450" y2="318" stroke="#7A7A7A" stroke-width="1.5"/>
  <line x1="430" y1="318" x2="430" y2="270" stroke="#7A7A7A" stroke-width="1.5" marker-end="url(#arrowhead)"/>
  <text x="430" y="345" text-anchor="middle" font-size="21" fill="#555555">Results</text>
</svg>

> **Operator** — a symbol that does an action (like `+`, `-`, `*`, `/`).
> **Operand** — the value(s) the operator works on.

In the picture: `x` and `y` are the **operands** (the inputs), `+` is the **operator** (the action), and `z` is the **result**.

```python
x = 3
y = 4
z = x + y   # '+' is the operator, x and y are operands, z is the result

print(z)
```

```text
7
```

**Simple way to remember it:** operands are the *ingredients*, the operator is the *action*, and the result is what comes out.

### 🔗 Learn More
- [Python Official Docs — Expressions](https://docs.python.org/3/reference/expressions.html)
- [Real Python — Operators and Expressions in Python](https://realpython.com/python-operators-expressions/)
- [W3Schools — Python Operators](https://www.w3schools.com/python/python_operators.asp)

---

## 2. Unary vs Binary Operators

> **Unary operator** — needs **one** operand.
> **Binary operator** — needs **two** operands.

### Unary Operators

**Negative (`-`)** flips a number's sign:

```python
x = 5
y = -x
print("y =", y)
```

```text
y = -5
```

**Logical NOT (`not`)** flips a `True`/`False` value:

```python
a = True
b = not a
print("b =", b)
```

```text
b = False
```

> 💡 There's also a **bitwise NOT (`~`)** — a more advanced unary operator. It's covered with the rest of the bitwise operators in [Part 2, Section 10](#10-bitwise-operators).

### Binary Operators

Binary operators need two operands. Most operators you'll use daily are binary — arithmetic (`+`, `-`), comparison (`==`, `>`), logical (`and`, `or`), and assignment (`=`, `+=`). Each has its own section below.

**Easy way to tell them apart:**
- Unary → one operand → `-x`, `not a`
- Binary → two operands → `a + b`, `x > y`

### 🔗 Learn More
- [Python Official Docs — Unary Arithmetic Operations](https://docs.python.org/3/reference/expressions.html#unary-arithmetic-and-bitwise-operations)
- [Real Python — Boolean Operators in Python](https://realpython.com/python-boolean/)
- [GeeksforGeeks — Unary Operators in Python](https://www.geeksforgeeks.org/unary-operators-python/)

---

## 3. Arithmetic Operators

Used for basic math.

| Operator | Name | Example |
|---|---|---|
| `+` | Addition | `5 + 2 = 7` |
| `-` | Subtraction | `5 - 2 = 3` |
| `*` | Multiplication | `5 * 2 = 10` |
| `/` | Division (always gives a float) | `5 / 2 = 2.5` |
| `//` | Floor Division (drops the decimal) | `5 // 2 = 2` |
| `%` | Modulus (the remainder) | `5 % 2 = 1` |
| `**` | Exponentiation (power) | `5 ** 2 = 25` |

```python
a = 10
b = 3

print("a + b  =", a + b)     # Addition
print("a - b  =", a - b)     # Subtraction
print("a * b  =", a * b)     # Multiplication
print("a / b  =", a / b)     # Division
print("a // b =", a // b)    # Floor Division
print("a % b  =", a % b)     # Modulus
print("a ** b =", a ** b)    # Exponentiation
```

```text
a + b  = 13
a - b  = 7
a * b  = 30
a / b  = 3.3333333333333335
a // b = 3
a % b  = 1
a ** b = 1000
```

> 💡 `/` always gives a `float`, even if the numbers divide evenly (`10 / 2` gives `5.0`, not `5`). Want a whole number instead? Use `//`.

### 🔗 Learn More
- [Python Official Docs — Arithmetic Operations](https://docs.python.org/3/reference/expressions.html#binary-arithmetic-operations)
- [Real Python — Basic Math in Python](https://realpython.com/python-numbers/)
- [W3Schools — Python Arithmetic Operators](https://www.w3schools.com/python/python_operators.asp)

---

## 4. Comparison (Equality) Operators

Used to compare two values. Every comparison gives back `True` or `False`. These are also called **relational** or **equality** operators.

| Operator | Name | Example |
|---|---|---|
| `==` | Equal | `5 == 5 → True` |
| `!=` | Not equal | `5 != 3 → True` |
| `>` | Greater than | `5 > 3 → True` |
| `<` | Less than | `5 < 3 → False` |
| `>=` | Greater than or equal | `5 >= 5 → True` |
| `<=` | Less than or equal | `5 <= 3 → False` |

```python
x = 5
y = 3

print("x == y =", x == y)
print("x != y =", x != y)
print("x > y  =", x > y)
print("x < y  =", x < y)
print("x >= y =", x >= y)
print("x <= y =", x <= y)
```

```text
x == y = False
x != y = True
x > y  = True
x < y  = False
x >= y = True
x <= y = False
```

### Chained comparisons

Python lets you chain comparisons in a single line, instead of repeating the same variable twice.

```python
x = 15

if 10 < x < 20:
    print("x is between 10 and 20")
```

```text
x is between 10 and 20
```

Behind the scenes, `10 < x < 20` means exactly the same as `10 < x and x < 20` — just shorter to write and easier to read.

### 🔗 Learn More
- [Python Official Docs — Comparisons](https://docs.python.org/3/reference/expressions.html#comparisons)
- [Real Python — Chaining Comparison Operators](https://realpython.com/python-boolean/#chaining-comparison-operators)
- [W3Schools — Python Comparison Operators](https://www.w3schools.com/python/python_operators.asp)

---

## 5. Logical Operators

Used to combine multiple `True`/`False` conditions.

| Operator | Name | Example |
|---|---|---|
| `and` | Logical AND — both must be true | `(5 > 3 and 10 > 5) → True` |
| `or` | Logical OR — at least one must be true | `(5 > 3 or 10 < 5) → True` |
| `not` | Logical NOT — flips the value | `not(5 > 3) → False` |

```python
x = True
y = False

print("x and y =", x and y)
print("x or y  =", x or y)
print("not x   =", not x)
```

```text
x and y = False
x or y  = True
not x   = False
```

### 🔗 Learn More
- [Python Official Docs — Boolean Operations](https://docs.python.org/3/reference/expressions.html#boolean-operations)
- [Real Python — Logical Operators in Python](https://realpython.com/python-boolean/#the-and-or-and-not-boolean-operators)
- [W3Schools — Python Logical Operators](https://www.w3schools.com/python/python_operators.asp)

---

## 6. Assignment Operators

Used to give a value to a variable — plus shorthand versions that update a variable based on its current value.

| Operator | Example | Same As |
|---|---|---|
| `=` | `x = 5` | `x = 5` |
| `+=` | `x += 3` | `x = x + 3` |
| `-=` | `x -= 3` | `x = x - 3` |
| `*=` | `x *= 3` | `x = x * 3` |
| `/=` | `x /= 3` | `x = x / 3` |
| `//=` | `x //= 3` | `x = x // 3` |
| `%=` | `x %= 3` | `x = x % 3` |
| `**=` | `x **= 3` | `x = x ** 3` |

```python
x = 5
print("x = 5      ", x)

x += 3
print("x += 3     ", x)

x -= 3
print("x -= 3     ", x)

x *= 3
print("x *= 3     ", x)

x /= 3
print("x /= 3     ", x)

x //= 3
print("x //= 3    ", x)
```

```text
x = 5       5
x += 3      8
x -= 3      5
x *= 3      15
x /= 3      5.0
x //= 3     1.0
```

**Why use shorthand?**
- **Shorter code** — easier to scan at a glance.
- **Less repeating** — you don't retype the variable name.
- **Standard style** — used everywhere in real Python code.

### 🔗 Learn More
- [Python Official Docs — Augmented Assignment Statements](https://docs.python.org/3/reference/simple_stmts.html#augmented-assignment-statements)
- [Real Python — Augmented Assignment Operators](https://realpython.com/python-operators-expressions/#augmented-assignment-operators)
- [W3Schools — Python Assignment Operators](https://www.w3schools.com/python/python_operators.asp)

---

## 7. Quick Comparison — Basic Operators

One table with all four **basic** operator families, side by side, before moving on to the advanced ones.

| Category | Operators | What it does | Returns |
|---|---|---|---|
| **Arithmetic** | `+` `-` `*` `/` `//` `%` `**` | Does math on numbers | A number |
| **Comparison / Equality** | `==` `!=` `>` `<` `>=` `<=` | Compares two values | `True` / `False` |
| **Logical** | `and` `or` `not` | Combines `True`/`False` conditions | `True` / `False` |
| **Assignment** | `=` `+=` `-=` `*=` `/=` `//=` `%=` `**=` | Stores or updates a variable | Nothing — it's a statement |

> 💡 **Quick way to tell them apart:** math → **arithmetic**. Yes/no question about two values → **comparison**. Combining two yes/no answers → **logical**. Putting a value into a variable → **assignment**.

That covers everything a beginner needs day to day. Ready for more? **Part 2** below covers the operators you'll need less often, but will definitely run into.

---

# Part 2 — Advanced Operators

## 8. Identity Operators — `is`, `is not`

Checks whether two variables point to the **exact same object in memory** — not just whether they hold equal values.

| Operator | Meaning | Example |
|---|---|---|
| `is` | `True` if both point to the same object | `x is y` |
| `is not` | `True` if they point to different objects | `x is not y` |

```python
a = [1, 2, 3]
b = [1, 2, 3]
c = a

print("a is c     =", a is c)        # True  — c points to the same object as a
print("a is b     =", a is b)        # False — separate objects, same values
print("a == b     =", a == b)        # True  — values match
print("a is not b =", a is not b)    # True  — different objects
```

```text
a is c     = True
a is b     = False
a == b     = True
a is not b = True
```

You can prove this with `id()`, which shows each object's memory address:

```python
print("id(a) =", id(a))
print("id(b) =", id(b))
print("id(c) =", id(c))
```

```text
id(a) = 134193929171776
id(b) = 134193940649408
id(c) = 134193929171776
```

`id(a)` and `id(c)` match — proof that `a` and `c` are the same object — while `id(b)` is completely different.

> ⚠️ **Rule of thumb:** use `==` to compare values. Save `is` for checking `None` (`if x is None:`) or confirming two variables are the exact same object on purpose.

### 🔗 Learn More
- [Python Official Docs — Identity Comparisons](https://docs.python.org/3/reference/expressions.html#is)
- [Real Python — Identity vs Equality in Python](https://realpython.com/python-is-identity-vs-equality/)
- [GeeksforGeeks — Identity Operators in Python](https://www.geeksforgeeks.org/python-identity-operators/)

---

## 9. Membership Operators — `in`, `not in`

Checks whether a value exists inside a sequence — a `list`, `tuple`, `set`, `dict`, or `str`.

| Operator | Meaning | Example |
|---|---|---|
| `in` | `True` if the value is found | `x in my_list` |
| `not in` | `True` if the value is NOT found | `x not in my_list` |

```python
my_list = [1, 2, 3, 4, 5]

print("my_list           =", my_list)
print("3 in my_list      =", 3 in my_list)
print("10 not in my_list =", 10 not in my_list)

my_string = "Operation Badar"

print("'O' in my_string         =", 'O' in my_string)
print("'Hello' not in my_string =", 'Hello' not in my_string)
```

```text
my_list           = [1, 2, 3, 4, 5]
3 in my_list      = True
10 not in my_list = True
'O' in my_string         = True
'Hello' not in my_string = True
```

### 🔗 Learn More
- [Python Official Docs — Membership Test Operations](https://docs.python.org/3/reference/expressions.html#membership-test-operations)
- [Real Python — The Python `in` and `not in` Operators](https://realpython.com/python-in-operator/)
- [W3Schools — Python Membership Operators](https://www.w3schools.com/python/python_operators.asp)

---

## 10. Bitwise Operators

These work directly on the individual **bits** (0s and 1s) inside a number. You won't need them every day, but they matter for low-level work like flags and performance-sensitive code.

| Operator | Name | What it does |
|---|---|---|
| `&` | AND | `1` only where **both** bits are `1` |
| `\|` | OR | `1` where **at least one** bit is `1` |
| `^` | XOR | `1` where the bits are **different** |
| `~` | NOT | Flips every bit |
| `<<` | Left Shift | Shifts bits left, fills with `0` (multiplies by powers of 2) |
| `>>` | Right Shift | Shifts bits right (divides by powers of 2) |

```python
a = 5     # binary: 0101
b = 3     # binary: 0011

print("a & b  =", a & b)     # AND
print("a | b  =", a | b)     # OR
print("a ^ b  =", a ^ b)     # XOR
print("~a     =", ~a)        # NOT
print("a << 1 =", a << 1)    # Left shift
print("a >> 1 =", a >> 1)    # Right shift
```

```text
a & b  = 1
a | b  = 7
a ^ b  = 6
~a     = -6
a << 1 = 10
a >> 1 = 2
```

See any integer's binary form with `bin()`:

```python
x = 5
print(bin(x), type(bin(x)))
```

```text
0b101 <class 'str'>
```

> 💡 `a << 1` doubles a number, and `a >> 1` halves it (rounding down) — a classic speed trick, though `*` and `//` work just as well and read more clearly.

### 🔗 Learn More
- [Python Official Docs — Bitwise Operations](https://docs.python.org/3/reference/expressions.html#binary-bitwise-operations)
- [Real Python — Bitwise Operators in Python](https://realpython.com/python-bitwise-operators/)
- [GeeksforGeeks — Bitwise Operators in Python](https://www.geeksforgeeks.org/python-bitwise-operators/)

---

## 11. The Walrus Operator `:=`

Added in Python 3.8, the **walrus operator** lets you **assign a value and use it in the same line**, instead of writing two separate lines.

```python
data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]

if (n := len(data)) > 10:
    print(f"List is long: {n} items")
```

```text
List is long: 11 items
```

Without it, you'd need two lines:

```python
n = len(data)
if n > 10:
    print(f"List is long: {n} items")
```

**Where it shines:** loops and conditions where you'd otherwise calculate the same thing twice.

```python
if (user_input := input("Enter a number: ")) and user_input.isdigit():
    print(f"You entered: {user_input}")
else:
    print("Invalid input. Please enter a valid number.")
```

```text
Enter a number: 7
You entered: 7
```

### 🔗 Learn More
- [Python Official Docs — Assignment Expressions](https://docs.python.org/3/reference/expressions.html#assignment-expressions)
- [PEP 572 — Assignment Expressions](https://peps.python.org/pep-0572/)
- [Real Python — The Walrus Operator: Python's Assignment Expressions](https://realpython.com/python-walrus-operator/)

---

## 12. Operator Precedence

When one line has more than one operator, Python doesn't just go left to right — it follows a fixed **order**, just like "PEMDAS" in math class.

**Highest to lowest priority (simplified):**

| Priority | Operators | Example |
|---|---|---|
| 1 (highest) | `()` | Parentheses — always go first |
| 2 | `**` | Exponentiation |
| 3 | `~`, unary `-`, `+` | Unary operators |
| 4 | `*`, `/`, `//`, `%` | Multiplication, division |
| 5 | `+`, `-` | Addition, subtraction |
| 6 | `<<`, `>>` | Bit shifts |
| 7 | `&` | Bitwise AND |
| 8 | `^` | Bitwise XOR |
| 9 | `\|` | Bitwise OR |
| 10 | `==`, `!=`, `>`, `<`, `>=`, `<=`, `is`, `in` | Comparisons |
| 11 | `not` | Logical NOT |
| 12 | `and` | Logical AND |
| 13 (lowest) | `or` | Logical OR |

```python
result = 2 + 3 * 4
print(result)          # multiplication runs first: 2 + 12

result2 = (2 + 3) * 4
print(result2)          # parentheses force addition first: 5 * 4
```

```text
14
20
```

> 💡 **When unsure, use parentheses.** `(a + b) * c` is instantly clear to anyone reading your code, even if they don't remember the exact precedence order.

### 🔗 Learn More
- [Python Official Docs — Operator Precedence](https://docs.python.org/3/reference/expressions.html#operator-precedence)
- [Real Python — Operator Precedence in Python](https://realpython.com/python-operators-expressions/#operator-precedence)
- [GeeksforGeeks — Operator Precedence in Python](https://www.geeksforgeeks.org/precedence-and-associativity-of-operators-in-python/)

---

# Part 3 — Keywords

## 13. Python Keywords

**Keywords** are reserved words that already have a special job built into Python. You **cannot** use a keyword as a variable, function, or class name — Python's grammar depends on these exact words.

```python
import keyword

print(keyword.kwlist)
```

```text
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await',
 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except',
 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is',
 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try',
 'while', 'with', 'yield']
```

Using one as a variable name crashes your program right away:

```python
class = "Python 101"   # SyntaxError: invalid syntax
```

```text
SyntaxError: invalid syntax
```

Check if any word is reserved, without memorizing the whole list:

```python
import keyword

print(keyword.iskeyword("for"))     # True — reserved
print(keyword.iskeyword("total"))   # False — safe to use
```

```text
True
False
```

### Soft keywords — a newer, more relaxed kind

Since Python 3.9, a small set of **soft keywords** were added: `match`, `case`, `_`, and `type`. They only have special meaning in specific situations (like a `match` statement) — unlike regular keywords, you can still use them as normal variable names everywhere else.

```python
import keyword

print(keyword.softkwlist)
```

```text
['_', 'case', 'match', 'type']
```

```python
# 'match' is a soft keyword — still works fine as a variable name
match = "This is allowed"
print(match)
```

```text
This is allowed
```

### 🔗 Learn More
- [Python Official Docs — Keywords](https://docs.python.org/3/reference/lexical_analysis.html#keywords)
- [Python Official Docs — `keyword` module](https://docs.python.org/3/library/keyword.html)
- [Real Python — Python Keywords: An Introduction](https://realpython.com/python-keywords/)

---

# Reference

## 14. Full Comparison Table — Every Operator

Every operator from Part 1 and Part 2, side by side, in one place.

| Category | Level | Operators | What it does | Returns |
|---|---|---|---|---|
| Arithmetic | Basic | `+` `-` `*` `/` `//` `%` `**` | Does math on numbers | A number |
| Comparison / Equality | Basic | `==` `!=` `>` `<` `>=` `<=` | Compares two values | `True` / `False` |
| Logical | Basic | `and` `or` `not` | Combines conditions | `True` / `False` |
| Assignment | Basic | `=` `+=` `-=` `*=` `/=` `//=` `%=` `**=` | Stores/updates a variable | Nothing (a statement) |
| Identity | Advanced | `is` `is not` | Checks if two variables are the same object | `True` / `False` |
| Membership | Advanced | `in` `not in` | Checks if a value exists in a sequence | `True` / `False` |
| Bitwise | Advanced | `&` `\|` `^` `~` `<<` `>>` | Works on individual bits | A number |
| Assignment expression | Advanced | `:=` | Assigns and returns a value in one go | The assigned value |

### 🔗 Learn More
- [Python Official Docs — Expressions](https://docs.python.org/3/reference/expressions.html)
- [Real Python — Operators and Expressions in Python](https://realpython.com/python-operators-expressions/)
- [GeeksforGeeks — Python Operators](https://www.geeksforgeeks.org/python-operators/)

---

## 15. Quick Revision

- An **operator** is a symbol that does something; an **operand** is the value it works on.
- **Unary** operators need one operand (`-x`); **binary** operators need two (`a + b`).
- **Part 1 (Basic):** arithmetic, comparison/equality, logical, and assignment operators cover almost everything you'll write day to day.
- **Part 2 (Advanced):** identity (`is`), membership (`in`), bitwise (`&`, `|`, `^`, `~`, `<<`, `>>`), and the walrus operator (`:=`) come up less often but matter a lot.
- `is` checks if two variables point to the **same object in memory**; `==` checks if their **values** match — not the same thing.
- **Operator precedence** decides the order operations run in when a line has more than one — use `()` whenever it makes the code clearer.
- **Keywords** are reserved words you can never use as a variable name; **soft keywords** (`match`, `case`, `_`, `type`) are more flexible.

---

## 16. 📚 Further Reading

> Want to go deeper on any topic in this guide? Start here.

| Topic | Resource |
|---|---|
| Official reference | [Python Docs — Expressions](https://docs.python.org/3/reference/expressions.html) |
| Operator precedence | [Python Docs — Operator Precedence Table](https://docs.python.org/3/reference/expressions.html#operator-precedence) |
| Keywords module | [Python Docs — `keyword` module](https://docs.python.org/3/library/keyword.html) |
| Walrus operator | [PEP 572 — Assignment Expressions](https://peps.python.org/pep-0572/) |
| Deep tutorials | [Real Python — Operators and Expressions in Python](https://realpython.com/python-operators-expressions/) |
| Beginner-first explanations | [W3Schools — Python Operators](https://www.w3schools.com/python/python_operators.asp) |
| Practice problems | [GeeksforGeeks — Python Operators](https://www.geeksforgeeks.org/python-operators/) |
| Bitwise deep dive | [Real Python — Bitwise Operators in Python](https://realpython.com/python-bitwise-operators/) |

---

<div align="center">

### 🎉 You made it!

You now know what operators and operands are, every basic operator you'll use daily, the advanced operators you'll need eventually, and how Python's reserved keywords work.

**Next step:** open a Python file and try every example in this guide yourself. ⚙️

</div>