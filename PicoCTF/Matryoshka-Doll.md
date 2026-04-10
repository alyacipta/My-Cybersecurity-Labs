# 🚩 picoCTF Challenge: Matryoshka Doll
**Status:** Completed ✅
**Date:** April 10, 2026
**Category:** Forensics

## 📝 Challenge Description
The objective of this challenge is to uncover a hidden flag concealed within a series of nested image files. Named after the Russian Matryoshka dolls, this task requires an investigator to **scrutinize** a file that appears to be a single image but actually contains multiple layers of hidden data.

## 🔍 Methodology & Logic
To solve this puzzle, I **leveraged** forensic tools within my **WSL** environment to perform **recursive extraction**:

1.  **Initial Analysis:** I started by inspecting the base image file. While it looked like a standard `.jpg`, I suspected there was more than meets the eye.
2.  **Embedded File Discovery:** I utilized the `binwalk` command to **identify** if any other files were embedded inside the image.
    ```bash
    binwalk doll.jpg
    ```
3.  **Recursive Extraction:** Upon finding a hidden ZIP file, I used the extraction flag to pull out the hidden content. I had to repeat this process several times as each extracted file contained yet another hidden layer.
    ```bash
    binwalk -e doll.jpg
    # Repeated for base_images/2_7.jpg, 3_8.jpg, etc.
    ```
4.  **Flag Retrieval:** After navigating through four layers of nested folders and images, I finally reached the **deepest** directory which contained a `flag.txt` file.
    - **Final Flag:** `picoCTF{4312b464ad127b679fe48c90b61d3680}`

## 💡 Key Insight
This challenge is an excellent demonstration of **Steganography** and file nesting techniques. It teaches a forensic analyst to never take a file at face value. Being **proficient** with tools like `binwalk` is **essential** for **streamlining** the process of uncovering data that has been intentionally hidden inside legitimate file types.
