# 🥷 Bandit OverTheWire: Logbook & Mission Notes

This folder contains my active documentation, commands, and logic mapping for the **OverTheWire: Bandit** wargame levels. It serves as my external brain to track progress and consolidate my terminal muscle memory.

---

# 🧭 Level Walkthrough & Core Concepts

## 📂 Level 0 ➔ Level 1: Standard File Reading

### Concept

Opening a standard, visible file.

### Command

```bash
cat readme
```

### How to Read the Command Logic

* `cat` → Opens and reads the contents of a file.
* `readme` → The specific target file name.

---

## 📂 Level 1 ➔ Level 2: Bypassing the Dash (-)

### Concept

When a filename is just a dash (`-`), `cat -` will confuse Linux into waiting for keyboard input. We use a relative path to force it to read the file.

### Command

```bash
cat ./-
```

### How to Read the Command Logic

* `cat` → Opens and displays file content.
* `./-` → The `./` tells Linux to look inside the current directory for a file literally named `-`, bypassing the keyboard input trap.

---

## 📂 Level 2 ➔ Level 3: Dealing with Spaces & Dashes

### Concept

Filenames containing both spaces and dashes (e.g., `--spaces in this filename--`) can trick Linux into reading them as command options or flags. Wrapping the name in quotes locks it as a single file entity.

### Command

```bash
cat "--spaces in this filename--"
```

### How to Read the Command Logic

* `cat` → Tries to open the target file.
* `""` (Double Quotes) → Groups the entire string together so Linux reads it as one solid file name instead of separate command parameters.

---

## 📂 Level 3 ➔ Level 4: Navigating Directories & Hidden Files

### Concept

Directories cannot be opened with `cat`; you must use `cd` to navigate. To see files intentionally hidden by the system (filenames starting with a dot `.`), use the "all" flag.

### Commands

```bash
cd inhere/
ls -a
```

### How to Read the Command Logic

* `cd inhere/` → Changes the directory to move the terminal focus inside the `inhere/` folder.
* `ls` → Lists visible files.
* `-a` (All Flag) → Forces the system to reveal hidden objects starting with a dot (`.`).

---

## 📂 Level 4 ➔ Level 5: Filtering Human-Readable Text

### Concept

When a directory is cluttered with corrupted binary files, we filter for human-readable ASCII text to identify the correct target without messing up the terminal.

### Commands

```bash
file ./*
cat -- ./-file07
```

### How to Read the Command Logic

* `file ./*` → Scans the properties of every file in the current directory to determine its type (look for ASCII text).
* `cat` → Opens the target file.
* `--` → A universal divider that tells Linux to stop reading dashes as command options.
* `./-file07` → The specific path to the identified ASCII file.

---

## 📂 Level 5 ➔ Level 6: Advanced Multi-Property Search

### Concept

Searching deep inside a labyrinth of multiple sub-folders for a non-executable file that matches an exact byte size.

### Command

```bash
find . -type f -size 1033c ! -executable
```

### How to Read the Command Logic

* `find .` → Initiates a search starting from the current directory.
* `-type f` → Restricts results to standard files only (excluding folders).
* `-size 1033c` → Filters for a file with an exact size of 1033 bytes (`c` stands for bytes).
* `! -executable` → The exclamation mark means **NOT**, filtering out runnable files or scripts.

---

## 📂 Level 6 ➔ Level 7: System-Wide Scanning & Noise Suppression

### Concept

Scanning the entire server root (`/`) based on user and group ownership. We attach error redirection (`2>/dev/null`) to suppress and hide thousands of annoying *Permission denied* messages.

### Command

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

### How to Read the Command Logic

* `find /` → Starts a comprehensive search from the highest system level (root directory).
* `-user bandit7` → Filters for files owned by the user `bandit7`.
* `-group bandit6` → Filters for files belonging to the group `bandit6`.
* `-size 33c` → Matches files that are exactly 33 bytes.
* `2>/dev/null` → Redirects standard error messages (like *Permission denied*) straight into the system trash bin so they don't clutter the screen.

---

## 📂 Level 7 ➔ Level 8: Targeted Keyword Filtering (grep)

### Concept

Isolating a single line of text out of thousands of chaotic lines using a precise keyword provided by the mission statement.

### Command

```bash
grep "millionth" data.txt
```

### How to Read the Command Logic

* `grep` → Searches for text matching a regular expression pattern.
* `"millionth"` → The precise keyword target we want to catch.
* `data.txt` → The source text file to scan.

---

## 📂 Level 8 ➔ Level 9: Isolating Unique Lines (Piping |)

### Concept

Finding the only line of text that occurs exactly once. We chain commands together using a pipe (`|`): first we sort the text alphabetically so duplicates sit together, then filter for the absolute unique line.

### Command

```bash
sort data.txt | uniq -u
```

### How to Read the Command Logic

* `sort data.txt` → Reorganizes all text lines in alphabetical order.
* `|` (Pipe) → Streams the output of the `sort` command directly into the next operation.
* `uniq -u` → Analyzes the sorted stream and strips away any data line that has a duplicate copy, leaving only the single unique line.

---

## 📂 Level 9 ➔ Level 10: strings

---

## 📂 Level 10 ➔ Level 11: base64 decode

---

## 📂 Level 11 ➔ Level 12: tr

---
