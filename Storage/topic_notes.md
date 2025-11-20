# 📦 STORAGE MODULE — TOPIC NOTES

## 1. 🌐 Amazon S3 Overview
Amazon Simple Storage Service (S3) is used to store files (called *objects*) inside *buckets*.  
It provides durability, scalability, and affordable storage.

### Key Terms
- **Bucket:** Container for storing objects  
- **Object:** The actual file stored in S3  
- **Region:** Buckets are created in one AWS region  
- **Key:** Unique path/name of an object  

### Core Features
- High durability (99.999999999%)  
- Versioning to keep older file versions  
- Encryption options (SSE-S3, SSE-KMS)  
- Access control using Bucket Policies & ACLs  

---

## 2. 🗂️ S3 Storage Classes
Different tiers based on how often the data is accessed:

- **S3 Standard** — for everyday use  
- **S3 Standard-IA** — cheaper, infrequent access  
- **S3 One Zone-IA** — stored in one AZ, lower cost  

---

## 3. 🌍 S3 Static Website Hosting
S3 can host simple websites using:

- `index.html` — homepage  
- Bucket Policy — allows public read  
- Static Website Hosting feature — serves files over the web  

Used in our group project.

---

## 4. 🔐 Security Basics
- Buckets are private by default  
- Public access only when needed  
- Bucket Policies control who can read files  

