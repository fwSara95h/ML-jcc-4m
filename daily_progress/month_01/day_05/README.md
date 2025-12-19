# DAY 5 - Hash Tables (Dictionaries)

Dictionaries are key-value stores with near-instant (*O(1)*) lookups via hashing, while lists must scan linearly (*O(n)*).

** Note that dicts/sets , unlike lists , are **unordered**.

## Micro-Challenges

### The Speed Trap (Lookup)
List membership walks every element, while dicts/sets hash the key to jump straight to its slot, so lookups stay O(1) even with huge collections.

### The Safe Vault
Use membership checks or `.get(key, default)` to read without **KeyError**, and remember to initialize missing keys before writing so the store stays consistent.

### The Frequency Counter
Count on the fly: if a hashed slot is empty, create the key with 1; if it exists, bump the count. (That's also the basic pattern behind `Counter`.)

### The Database Merger
Merging dicts iterates the new entries and overwrites any matching keys (e.g., `prefs = base | override`), keeping originals when no collision occurs.
