# DAY 10 - The Wrapper Patterns (Decorators)

## Micro-Challenges

### 
### 
### 
### 

---

### **DEEP DIVE: 10.1 Micro-Challenge - The Manual Wrapper**

**Goal:**
Write a function `wrapper(func)` that runs code before/after. Apply it manually:
`new_func = wrapper(old_func)`.

**Deep Dive:**
This demystifies the `@` syntax. A decorator is simply a function that takes a function and returns a function.

---

### **DEEP DIVE: 10.2 Micro-Challenge - The Syntax Sugar**

**Goal:**
Apply the wrapper using the `@decorator` syntax.

**Deep Dive:**
The `@` symbol is *Syntax Sugar*. At compile time, Python reads this and automatically performs the reassignment:
`func = decorator(func)`.

---

### **DEEP DIVE: 10.3 Micro-Challenge - The Args Problem**

**Goal:**
Try to decorate a function that takes arguments (`add(a, b)`) with a wrapper that takes none.

**Deep Dive:**
It crashes. The inner wrapper function **MUST** accept `*args` and `**kwargs` to be compatible with any target function signature.

---

### **DEEP DIVE: 10.4 Micro-Challenge - The Return Value Thief**

**Goal:**
Write a decorator that forgets to return `func(*args)`. Print the result of the decorated function.

**Deep Dive:**
It prints `None`. A wrapper must explicitly capture and return the result of the original function, otherwise the data is lost inside the wrapper scope.

---

### **DEEP DIVE: 10.5 Micro-Challenge - The Timer (Performance)**

**Goal:**
Create a `@timer` decorator that prints execution time using `time.time()`.

**Deep Dive:**
This is AOP (Aspect-Oriented Programming). We inject timing logic into the function without modifying the function’s actual code.

---

### **DEEP DIVE: 10.6 Micro-Challenge - The Authenticator (Guard)**

**Goal:**
Create `@admin_required`. If global `USER != 'admin'`, raise `PermissionError`.

**Deep Dive:**
The decorator acts as a gatekeeper. It executes *before* the sensitive function is entered. If the check fails, the stack frame for the target function is never even created.

---

### **DEEP DIVE: 10.7 Micro-Challenge - The Memorizer (Cache)**

**Goal:**
Write a `@cache` decorator that stores results of expensive function calls in a dictionary.

**Deep Dive:**
If `func(5)` is called, check the dict. If key `5` exists, return it instantly (`O(1)`).
If not, run the function and save the result. This optimizes recursion (e.g., Fibonacci).

---

### **DEEP DIVE: 10.8 Micro-Challenge - The Metadata Fix**

**Goal:**
Print `func.__name__` of a decorated function.

**Deep Dive:**
It prints `"wrapper"`, not the original name. This confuses debuggers.

**Fix:**
Use `@functools.wraps(func)` on the wrapper to copy the original metadata (name, docstring) to the new function.

---

### **DEEP DIVE: 10.9 Micro-Challenge - The Stacked Decorator**

**Goal:**
Apply two decorators: `@bold` and `@italic` to a string-returning function.

**Deep Dive:**
Decorators stack from **bottom to top** (Inner → Outer).
`@bold @italic` becomes `bold(italic(func()))`.
Order matters.

---

### **DEEP DIVE: 10.10 Micro-Challenge - Decorators with Arguments**

**Goal:**
Create a decorator that accepts a setting: `@repeat(times=3)`.

**Deep Dive:**
This requires **Three Levels of Nested Functions**:

1. The **Factory** (accepts `times`)
2. The **Decorator** (accepts `func`)
3. The **Wrapper** (accepts `*args`)
