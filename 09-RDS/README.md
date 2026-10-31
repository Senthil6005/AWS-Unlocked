# 09 – RDS – Relational Database Service

**Category:** 🗄️ Database

## 📘 What is it?
Managed relational database service – AWS handles provisioning, patching, backups and failover.

## 💡 Why it matters
Most applications need a database; RDS removes the operational burden of running one on EC2.

## 🔑 Concepts
- Engines: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Aurora
- **Multi-AZ** – synchronous standby for high availability (failover)
- **Read Replicas** – asynchronous copies for read scaling
- Automated backups (point-in-time restore) & manual snapshots
- Encryption with KMS
- DB subnet group (keep RDS in private subnets)
- Parameter groups
- Aurora – AWS cloud-native, MySQL/PostgreSQL compatible

## 💻 Commands / Example
```bash
aws rds describe-db-instances
aws rds create-db-snapshot --db-instance-identifier mydb --db-snapshot-identifier mydb-snap1
mysql -h <rds-endpoint> -u admin -p
```

## ❓ Interview Questions
1. Multi-AZ vs Read Replica?
2. RDS vs database on EC2?
3. How do you secure RDS?
4. What is Aurora?

## 📝 Practice
- Launch MySQL RDS in a private subnet, connect from an EC2 in the same VPC, and take a snapshot.
- ⚠️ Delete or stop resources after the lab to avoid charges.
