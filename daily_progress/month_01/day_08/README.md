# DAY 8 - The Physics of Code (Time Complexity)

Briefly: some operations scale with N (*linear*), some are constant/instant ($O(1)$), and a few explode fast (e.g.: quadratic). Essential to know which is which before we code ourselves into a corner and the program hangs unexpectectedly (or worse).

## Micro-Challenges

### The Linear Scan ($O(N)$)
Linear search checks items one by one; double the data, double the time.

### The Hash Lookup ($O(1)$)
Set/dict lookup hashes the key and jumps to the slot. Size barely matters.

### The Insertion Trap ($O(N)$)
`append` is cheap, `insert(0, x)` shifts everything right and gets slow fast.

### The Queue Bottleneck (Pop)
`.pop()` from the end is $O(1)$; `.pop(0)` forces a left shift of the rest.

### The String Builder ($O(N^2)$)
Strings are immutable, so repeated `+=` keeps copying. Better use `"".join()` instead.

### The Length Trick ($O(1)$)
`len()` reads cached size metadata, not a full count.

### The Quadratic Nested Loop ($O(N^2)$)
Nested loops over two lists blow up quickly and are a common timeout culprit.

### The Sorting Cost ($O(N\log N)$)
Timsort is efficient, but still heavy. Do not sort inside loops.

### The Dictionary Creator ($O(N)$)
Lookup is $O(1)$, but building the dict costs $O(N)$ to hash and allocate.

### The Slice Copy ($O(k)$)
Slicing copies references into a new list, so time scales with slice size.
