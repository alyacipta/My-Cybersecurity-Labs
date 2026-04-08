# 🚩 picoCTF Challenge: Python Wrangling
**Status:** Completed ✅
**Date:** April 8, 2026
**Category:** General Skills

## 📝 Challenge Description
The objective of this challenge is to execute a Python script called `ende.py` to decrypt a file named `flag.txt.en`. The challenge requires the user to utilize a provided `password.txt` to successfully retrieve the flag through the terminal.

## 🔍 Methodology & Logic
To solve this task, I focused on mastering **Command Line Interface (CLI)** interactions within my **WSL** environment:

1.  **Environment Preparation:** I used the `wget` command to download all necessary assets directly into my working directory.
    - `ende.py` (The decryption script)
    - `flag.txt.en` (The encrypted flag)
    - `password.txt` (The file containing the decryption key)

2.  **Credential Retrieval:** I utilized the `cat` command to read the contents of `password.txt` and copied the credentials to my clipboard.
    ```bash
    cat password.txt
    ```

3.  **Script Execution:** I deployed the Python script using the specific flag `-d` for decryption. This process required a consistent understanding of how terminal arguments work.
    ```bash
    python3 ende.py -d flag.txt.en
    ```

4.  **Authentication:** When prompted, I entered the password obtained in step 2. The script then successfully deciphered the file and displayed the flag.
    - **Final Flag:** `picoCTF{4p0110_1n_7h3_h0us3_67716f6e}`

## 💡 Key Insight
This challenge is a great exercise in **script interaction** and parameter handling. It demonstrates that in cybersecurity, many sophisticated tools do not have a GUI (Graphical User Interface); therefore, being proficient in the terminal is an essentialskill for any engineer.
