# DAY 11 - Functional Programming (Lambda Map)


## Micro-Challenges

### 
### 
### 
### 

--- 

### **DEEP DIVE: 11.1 Micro-Challenge - The Anonymous Function**

**Goal:**
Write a function `add(x, y)` using `lambda`.

**Deep Dive:**
`lambda` creates a function object on the heap but assigns it no name (unless you bind it to a variable). It is purely syntactic sugar for single-expression functions.

---

### **DEEP DIVE: 11.2 Micro-Challenge - The Mapper**

**Goal:**
Square a list of numbers using `map()`.

**Deep Dive:**
`map(func, list)` pushes the loop into C-speed. It returns an iterator (lazy), not a list. You must cast it with `list()` to trigger execution.

---

### **DEEP DIVE: 11.3 Micro-Challenge - The Filter**

**Goal:**
Remove all negative numbers from a list using `filter()`.

**Deep Dive:**
`filter(func, list)` keeps items where `func(item)` returns Truthy. Passing `None` as the function automatically filters out Falsy values (`0`, `""`, `None`).

---

### **DEEP DIVE: 11.4 Micro-Challenge - The Reducer**

**Goal:**
Calculate the product of a list (`1 * 2 * 3 * 4`) using `functools.reduce`.

**Deep Dive:**
Reduce collapses a list into a single value. It takes item 1 and 2, applies the function, takes the result and item 3, applies again… until one item remains.

---

### **DEEP DIVE: 11.5 Micro-Challenge - The Custom Sort Key**

**Goal:**
Sort `["100px", "20px", "3px"]` numerically (so `3px` comes first).

**Deep Dive:**
`sorted(data, key=lambda x: int(x[:-2]))`.
The key function transforms the item **only for comparison purposes**, leaving the original data intact.

---

### **DEEP DIVE: 11.6 Micro-Challenge - The Zip Lock**

**Goal:**
Combine `names = ["A", "B"]` and `ages = [20, 30]` into a dictionary.

**Deep Dive:**
`dict(zip(names, ages))`.
`zip` creates an iterator of tuples. `dict()` consumes those tuples to build the hash map.

---

### **DEEP DIVE: 11.7 Micro-Challenge - List Comprehension Speed**

**Goal:**
Compare `map(lambda...)` vs `[x ... for x ...]`.

**Deep Dive:**
List comprehensions are generally faster than `map + lambda` because they avoid the overhead of calling a Python function frame for every single item.

---

### **DEEP DIVE: 11.8 Micro-Challenge - Any / All**

**Goal:**
Check if **any** number in a list is negative. Check if **all** are positive.

**Deep Dive:**
These are short-circuiting operators.

* `any()` stops at the first `True`.
* `all()` stops at the first `False`.
  This is **O(1)** in the best case.

---

### **DEEP DIVE: 11.9 Micro-Challenge - Partial Functions**

**Goal:**
Create a function `power(base, exp)`. Use `functools.partial` to create a new function `square(x)` that locks `exp = 2`.

**Deep Dive:**
Partials “freeze” arguments. This is useful when you need to pass a function to a callback (like in UI frameworks) that expects fewer arguments.

---

### **DEEP DIVE: 11.10 Micro-Challenge - The Immutability Test**

**Goal:**
Try to modify a tuple inside a `map` function.

**Deep Dive:**
Functional programming relies on **immutability**. Functions should not have side effects (modifying global state). They should receive input and return new output.

---

