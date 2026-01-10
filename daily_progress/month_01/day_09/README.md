# DAY 9 - Infinite Memory (Generators)

## Micro-Challenges

### 
### 
### 
### 
### 
### 
### 
### 
### 
### 



---

### **DEEP DIVE: 9.1 Micro-Challenge -- The Basic Yield**

**Goal:**
Write a function `gen()` that yields `1`, then `2`, then `3`. Loop through it.

**Deep Dive:**
Unlike `return`, `yield` pauses the function and saves the **Stack Frame** (local variables) in RAM. The function is “frozen” until you call it again.

---

### **DEEP DIVE: 9.2 Micro-Challenge -- The Memory Profile**

**Goal:**
Compare `sys.getsizeof()` of a **List Comprehension** vs a **Generator Expression** for 1 million numbers.

**Deep Dive:**

* `[x for x in range(1M)]` consumes ~8MB RAM (stores all numbers).
* `(x for x in range(1M))` consumes ~100 bytes (stores only the logic).

---

### **DEEP DIVE: 9.3 Micro-Challenge -- The Infinite Sequence**

**Goal:**
Write a `while True` generator that produces Fibonacci numbers forever.

**Deep Dive:**
This is impossible with a standard list (RAM would fill up). Generators allow **Infinite Data Streams** because they process one item at a time (**Lazy Evaluation**).

---

### **DEEP DIVE: 9.4 Micro-Challenge -- The One-Time Trap**

**Goal:**
Create a generator `g`. Loop through it once. Try to loop through it again.

**Deep Dive:**
Generators are **Exhaustible**. Once iterated, the “cursor” is at the end. You cannot rewind a generator; you must re-instantiate it.

---

### **DEEP DIVE: 9.5 Micro-Challenge -- The Next Protocol**

**Goal:**
Manually call `next(gen)` until it crashes.

**Deep Dive:**
When a generator runs out of items, it raises a **StopIteration** exception. `for` loops catch this exception silently to stop looping.

---

### **DEEP DIVE: 9.6 Micro-Challenge -- The Pipeline (Chaining)**

**Goal:**
Create two generators: one squares numbers, the other filters evens. Chain them:
`filter(square(nums))`.

**Deep Dive:**
This creates a **Data Pipeline**. Data flows from source → square → filter **one item at a time**. No intermediate lists are created in RAM.

---

### **DEEP DIVE: 9.7 Micro-Challenge -- The Large File Reader**

**Goal:**
Write a generator to read a “fake” 100GB file line-by-line.

**Deep Dive:**
Using `yield line` allows you to process datasets larger than your machine’s physical RAM. This is the standard for **Big Data processing** in Python.

---

### **DEEP DIVE: 9.8 Micro-Challenge -- Yield From**

**Goal:**
Write a generator that yields values from two different sub-generators using `yield from`.

**Deep Dive:**
`yield from` delegates the generator operation to another sub-generator. It flattens nested structures efficiently without manual loops.

---

### **DEEP DIVE: 9.9 Micro-Challenge -- The Send Method**

**Goal:**
Use `gen.send(value)` to inject data **into** a running generator.

**Deep Dive:**
Generators can be **two-way streets**.
`val = yield` pauses and waits to receive data from the outside world.
This is the basis for **Coroutines (AsyncIO)**.

---

### **DEEP DIVE: 9.10 Micro-Challenge -- State Retention**

**Goal:**
Write a generator that calculates a **Running Average**.

**Deep Dive:**
The generator remembers the `total` and `count` variables between yields. This eliminates the need for global variables or class attributes.


