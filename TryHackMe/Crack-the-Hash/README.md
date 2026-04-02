# TryHackMe: Crack the Hash
**Status:** Room Completed ✅
**Completion Date:** April 2, 2026

## 📝 Final Progress Report (April 2, 2026)
Today’s session was a mix of technical breakthroughs and significant environment challenges. While I successfully finished the room, the process was far from perfect.

### 🚧 Technical Hurdles & Honesty:
- **Environment Failure:** My local workstation (WSL and BIOS virtualization) experienced recurring locks. This prevented me from running high-performance tools like **Hashcat** or **John the Ripper** effectively on my own machine.
- **Task 2 Approach:** Due to these persistent hardware/software limitations, I completed the second task by studying **professional walkthroughs and YouTube tutorials**. 
- **The Reality:** Instead of being completely stalled by a broken environment, I chose to learn the **logic and methodology** from external resources. While I didn't execute the final cracks for Task 2 myself, I studied the specific Mode IDs and signatures required.

### 💡 Key Takeaways:
1. **Adaptive Learning:** When tools fail, the priority shifts to understanding the "Why" behind the hash rather than just the "How" of the command.
2. **Persistence:** Despite the environment errors, I pushed through to see the logic of every hash in the room.
3. **Strategic Pivot:** Recognizing when a hardware environment is a bottleneck is a key skill. My next step is establishing a stable, high-performance local lab.

---
## 🛡️ Progress Report (April 1, 2026)
**Status:** Task 2 Continued (Challenges Encountered) 🚧

### 🚀 Breakthroughs & Lessons:
- **Identification:** Encountered a complex hash that CrackStation could not identify. Using the `$6$` signature and **Hashes.com**, I identified it as **SHA-512 (Unix)**.
- **Tool Logic:** Learned that SHA-512 (Unix) requires **Hashcat Mode 1800**.
- **Technical Hurdles:** Faced environment limitations in the THM AttackBox where Hashcat failed to recognize local drivers/wordlists even with `--force`.

### 🛠️ Pivot Strategy:
- Decided to transition to a local **WSL (Windows Subsystem for Linux)** environment. This will allow for more stable tool management and custom installations (like `hashid` and `hashcat`) without cloud machine restrictions.
- Learned that "Tool Troubleshooting" is 50% of the job in Penetration Testing.

---

## 🛡️ Progress Report (March 31, 2026)
**Status:** Task 1 Initial Progress ✅
**Tutorial Followed:** [TryHackMe | Crack The Hash by Avocari (YouTube)](https://www.youtube.com/watch?v=4kJZxMd7NmM)

### 📝 What I Learned:
In this room, I explored the world of password hashing and cracking. I learned that not all hashes are the same and some require specific tools to identify and break.

### 🛠️ Tools Used:
1. **CrackStation (Online):** Used for quick lookups of common hash types (MD5, SHA1).
2. **HashID (Terminal):** Used this when CrackStation failed to identify a hash. It helped me identify a **Blowfish** hash.
3. **Hashcat (Terminal):** A powerful tool used to crack the identified hash using the specific mode ID provided by HashID.

### 🚀 Technical Workflow:
- Used `hashid -m [hash]` to identify unknown algorithms.
- Executed `hashcat -m [Mode_ID] [hash]` to reveal plain-text passwords.

---
*Next Goal: Successfully set up WSL and finish the SHA-512 crack in Task 1.*
