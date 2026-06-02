# 🥷 Bandit OverTheWire: Logbook & Mission Notes

This folder contains my active documentation, commands, and logic mapping for the **OverTheWire: Bandit** wargame levels. It serves as my external brain to track progress and consolidate my terminal muscle memory.

---

## 🧭 Level Walkthrough & Core Concepts

### 📂 Level 0 ➔ Level 1: Standard File Reading

**Concept:** Opening a standard, visible file.

**Command:**
```bash
cat readme
```

---

### 📂 Level 1 ➔ Level 2: Bypassing the Dash (-)

**Concept:**  
When a filename is just a dash (`-`), `cat -` will confuse Linux into waiting for keyboard input. We use a relative path to force it to read the file.

**Command:**
```bash
cat ./-
```

---

### 📂 Level 2 ➔ Level 3: Dealing with Spaces & Dashes

**Concept:**  
Filenames containing both spaces and dashes (e.g., `--spaces in this filename--`) can trick Linux into reading them as command options/flags. Wrapping the name in quotes locks it as a single file entity.

**Command:**
```bash
cat "--spaces in this filename--"
```

---

### 📂 Level 3 ➔ Level 4: Navigating Directories & Hidden Files

**Concept:**  
Directories cannot be opened with `cat`; you must use `cd` to navigate. To see files intentionally hidden by the system (filenames starting with a dot `.`), use the "all" flag.

**Commands:**
```bash
cd inhere/
ls -a
```

---

### 📂 Level 4 ➔ Level 5: Filtering Human-Readable Text

**Concept:**  
When a directory is cluttered with corrupted binary files, we filter for human-readable ASCII text to identify the correct target without messing up the terminal.

**Commands:**
```bash
file ./*
cat -- ./-file07
```

> Adjust the file number based on the ASCII text output from the `file` command.

---

### 📂 Level 5 ➔ Level 6: Advanced Multi-Property Search

**Concept:**  
Searching deep inside a labyrinth of multiple sub-folders for a non-executable file that matches an exact byte size.

**Command:**
```bash
find . -type f -size 1033c ! -executable
```

> c is bytes

---

### 📂 Level 6 ➔ Level 7: System-Wide Scanning & Noise Suppression

**Concept:**  
Scanning the entire server root (`/`) based on user and group ownership. We attach error redirection (`2>/dev/null`) to suppress and hide thousands of annoying `Permission denied` messages.

**Command:**
```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

---

### 📂 Level 7 ➔ Level 8: Targeted Keyword Filtering (grep)

**Concept:**  
Isolating a single line of text out of thousands of chaotic lines using a precise keyword provided by the mission statement.

**Command:**
```bash
grep "millionth" data.txt
```

---

### 📂 Level 8 ➔ Level 9: Isolating Unique Lines (Piping `|`)

**Concept:**  
Finding the only line of text that occurs exactly once. We chain commands together using a pipe (`|`): first we sort the text alphabetically so duplicates sit together, then filter for the absolute unique line.

**Command:**
```bash
sort data.txt | uniq -u
```
