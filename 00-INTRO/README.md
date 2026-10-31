# 00 – Introduction to Cloud Computing & AWS

## 🎯 Objectives
- Understand cloud computing and why companies move to the cloud
- Learn AWS global infrastructure and core service categories
- Set up your AWS account safely

## 📘 What is Cloud Computing?
- **Cloud computing** = renting IT resources (servers, storage, databases, networking) over the internet, **on-demand**, and **paying only for what you use**.
- No need to buy physical servers or maintain data centers.

## ✅ Benefits of Cloud
| Benefit | Meaning |
|---------|---------|
| **Pay-as-you-go** | No upfront cost; pay per hour/second/GB |
| **Scalability** | Increase or decrease resources in minutes |
| **Elasticity** | Scale automatically with traffic |
| **High Availability** | Run across multiple data centers |
| **Global Reach** | Deploy near users worldwide in minutes |
| **Security** | Enterprise-grade security & compliance |
| **Speed / Agility** | Launch servers in minutes, not weeks |

## ☁️ Cloud Service Models
| Model | You manage | Provider manages | AWS Example |
|-------|-----------|------------------|-------------|
| **IaaS** | OS, apps, data | Hardware, network | EC2, VPC, EBS |
| **PaaS** | Apps, data | OS, runtime, servers | Elastic Beanstalk, RDS |
| **SaaS** | Only usage | Everything | Gmail, Amazon WorkMail |
| **Serverless / FaaS** | Only code | Everything else | Lambda |

## 🌐 Cloud Deployment Models
| Model | Description |
|-------|-------------|
| **Public Cloud** | Shared provider infrastructure (AWS, Azure, GCP) |
| **Private Cloud** | Dedicated to one organization |
| **Hybrid Cloud** | Mix of on-premises + public cloud |
| **Multi-Cloud** | Using more than one cloud provider |

## 🏢 Major Cloud Providers
| Provider | Company |
|----------|---------|
| AWS | Amazon (launched 2006 – market leader) |
| Azure | Microsoft |
| GCP | Google |
| OCI | Oracle |

## 🗺️ AWS Global Infrastructure
| Component | Meaning |
|-----------|---------|
| **Region** | Geographic area with multiple data centers (e.g., `ap-south-1` Mumbai, `ap-south-2` Hyderabad) |
| **Availability Zone (AZ)** | One or more isolated data centers inside a region (e.g., `ap-south-1a`) |
| **Edge Location** | Cache sites for CloudFront & Route 53 – closer to users |
| **Local Zones / Wavelength** | Extend AWS closer to cities & 5G networks |

### How to choose a Region
1. **Compliance** – data laws (some data must stay in India)
2. **Latency** – close to your users
3. **Service availability** – not every service is in every region
4. **Pricing** – cost differs by region

## 🤝 Shared Responsibility Model
| AWS is responsible for | You are responsible for |
|------------------------|-------------------------|
| Security **OF** the cloud | Security **IN** the cloud |
| Physical data centers, hardware, network, hypervisor | Data, IAM users & permissions, OS patching (EC2), security groups, encryption choices, app code |

## 🧰 AWS Service Categories (this course)
| Category | Services |
|----------|----------|
| 💻 Compute | EC2, Lambda, ECS, EKS, ELB & ASG |
| 📦 Storage | S3, EBS, EFS |
| 🗄️ Database | RDS |
| 🌐 Networking | VPC, Route 53, CloudFront |
| 🔐 Security | IAM, KMS, CloudTrail |
| 📨 Integration | SNS, SQS, SES |
| 📊 Monitoring | CloudWatch |
| 🏗️ DevOps & IaC | CloudFormation, CodeDeploy, CodePipeline |
| 🧑‍💻 Scripting | Linux, Python (boto3), Shell scripting |

## 🔐 Account Setup – Best Practices (Do this on Day 1!)
1. Create the AWS account and **enable MFA on the root user**.
2. **Never use the root user** for daily work – create an IAM admin user/role.
3. Set up a **Billing alarm / AWS Budget** to avoid surprise bills.
4. Choose one region for labs (e.g., `ap-south-1` Mumbai).
5. **Stop or delete** resources after every lab.
6. Never share or commit access keys to GitHub.

## 💻 Ways to Access AWS
| Method | Use |
|--------|-----|
| **Management Console** | Web UI |
| **AWS CLI** | Command line automation |
| **SDKs** | Code (Python boto3, Java, Node.js) |
| **CloudShell** | Browser-based terminal with CLI pre-installed |
| **IaC** | CloudFormation, Terraform |

```bash
aws configure                 # set access key, secret, region, output
aws sts get-caller-identity   # who am I?
aws ec2 describe-regions --output table
```

## 💰 Pricing Basics
- **Pay for:** compute time, storage used, and **data transfer OUT** to the internet.
- **Data transfer IN** is generally free.
- Use the **AWS Pricing Calculator** to estimate costs.
- Check the current Free Tier offer on the AWS website – it changes over time.

## ❓ Interview Questions
1. What is cloud computing? Name its benefits.
2. IaaS vs PaaS vs SaaS – give AWS examples.
3. Region vs Availability Zone vs Edge Location?
4. Explain the Shared Responsibility Model.
5. Why should you not use the root account?
6. Scalability vs elasticity?
7. How do you avoid unexpected AWS bills?

## 📝 Practice
- Create an AWS account, enable root MFA, create an IAM admin user and set a budget alert.
- Install AWS CLI, run `aws configure` and `aws sts get-caller-identity`.
