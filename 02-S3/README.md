# 02 – S3 – Simple Storage Service

**Category:** 📦 Storage

## 📘 What is it?
Object storage with virtually unlimited capacity; data is stored as objects inside buckets.

## 💡 Why it matters
Used for backups, static websites, logs, data lakes and artifacts – one of the most used AWS services.

## 🔑 Concepts
- Bucket (globally unique name) and Object (key + data + metadata)
- Max object size 5 TB; use multipart upload for large files
- Designed for 11 nines (99.999999999%) durability
- Versioning – keep previous versions, protect from deletes
- Lifecycle rules – move/expire objects automatically
- Static website hosting
- Block Public Access (ON by default)
- Bucket policies vs ACLs
- Encryption: SSE-S3, SSE-KMS, client-side
- Presigned URLs – temporary access
- Replication: CRR (cross-region), SRR (same-region)

## 🔑 Storage Classes
- S3 Standard – frequent access
- S3 Intelligent-Tiering – auto moves between tiers
- S3 Standard-IA / One Zone-IA – infrequent access
- S3 Glacier Instant / Flexible / Deep Archive – archive at low cost

## 💻 Commands / Example
```bash
aws s3 mb s3://my-unique-bucket-123
aws s3 cp file.txt s3://my-unique-bucket-123/
aws s3 ls s3://my-unique-bucket-123/
aws s3 sync ./site s3://my-unique-bucket-123/
aws s3 presign s3://my-unique-bucket-123/file.txt --expires-in 300
aws s3 rb s3://my-unique-bucket-123 --force
```

## ❓ Interview Questions
1. Object vs block vs file storage?
2. What are S3 storage classes?
3. How do you secure an S3 bucket?
4. What is versioning? What is a presigned URL?
5. Why must bucket names be globally unique?

## 📝 Practice
- Host a static website on S3, enable versioning and add a lifecycle rule to move objects to Glacier after 30 days.
- ⚠️ Delete or stop resources after the lab to avoid charges.
