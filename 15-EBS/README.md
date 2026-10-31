# 15 – EBS – Elastic Block Store

**Category:** 📦 Storage

## 📘 What is it?
Block storage volumes attached to EC2 instances – like a virtual hard disk.

## 💡 Why it matters
Every EC2 root disk is EBS; understanding volume types, snapshots and encryption is essential.

## 🔑 Concepts
- Volume is tied to **one AZ**
- Types: gp3/gp2 (general SSD), io2/io1 (provisioned IOPS), st1 (throughput HDD), sc1 (cold HDD)
- Snapshots – incremental backups stored in S3 (managed by AWS)
- Copy snapshots across regions for DR
- Encryption with KMS
- Increase size/type without downtime (then grow the filesystem)
- Multi-Attach (io1/io2 only)
- Instance Store – temporary, data lost on stop

## 💻 Commands / Example
```bash
aws ec2 create-volume --size 10 --volume-type gp3 --availability-zone ap-south-1a
aws ec2 attach-volume --volume-id <vol-id> --instance-id <id> --device /dev/sdf
lsblk
sudo mkfs -t xfs /dev/nvme1n1
sudo mount /dev/nvme1n1 /data
aws ec2 create-snapshot --volume-id <vol-id> --description "backup"
```

## ❓ Interview Questions
1. EBS vs Instance Store?
2. gp3 vs io2?
3. How do you move an EBS volume to another AZ?
4. Are snapshots incremental?

## 📝 Practice
- Attach a new EBS volume, format and mount it permanently, take a snapshot and restore it in another AZ.
- ⚠️ Delete or stop resources after the lab to avoid charges.
