# 2026‑4‑14 — Lab 16: OpenSSL Key Pair, Encryption, Signing

## ⭐ 1. Overview  
In this lab, I practiced the core concepts of asymmetric cryptography using OpenSSL. My goal was to understand how RSA key pairs work in real systems and how they provide confidentiality, integrity, authenticity, and non‑repudiation.

I generated my own RSA private and public keys, encrypted a message using the public key, and decrypted it using the private key. This helped me see how public‑key encryption ensures that only the private‑key holder can read protected data.

I also created a SHA‑256 digital signature for a file and verified it using the public key. This demonstrated how signatures prove authorship and ensure that a file hasn’t been modified. Working through these steps gave me hands‑on experience with the same cryptographic mechanisms used in SSH authentication, TLS certificates, secure email, and software package signing.

Overall, this lab strengthened my understanding of key management and cryptographic workflows that I will use regularly as a sysadmin and IT support technician.

---

## 🎯 2. Objectives  
- Generate a 2048‑bit RSA private key  
- Generate the corresponding public key  
- Encrypt and decrypt a message using RSA  
- Create a digital signature and verify it  
- Demonstrate confidentiality, integrity, authenticity, and non‑repudiation  

---

## 🛠️ 3. Tools & Commands Used  

### Key Generation  
- `openssl genrsa -out private_key.pem 2048`  
- `openssl rsa -in private_key.pem -outform PEM -pubout -out public_key.pem`

### Encryption & Decryption  
- `echo 'This is a secret message...' > secret.txt`  
- `openssl rsautl -encrypt -pubin -inkey public_key.pem -in secret.txt -out secret.enc`  
- `openssl rsautl -decrypt -inkey private_key.pem -in secret.enc`

### Signing & Verification  
- `openssl dgst -sha256 -sign private_key.pem -out secret.txt.sha256 secret.txt`  
- `openssl dgst -sha256 -verify public_key.pem -signature secret.txt.sha256 secret.txt`

---

## 🧩 4. Steps Completed  

### 4.1 I Generated a Private Key  
I created a 2048‑bit RSA private key and inspected it to confirm the modulus and key structure.

### 4.2 I Generated a Public Key  
I extracted the public key from my private key and verified that it matched correctly.

### 4.3 I Encrypted and Decrypted a Message  
- I created a plaintext file (`secret.txt`)  
- I encrypted it using my **public key**  
- I decrypted it using my **private key**  
- I confirmed that the decrypted output matched the original message  

This showed me how RSA provides **confidentiality**.

### 4.4 I Signed and Verified a File  
- I generated a SHA‑256 signature for `secret.txt`  
- I verified the signature using my public key  
- OpenSSL returned `Verified OK`, confirming the file was unchanged  

This demonstrated **integrity**, **authenticity**, and **non‑repudiation**.

---

## 🐞 5. Problems & Fixes  
I didn’t encounter any issues during this lab.  
All commands executed successfully on the first attempt.

---

## 📚 6. What I Learned  
- RSA key pairs are the foundation of secure communication  
- Public keys encrypt; private keys decrypt  
- Private keys sign; public keys verify  
- Digital signatures ensure that files haven’t been modified  
- Hashing + signing is used in software distribution, TLS certificates, and SSH trust models  
- OpenSSL gives me low‑level visibility into cryptographic operations that are normally hidden behind higher‑level tools  

---

## 📎 7. Related Files  
- `private_key.pem`  
- `public_key.pem`  
- `secret.txt`  
- `secret.enc`  
- `secret.txt.sha256`  

*(I will add screenshots when uploading to GitHub.)*

---

## 🔜 8. Next Steps  
- Move on to **Lab 17: Hashing with md5sum & shasum**  
- Compare hashing vs signing  
- Document Lab 17using the same 8‑section structure  
- Add both labs to my Daily Practice repo  
