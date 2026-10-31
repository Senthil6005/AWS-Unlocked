# 04 – VPC – Virtual Private Cloud

**Category:** 🌐 Networking

## 📘 What is it?
Your own logically isolated private network inside AWS.

## 💡 Why it matters
Every EC2, RDS, EKS and Lambda (in VPC) lives inside a VPC – networking is the backbone of AWS architecture.

## 🔑 Concepts
- CIDR block (e.g., `10.0.0.0/16`)
- Subnets – public (route to IGW) and private
- Internet Gateway (IGW) – internet access for public subnets
- NAT Gateway – outbound internet for private subnets
- Route Tables
- Security Groups (stateful, instance level, allow only)
- NACLs (stateless, subnet level, allow + deny)
- VPC Peering, Transit Gateway
- VPC Endpoints (Gateway for S3/DynamoDB, Interface/PrivateLink)
- Bastion host
- VPC Flow Logs
- AWS reserves 5 IPs in every subnet

## 💻 Commands / Example
```bash
aws ec2 create-vpc --cidr-block 10.0.0.0/16
aws ec2 create-subnet --vpc-id <vpc-id> --cidr-block 10.0.1.0/24 --availability-zone ap-south-1a
aws ec2 create-internet-gateway
aws ec2 attach-internet-gateway --vpc-id <vpc-id> --internet-gateway-id <igw-id>
aws ec2 describe-route-tables
```

## ❓ Interview Questions
1. Public vs private subnet?
2. IGW vs NAT Gateway?
3. Security Group vs NACL?
4. What is VPC peering? Is it transitive?
5. How does a private EC2 download updates?

## 📝 Practice
- Build a custom VPC with 2 public and 2 private subnets across 2 AZs, IGW, NAT Gateway and a bastion host.
- ⚠️ Delete or stop resources after the lab to avoid charges.
