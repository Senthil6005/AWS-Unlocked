# 10 – Python & Boto3 for AWS

**Category:** 🧑‍💻 Automation

## 📘 What is it?
Python is the most popular language for cloud automation; **boto3** is the AWS SDK for Python.

## 💡 Why it matters
Automate repetitive AWS tasks: stop idle instances, clean old snapshots, generate reports.

## 🔑 Concepts
- Python basics: variables, lists, dicts, loops, functions
- Virtual environments & pip
- boto3 **client** (low-level) vs **resource** (high-level)
- Credentials from IAM role or `aws configure` – never hardcode
- Pagination & error handling (`botocore.exceptions`)
- Used inside Lambda functions

## 💻 Commands / Example
```python
import boto3

ec2 = boto3.client('ec2', region_name='ap-south-1')
for r in ec2.describe_instances()['Reservations']:
    for i in r['Instances']:
        print(i['InstanceId'], i['State']['Name'])

s3 = boto3.client('s3')
for b in s3.list_buckets()['Buckets']:
    print(b['Name'])
```

## ❓ Interview Questions
1. boto3 client vs resource?
2. How should a Python script get AWS credentials?
3. How do you handle pagination in boto3?

## 📝 Practice
- Write a boto3 script that stops all running EC2 instances with tag `Env=dev`.
- ⚠️ Delete or stop resources after the lab to avoid charges.
