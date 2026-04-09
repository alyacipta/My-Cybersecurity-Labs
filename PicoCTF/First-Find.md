# 🚩 picoCTF Challenge: First Find
**Status:** Completed ✅
**Date:** April 9, 2026
**Category:** General Skills / Forensics

## 📝 Challenge Description
The objective of this challenge is to locate a specific file named `metadata` hidden within a complex directory structure containing numerous subfolders. This task tests the ability to navigate and search through large datasets efficiently.

## 🔍 Methodology & Logic
Instead of manually inspecting each folder, I leveraged the power of the **WSL** terminal to automate the search process:

1.  **Extraction:** After downloading the challenge file, I extracted the compressed archive to reveal a deeply nested file structure.
2.  **Automated Search:** I utilized the `find` command, which is an **essential** tool for any security professional, to pinpoint the exact location of the target file:
    ```bash
    find . -name "metadata"
    ```
3.  **Content Retrieval:** Once the path was identified, I used the `cat` command to read the file's content and **extract** the flag.
    ```bash
    cat ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/metadata
    ```
    - **Final Flag:** `picoCTF{f1nd_17_dq382551}`

## 💡 Key Insight
This challenge demonstrates that manual inspection is often **inefficient** when dealing with large-scale systems. Mastering terminal commands like `find` allows an investigator to **streamline** their workflow and maintain a **consistent** pace during a forensic investigation.
