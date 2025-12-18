# DAY 4 - Lists (Data Structures I)

Lists are mutable, so assignment just makes two names point at the same list. Make sure to copy (e.g.: with the `.copy` method) when you want independence.

## Micro-Challenges

### The Reference Trap
`b = a` shares the same list; mutating one changes the other. Copy with `a.copy()` or `a[:]` to avoid **aliasing**.

### The Slicing Surgeon
**Slicing** (e.g., `data[-1:-4:-1]`) returns a new list, leaving the original untouched while giving you a trimmed and/or reversed selection.

### The Stack Emulator
Treat a list as a *LIFO* stack: `append`/`pop` from the end are O(1), while `insert(0, x)` is *O(n)* because everything needs to shift.

### The One-Line Architect
**List Comprehensions** build lists in a single [preferably readable] line and run faster than manual loops for the same outcome.
