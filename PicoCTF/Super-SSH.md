# 🚩 picoCTF Challenge: Super SSH
**Status:** Completed ✅
**Date:** April 15, 2026
**Category:** General Skills

## 📝 Challenge Description
The objective of this challenge is to demonstrate the ability to securely connect to a remote server using the **SSH (Secure Shell)** protocol. This task requires handling specific credentials, such as a host address, port number, and password, to gain access to a remote terminal environment.

## 🔍 Methodology & Logic
To successfully **retrieve** the flag, I followed a standard remote access procedure via my **WSL** terminal:

1.  **Credential Acquisition:** I identified the necessary connection details provided in the challenge description, including the username, host server, and the designated port.
2.  **SSH Execution:** I utilized the `ssh` command followed by the `-p` flag to specify the non-standard port. This is an **essential** skill for managing remote Linux servers.
    ```bash
    ssh ctf-player@titan.picoctf.net -p 56358
    ```
3.  **Authentication:** After initiating the connection, I entered the provided password to authenticate my session.
4.  **Flag Retrieval:** Once the remote shell was established, the flag was immediately displayed in the terminal.
    - **Final Flag:** `picoCTF{s5h_4ll_7h3_w4y_3687353b}`

## 💡 Key Insight
This challenge reinforces the importance of **secure communication** between local and remote systems. Being **proficient** in SSH is a prerequisite for more advanced tasks like **Penetration Testing** on live machines. It also teaches the importance of correctly managing port arguments when standard ports are not in use.
