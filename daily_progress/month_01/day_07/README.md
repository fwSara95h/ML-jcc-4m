# DAY 7 - Error Handling (Exceptions)

Errors bubble up the call stack; `try/except` lets you catch them so one bad input doesn�t crash a whole run. Use `finally` for cleanup that must always happen.

## Micro-Challenges

### The Input Guard
Wrap risky parsing in `try/except ValueError` so bad inputs fall back gracefully instead of killing the program.

### The Math Safety Net
Catch `ZeroDivisionError` to skip or patch invalid rows instead of stopping long-running jobs.

### The Cleanup Crew
Put must-run cleanup (closing files, releasing connections) in `finally` so it executes even on errors or early returns.

### The Custom Signal
`raise` your own exceptions to enforce rules and let callers decide how to handle the failure.
