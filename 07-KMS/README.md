# 07 – KMS – Key Management Service

**Category:** 🔐 Security

## 📘 What is it?
Managed service to create and control encryption keys used to protect data.

## 💡 Why it matters
Encryption at rest for S3, EBS, RDS, EFS and more is powered by KMS – a core compliance requirement.

## 🔑 Concepts
- AWS managed keys vs Customer managed keys (CMK)
- Symmetric vs asymmetric keys
- Key policies + IAM control access
- Envelope encryption (data key encrypts data, KMS key encrypts data key)
- Automatic key rotation
- Key deletion has a waiting period (7–30 days)
- Every key use is logged in CloudTrail

## 💻 Commands / Example
```bash
aws kms create-key --description "app key"
aws kms create-alias --alias-name alias/app-key --target-key-id <key-id>
aws kms encrypt --key-id alias/app-key --plaintext fileb://secret.txt --output text --query CiphertextBlob
aws kms list-keys
```

## ❓ Interview Questions
1. What is envelope encryption?
2. AWS managed vs customer managed key?
3. Encryption at rest vs in transit?
4. Can you export a KMS key?

## 📝 Practice
- Create a customer managed key and use it to encrypt an S3 bucket and an EBS volume.
- ⚠️ Delete or stop resources after the lab to avoid charges.
