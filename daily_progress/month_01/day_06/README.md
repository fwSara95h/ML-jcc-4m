# DAY 6 - Functions Modularity

Functions run in their own stack frame: 
- locals live and die there, and 
- names resolve by the LEGB rule 
    - Local -> Enclosing -> Global -> Built-in

## Micro-Challenges

### The Scope Fortress
Rebinding a name inside a function makes a fresh local; the global stays unchanged unless you explicitly opt in with the `global` keyword (rarely a good idea).

### The Pure Return
Every function returns something; omit the `return` statement and you get an implicit execution of `return None`. Returning values and letting callers decide whether to print/log is preferable.

### The Default Gateway
Default arguments store their value when the function is defined, so callers can skip common parameters without extra boilerplate.

### The Logic Gate
Comparisons already yield booleans, so you can just `return x == y` [etc] instead of wrapping it in extra `if`/`else` noise.
