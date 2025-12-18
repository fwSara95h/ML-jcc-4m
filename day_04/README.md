# DAY 4 - Lists (Data Structures I)

Lists are mutable, so assignment to a "new" variable just makes multiple names that point to the same list. Remember to copy (e.g.: with the `.copy` method) when we want to manipulate the new lists while preserving the original.

## Micro-Challenges

### The Reference Trap
`b = a` shares the same list; changing/mutating one changes the other. Use `b = a.copy()` or `b = a[:]` to avoid **aliasing** -- then we can make changes to `b` without affecting `a`.

### The Slicing Surgeon
Data **Slicing** (e.g., `data[-1:-4:-1]`) produces a new list from a trimmed and/or reversed selection while leaving the original untouched.

### The Stack Emulator
A list can be treated as a *LIFO* stack by using the *O(1)* methods `.append`/`.pop` to add/remove an element to/from the end, while `.insert(0, x)` is *O(n)* because pre-existing elements would need to shift.

### The One-Line Architect
**List Comprehension** builds a new list in a single [preferably readable] line of code and runs faster than a manual loop for the same outcome.
