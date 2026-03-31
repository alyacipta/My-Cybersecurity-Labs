# TryHackMe: Crack the Hash
**Status:** Task 1 Completed ✅
**Date:** March 31, 2026
**Tutorial Followed:** [TryHackMe | Crack The Hash by Avocari (YouTube)](https://www.youtube.com/watch?v=4kJZxMd7NmM)

### 🛡️ What I Learned Today:
In this room, I explored the world of password hashing and cracking. I learned that not all hashes are the same and some require specific tools to identify and break.

### 🛠️ Tools Used:
1. **CrackStation (Online):** Used for quick lookups of common hash types (MD5, SHA1).
2. **HashID (Terminal):** Used this when CrackStation failed to identify a hash. It helped me identify a **Blowfish** hash.
3. **Hashcat (Terminal):** A powerful tool used to crack the identified hash using the specific mode ID provided by HashID.

### 🚀 Technical Workflow:
- When a hash was marked as "Unknown" in CrackStation, I switched to the TryHackMe AttackBox terminal.
- I used the command `hashid -m [hash]` to identify the algorithm.
- Once identified (e.g., Blowfish), I used the corresponding Mode ID with Hashcat: 
  `hashcat -m [Mode_ID] [hash]` 
- This successfully revealed the plain-text password hidden behind the scrambled characters.

---
*Next Goal: Complete Task 2 and explore more complex hash types.*
