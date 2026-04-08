# 🚩 picoCTF Challenge: 2Warm
**Status:** Completed ✅
**Date:** April 8, 2026
**Category:** General Skills

## 📝 Challenge Description
The objective of this challenge is to convert the decimal number `42` (base 10) into its binary representation (base 2).

## 🔍 Methodology & Logic
To successfully retrieve the flag, I followed a systematic approach to understand how computers process numerical data:

1.  **Manual Conversion:** I performed a manual calculation by repeatedly dividing 42 by 2 and recording the remainder.
    - 42 / 2 = 21 (Rem: 0)
    - 21 / 2 = 10 (Rem: 1)
    - 10 / 2 = 5  (Rem: 0)
    - 5 / 2  = 2  (Rem: 1)
    - 2 / 2  = 1  (Rem: 0)
    - 1 / 2  = 0  (Rem: 1)
    - Reading from bottom to top, the result is `101010`.

2.  **Terminal Execution (WSL):** To ensure my result was consistent, I utilized a Python one-liner in my **WSL** terminal to automate the conversion:
    ```bash
    python3 -c "print(bin(42))"
    ```
    *Output:* `0b101010`

3.  **Flag Identification:** After verifying the binary value, I encapsulated the result into the standard picoCTF format.
    - **Final Flag:** `picoCTF{101010}`

## 💡 Key Insight
This task highlights the essential prerequisite of understanding base conversions in Computer Engineering. It demonstrates how high-level decimal data is translated into low-level binary formats that hardware can execute.
