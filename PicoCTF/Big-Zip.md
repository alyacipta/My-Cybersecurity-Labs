# 🚩 picoCTF Challenge: Big Zip
**Status:** Completed ✅
**Date:** April 9, 2026
**Category:** General Skills

## 📝 Challenge Description
The objective of this challenge is to locate a specific flag hidden somewhere within a massive ZIP archive containing thousands of files and folders. This task is designed to test an investigator's ability to search through large datasets **efficiently**.

## 🔍 Methodology & Logic
Manually searching through thousands of files is **inefficient**. Therefore, I **leveraged** powerful Linux commands within my **WSL** environment to **automate** the discovery process:

1.  **Extraction:** I first unzipped the large archive using the terminal, which revealed a vast and complex directory structure.
    ```bash
    unzip big-zip-files.zip
    ```

2.  **Recursive Search:** Instead of opening every folder, I utilized the `grep` command with the recursive flag (`-r`). This allowed me to **scrutinize** the contents of every single file in the directory simultaneously.
    ```bash
    grep -r "picoCTF" .
    ```

3.  **Result Analysis:** The command instantly **pinpointed** the exact file and line where the flag was stored, bypassing hours of manual searching.
    - **Final Flag:** `picoCTF{gREp_1S_mAG1c_efbfda11}`

## 💡 Key Insight
This challenge reinforces the idea that in cybersecurity, "Grepping" is a **fundamental** skill. Being **proficient** with recursive search tools allows a forensic analyst to **streamline** their workflow and find critical evidence within a **trove**  of data in seconds.
