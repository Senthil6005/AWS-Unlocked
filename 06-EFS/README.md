# 06 – EFS – Elastic File System

**Category:** 📦 Storage

## 📘 What is it?
Fully managed, elastic NFS file system that many EC2 instances can mount at the same time.

## 💡 Why it matters
Used when multiple servers need shared files (e.g., web servers behind a load balancer, CMS uploads).

## 🔑 Concepts
- NFS v4 protocol, Linux only
- Grows and shrinks automatically – pay per GB used
- Mount targets in each AZ
- Multi-AZ (Regional) and One Zone options
- Storage classes: Standard, Infrequent Access, Archive with lifecycle
- Performance & throughput modes
- Security group must allow port **2049**

## 💻 Commands / Example
```bash
sudo dnf install -y amazon-efs-utils
sudo mkdir /efs
sudo mount -t efs <file-system-id>:/ /efs
df -h | grep efs
```

## ❓ Interview Questions
1. EBS vs EFS vs S3?
2. Can EFS be used with Windows?
3. Which port does EFS use?

## 📝 Practice
- Create EFS, mount it on two EC2 instances in different AZs and verify a file created on one appears on the other.
- ⚠️ Delete or stop resources after the lab to avoid charges.
