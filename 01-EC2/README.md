# 01 – EC2 – Elastic Compute Cloud

**Category:** 💻 Compute

## 📘 What is it?
Virtual servers (instances) in the cloud that you can launch, resize and terminate anytime.

## 💡 Why it matters
EC2 is the foundation of AWS – web servers, Jenkins, databases and most labs run on EC2.

## 🔑 Concepts
- AMI (Amazon Machine Image) – OS template
- Instance types: t (burstable), m (general), c (compute), r (memory), g/p (GPU)
- Key pair – SSH login (private key `.pem` stays with you)
- Security Group – stateful virtual firewall at instance level
- User Data – script that runs at first boot
- Instance states: pending → running → stopping → stopped → terminated
- Elastic IP – static public IP
- Instance metadata: `http://169.254.169.254` (use IMDSv2)

## 🔑 Pricing Models
- **On-Demand** – pay per second, no commitment
- **Reserved Instances / Savings Plans** – 1 or 3 year commitment, big discount
- **Spot** – unused capacity, up to ~90% cheaper, can be interrupted
- **Dedicated Hosts** – physical server for licensing/compliance

## 💻 Commands / Example
```bash
aws ec2 describe-instances --output table
aws ec2 run-instances --image-id <ami-id> --instance-type t2.micro --key-name mykey --security-group-ids <sg-id>
aws ec2 stop-instances --instance-ids <id>
aws ec2 terminate-instances --instance-ids <id>
ssh -i mykey.pem ec2-user@<public-ip>
```

## ❓ Interview Questions
1. Stop vs terminate?
2. Security Group vs NACL?
3. What is User Data?
4. On-Demand vs Reserved vs Spot?
5. How do you recover access if the key pair is lost?

## 📝 Practice
- Launch a Linux EC2, install nginx using User Data, open port 80 in the SG and access it from a browser.
- ⚠️ Delete or stop resources after the lab to avoid charges.
