# 03 – IAM – Identity and Access Management

**Category:** 🔐 Security

## 📘 What is it?
Global service to control **who** can access **what** in your AWS account.

## 💡 Why it matters
Every AWS action is checked by IAM. Wrong permissions are the #1 cause of cloud security incidents.

## 🔑 Concepts
- Users – people/apps with long-term credentials
- Groups – collection of users (attach policies to groups)
- Roles – temporary credentials assumed by services/users (preferred)
- Policies – JSON documents with Effect, Action, Resource, Condition
- AWS managed vs customer managed vs inline policies
- Least privilege principle
- MFA, password policy, access key rotation
- Explicit **Deny** always wins
- IAM is **global** (not region-specific)

## 💻 Commands / Example
```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": ["s3:GetObject"],
    "Resource": "arn:aws:s3:::my-bucket/*"
  }]
}

aws iam create-user --user-name devuser
aws iam list-users
aws iam attach-user-policy --user-name devuser --policy-arn arn:aws:iam::aws:policy/ReadOnlyAccess
```

## ❓ Interview Questions
1. IAM user vs IAM role?
2. What is an IAM policy? Explain its structure.
3. What is least privilege?
4. How does an EC2 instance access S3 securely?
5. What happens when Allow and Deny conflict?

## 📝 Practice
- Create a group `developers` with read-only access, add a user with MFA, and attach an IAM role to EC2 to read S3 without access keys.
- ⚠️ Delete or stop resources after the lab to avoid charges.
