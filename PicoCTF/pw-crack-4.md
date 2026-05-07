# 🚩 picoCTF Challenge: PW Crack 4
**Status:** Completed ✅   
**Date:** May 7, 2026   
**Category:** General Skills (Scripting/Python)

## 📝 Challenge Description
The objective of this challenge is to decrypt a password-protected flag file (`level4.flag.txt.enc`). The challenge provides a Python script (`level4.py`) that checks a user-provided password against a hashed value. However, the password is hidden within a list of 100 possible options.

## 🔍 Methodology & Logic
I adopted a more **proactive** approach by modifying the source code to automate the password-checking process. This technique is often referred to as **scripting** for automated exploitation.

1.  **Code Analysis:** I analyzed the `level4.py` file and identified the `pos_pw_list` variable, which contains 100 potential passwords, and the `level_4_pw_check()` function.
2.  **Script Modification:** Instead of manually entering passwords, I **implemented** a `for` loop to iterate through the `pos_pw_list`. I modified the script to automatically pass each candidate to the hash-checking function.
3.  **Advanced Debugging:** For the first time, I utilized the **Python Debugger** in VS Code. This allowed me to set breakpoints and **monitor** the variable states in real-time, which significantly improved my understanding of the script's execution flow.
4.  **Flag Retrieval:** The automated script successfully identified the correct password and decrypted the flag.
    - **Final Flag:** `picoCTF{fl45h_5pr1ng1ng_d770d48c}`

## 💡 Key Insight
This challenge is a **fundamental** lesson in how scripting can bypass manual security barriers. Learning to use a debugger was a **game-changer** for me, as it transformed a "black box" into a transparent process. It proves that being **proficient** in a programming language like Python is a mandatory **prerequisite** for any security professional.
