# DAY 14 - The Final Boss (Algorithmic Logic)

## Micro-Challenges

### 
### 
### 
### 

---

### 📘 DEEP DIVE: 14.1 Capstone: **Two Sum (O(N))**

**Goal:** Find two numbers in a list that add up to Target.
**Deep Dive:** Naive: Nested Loops *(O(N²))*. Pro: Use a Dictionary (Seen Map). Calculate `needed = target - current`. If `needed` is in `map`, you win.

---

### 📘 DEEP DIVE: 14.2 Capstone: **The Palindrome (Slicing)**

**Goal:** Check if a string is a palindrome (ignoring space/case).
**Deep Dive:** Clean string → `s == s[::-1]`. Slicing creates a reversed copy in memory.

---

### 📘 DEEP DIVE: 14.3 Capstone: **Anagrams (Frequency)**

**Goal:** Are "silent" and "listen" anagrams?
**Deep Dive:**

1. Sort both (O(N log N)).
2. Count frequencies: `{ 's': 1, 'i': 1... }` (O(N)).
   Use `collections.Counter`.

---

### 📘 DEEP DIVE: 14.4 Capstone: **Flattening (Recursion)**

**Goal:** Flatten `[1, [2, [3, 4]]]` into `[1, 2, 3, 4]`.
**Deep Dive:** Write a recursive function. If item is list → recurse. Else → yield.

---

### 📘 DEEP DIVE: 14.5 Capstone: **FizzBuzz (The Logic Gate)**

**Goal:** Print 1-100. Div by 3 "Fizz", by 5 "Buzz", both "FizzBuzz".
**Deep Dive:** Order matters! Check `% 15` (both) FIRST. If you check 3 first, "FizzBuzz" numbers will just print "Fizz".

---

### 📘 DEEP DIVE: 14.6 Capstone: **Deduplication (O(N))**

**Goal:** Remove duplicates from a list while keeping order.
**Deep Dive:** `list(set(x))` destroys order. Solution: Iterate, check if item in seen_set, if not → append to result.

---

### 📘 DEEP DIVE: 14.7 Capstone: **Binary Search (O(log N))**

**Goal:** Find index of number in sorted list.
**Deep Dive:** Check middle. If too low, eliminate left half. If too high, eliminate right half. Repeat. Much faster than scanning.

---

### 📘 DEEP DIVE: 14.8 Capstone: **Missing Number (Math)**

**Goal:** List 1 to 100 is missing one number. Find it.
**Deep Dive:** Don’t scan. Calculate Expected Sum `N(N+1)/2`. Subtract Actual Sum. The difference is the missing number.

---

### 📘 DEEP DIVE: 14.9 Capstone: **Grouping (itertools)**

**Goal:** Group list of dicts by "category".
**Deep Dive:** Use `itertools.groupby`.
**Note:** Data MUST be sorted by the key first!

---

### 📘 DEEP DIVE: 14.10 Capstone: **Merge Sorted Lists**

**Goal:** Combine two sorted lists into one sorted list (O(N)).
**Deep Dive:** Two Pointers. Compare head of A and head of B. Take smaller. Move pointer. Repeat.

---

