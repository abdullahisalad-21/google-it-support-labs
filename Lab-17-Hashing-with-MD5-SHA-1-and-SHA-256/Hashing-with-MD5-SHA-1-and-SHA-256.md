# 2026‑4‑14 — Lab 17: Hashing with MD5, SHA‑1, and SHA‑256

## ⭐ 1. Overview  
In this lab, I practiced generating and verifying file hashes using `md5sum` and `shasum`. Hashing is a fundamental security concept used to ensure file integrity. Unlike encryption, hashing is a one‑way process: once a hash is created, it cannot be reversed to recover the original data.

My goal in this lab was to understand how hashing detects tampering, how different hashing algorithms behave, and why stronger algorithms like SHA‑256 are preferred over older ones like MD5 and SHA‑1. By creating a text file, hashing it, modifying it, and observing how verification fails, I gained hands‑on experience with integrity checking — a critical skill for verifying downloads, detecting corruption, and validating system files.

This lab also helped me compare the strength of different hashing algorithms. MD5 produces a short 128‑bit digest and is considered weak today. SHA‑1 is stronger but still vulnerable to collisions. SHA‑256 produces a much longer digest and is widely used in modern security systems, including TLS certificates, package managers, and digital signatures.

Overall, this lab strengthened my understanding of how hashing supports secure workflows and why integrity verification is essential in IT and cybersecurity.

---

## 🎯 2. Objectives  
- Create a text file to use for hashing  
- Generate an MD5 hash and store it  
- Demonstrate MD5 verification failure after modifying the file  
- Recompute a new MD5 hash for the modified file  
- Generate and verify a SHA‑1 hash  
- Generate and verify a SHA‑256 hash  

---

## 🛠️ 3. Tools & Commands Used  

### MD5 Hashing  
- `md5sum file.txt > file.txt.md5`  
- `md5sum -c file.txt.md5`  

### File Modification  
- `cp file.txt badfile.txt`  
- `nano badfile.txt`  

### SHA‑1 Hashing  
- `shasum file.txt > file.txt.sha1`  
- `shasum -c file.txt.sha1`  

### SHA‑256 Hashing  
- `shasum -a 256 file.txt > file.txt.sha256`  
- `shasum -a 256 -c file.txt.sha256`  

---

## 🧩 4. Steps Completed  

### 4.1 I Created a Text File  
I created a simple text file containing sample data to use for hashing. This file served as the baseline for all hash computations.

### 4.2 I Generated the MD5 Hash  
I used `md5sum` to compute the MD5 digest and saved it to `file.txt.md5`. I verified the hash successfully, confirming that the file had not been altered.

### 4.3 I Demonstrated MD5 Verification Failure  
I copied the file to `badfile.txt`, generated a matching MD5 hash, and then edited the file by adding a single space. When I verified the hash again, it failed. This showed me how even a tiny change completely alters the hash.

### 4.4 I Recomputed the MD5 Hash  
After modifying the file, I generated a new MD5 hash and verified it successfully. This confirmed that the new hash matched the modified content.

### 4.5 I Generated and Verified a SHA‑1 Hash  
I used `shasum` to compute a SHA‑1 digest. The verification succeeded, showing that the file had not changed since the hash was created.

### 4.6 I Generated and Verified a SHA‑256 Hash  
I computed a SHA‑256 digest using `shasum -a 256`. The resulting hash was much longer, demonstrating its stronger security. Verification succeeded as expected.

---

## 🐞 5. Problems & Fixes  
I didn’t encounter any issues during this lab. All hashing and verification commands worked as expected, and the behavior matched the lab instructions.

---

## 📚 6. What I Learned  
- Hashing is a one‑way process used for integrity checking  
- Even a single character change produces a completely different hash  
- MD5 is weak and prone to collisions  
- SHA‑1 is stronger but still outdated  
- SHA‑256 is the current standard for secure hashing  
- Hash verification is essential for detecting tampering, corruption, or unauthorized changes  
- Tools like `md5sum` and `shasum` are simple but powerful for validating file integrity  

---

## 📎 7. Related Files  
- `file.txt`  
- `file.txt.md5`  
- `badfile.txt`  
- `badfile.txt.md5`  
- `new.badfile.txt.md5`  
- `file.txt.sha1`  
- `file.txt.sha256`  

*(I will add screenshots when uploading to GitHub.)*

---

## 🔜 8. Next Steps  
- Move on to the next lab in the course  
- Compare hashing with encryption and signing  
- Practice verifying downloaded software using SHA‑256 checksums  
- Add this documentation to my Daily Practice repo  
