# 🚩 picoCTF Challenge: Mod 26
**Status:** Completed ✅
**Date:** April 14, 2026
**Category:** Cryptography

## 📝 Challenge Description
The objective of this challenge is to decrypt a ciphered string using the **ROT13** (Rotate 13) algorithm. This is a classic substitution cipher where each letter is replaced by the 13th letter after it in the alphabet.

## 🔍 Methodology & Logic
To successfully **decipher** the flag, I explored the logic of rotational shifts and implemented a programmatic solution:

1.  **Cipher Identification:** I identified that the provided string `cvpbpgs{pelcgbtencul_vf_sha_o0on6033}` followed the standard flag format, but with shifted characters.
2.  **Algorithm Analysis:** Since ROT13 is its own inverse, shifting the characters by 13 positions again will **revert** them to their original state.
3.  **Execution (WSL/Python):** Instead of manual calculation, I **leveraged** [memanfaatkan] a Python one-liner in my **WSL** terminal to **automate** the decryption process:
    ```bash
    python3 -c "import codecs; print(codecs.encode('cvpbpgs{pelcgbtencul_vf_sha_o0on6033}', 'rot_13'))"
    ```
4.  **Verification:** The script successfully **revealed** the plain text flag.
    - **Final Flag:** `picoCTF{cryptography_is_fun_b0ba6033}`

## 💡 Key Insight
This challenge emphasizes the importance of understanding basic encryption schemes. It demonstrates that not all "scrambled" data is secure; without a complex key or multiple rounds of encryption, data remains **vulnerable** to simple rotational analysis. Being **proficient** in using Python for quick decoding is an **essential** skill for any security researcher.
