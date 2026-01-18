# DAY 13 - Persistence (Files & Contexts)

## Micro-Challenges

### 
### 
### 
### 


---

### DEEP DIVE: 13.1 Micro-Challenge - **The Safe Open**

**Goal:** Write to a file without `.close()`.
**Deep Dive:** Use `with open(...) as f`. This is a Context Manager. It guarantees file closure even if an exception crashes the block.

---

### DEEP DIVE: 13.2 Micro-Challenge - **Append vs Write**

**Goal:** Add a log line to a file without deleting old content.
**Deep Dive:** Mode `'w'` wipes the file. Mode `'a'` appends to the end. Mode `'x'` fails if file exists (Safety).

---

### DEEP DIVE: 13.3 Micro-Challenge - **Binary Mode**

**Goal:** Read an image file.
**Deep Dive:** Use mode `'rb'`. Text modes decode bytes to String (UTF-8). Binary modes return raw bytes, essential for images/PDFs.

---

### DEEP DIVE: 13.4 Micro-Challenge - **Encoding Hell**

**Goal:** Fix a `"UnicodeDecodeError"`.
**Deep Dive:** Always specify `encoding='utf-8'`. Windows defaults to `'cp1252'`, which crashes on emojis or foreign characters.

---

### DEEP DIVE: 13.5 Micro-Challenge - **JSON Serialization**

**Goal:** Save a dictionary to a file.
**Deep Dive:** `json.dump()`. JSON is the standard for data exchange.
**Note:** JSON keys must be strings; Python allows integers, but JSON converts them.

---

### DEEP DIVE: 13.6 Micro-Challenge - **CSV Parsing**

**Goal:** Read a CSV into a list of dictionaries.
**Deep Dive:** Use `csv.DictReader`. It handles quoted strings and delimiters automatically, preventing bugs when data contains commas.

---

### DEEP DIVE: 13.7 Micro-Challenge - **Buffering**

**Goal:** Write 1 million lines. Why doesn’t the disk spin 1 million times?
**Deep Dive:** Python (and the OS) uses a **Buffer**. Data accumulates in RAM and is "Flushed" to disk in chunks to save I/O cycles.

---

### DEEP DIVE: 13.8 Micro-Challenge - **Pathlib**

**Goal:** Join a folder and filename safely on Windows and Mac.
**Deep Dive:** Do not use string concatenation `folder + "/" + file`. Use `pathlib.Path`. It handles OS-specific separators (`\` vs `/`) automatically.

---

### DEEP DIVE: 13.9 Micro-Challenge - **Custom Context Manager**

**Goal:** Create a block with `Timer():` that prints time taken.
**Deep Dive:** Implement `__enter__` (start timer) and `__exit__` (end timer).

---

### DEEP DIVE: 13.10 Micro-Challenge - **Pickle (The Warning)**

**Goal:** Save a Python Object (Class) to file.
**Deep Dive:** Use `pickle`.
**Warning:** Never unpickle data from untrusted sources. It can execute arbitrary code (Security Risk).

---