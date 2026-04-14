# 🚩 picoCTF Challenge: Scavenger Hunt
**Status:** Completed ✅
**Date:** April 14, 2026
**Category:** Web Exploitation

## 📝 Challenge Description
The objective of this challenge is to recover a flag that has been fragmented and hidden across various web server files. This task requires a thorough investigation of how web applications and servers store sensitive information.

## 🔍 Methodology & Logic
To successfully **retrieve** all parts of the flag, I performed a systematic digital "scavenger hunt" by inspecting different layers of the web application:

1.  **Source Code Inspection:** I started by analyzing the HTML, CSS, and JavaScript files via the browser's **Developer Tools**. I found the first two parts of the flag hidden in the comments of the HTML and CSS files.
2.  **Server Configuration Analysis:** Since the JavaScript hint suggested that the developer used a specialized server configuration, I **scrutinized** the `.htaccess` file, which revealed the third part of the flag.
3.  **Deployment Artifacts:** Following the clues, I checked for files related to macOS deployment. By accessing the `.DS_Store` file path, I successfully **uncovered** the final portion of the hidden data.
4.  **Flag Reassembly:** I combined all retrieved segments to form the complete flag.
    - **Final Flag:** `picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lOOk_35833e52}`

## 💡 Key Insight
This challenge highlights that security is not just about the visible code. **Essential** information can be leaked through server-side configuration files and hidden OS metadata. Being **proficient** in identifying these "information leaks" is a critical skill for any security professional to **prioritize** during a vulnerability assessment.
