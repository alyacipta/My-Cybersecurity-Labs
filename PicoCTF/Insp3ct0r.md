# 🚩 picoCTF Challenge: Insp3ct0r
**Status:** Completed ✅
**Date:** April 14, 2026
**Category:** Web Exploitation

## 📝 Challenge Description
The objective of this challenge is to discover a flag that has been split into three parts and hidden within the source code of a website. This task tests the ability to **scrutinize** various web technologies, including HTML, CSS, and JavaScript.

## 🔍 Methodology & Logic
To successfully **retrieve** the full flag, I performed a manual inspection of the web application's front-end components using the browser's Developer Tools:

1.  **HTML Inspection:** I started by viewing the page source (Ctrl+U). I found the first part of the flag hidden in a comment at the end of the HTML structure.
2.  **CSS Analysis:** I then **navigated** to the linked stylesheet (`mycss.css`). Upon reviewing the code, I identified the second segment of the flag, also stored within a comment.
3.  **JavaScript Investigation:** Finally, I examined the external JavaScript file (`myjs.js`). The third and final portion of the flag was **uncovered** there.
4.  **Flag Reassembly:** I combined all three fragments to form the complete string.
    - **Final Flag:** `picoCTF{tru3_d3t3ct1v3_0ut_f0r_puzzl3s_1495021}`

## 💡 Key Insight
This challenge emphasizes that security is not always about complex exploits; sometimes, **essential** information is leaked through simple human error or poor documentation habits. Being **proficient** in using browser inspection tools is a fundamental skill for any security researcher to **prioritize** during the initial reconnaissance phase.
