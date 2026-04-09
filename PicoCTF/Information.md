# 🚩 picoCTF Challenge: Information
**Status:** Completed ✅
**Date:** April 9, 2026
**Category:** Forensics

## 📝 Challenge Description
The goal of this challenge is to examine a seemingly ordinary image file to find a hidden flag. This task requires an understanding of **Metadata**—information stored within a file that describes its characteristics but is not visible to the naked eye.

## 🔍 Methodology & Logic
To successfully extract the hidden data, I implemented the following forensic steps using my **WSL** environment:

1.  **Asset Acquisition:** I downloaded the provided image file using the terminal to maintain a consistent workflow.
2.  **Metadata Analysis:** I utilized a tool called `exiftool` to inspect the file's metadata. This allowed me to scrutinize various fields such as the author, license, and creation date.
    ```bash
    exiftool cat.jpg
    ```
3.  **Pattern Recognition:** While reviewing the output, I identified a suspicious string in the `License` field that appeared to be **Base64 encoded**.
4.  **Data Decoding:** I leveraged the `base64` command in the terminal to decode the suspicious string, which ultimately **revealed** the hidden flag.
    ```bash
    echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 -d
    ```
    - **Final Flag:** `picoCTF{the_m3tadata_1s_modified}`

## 💡 Key Insight
This challenge emphasizes that digital files often contain a trove of hidden information beyond their visual content. Developing the habit of checking metadata is an essential part of a forensic investigator's mindset. It also reinforces the importance of being proficient in decoding various data formats like Base64.
