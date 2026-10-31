# 08 – ELB & Auto Scaling Group

**Category:** 💻 Compute – High Availability

## 📘 What is it?
ELB distributes traffic across healthy targets; ASG automatically adds/removes EC2 instances based on demand.

## 💡 Why it matters
Together they give high availability and scalability – the classic production architecture.

## 🔑 Load Balancer Types
- **ALB** – Layer 7 (HTTP/HTTPS), path & host-based routing
- **NLB** – Layer 4 (TCP/UDP), ultra-low latency, static IP
- **GWLB** – Layer 3, for firewalls/appliances
- Classic LB – legacy
- Target groups & health checks
- Listeners & rules, SSL termination with ACM

## 🔑 Auto Scaling
- Launch Template
- Min / Desired / Max capacity
- Scaling policies: Target tracking, Step, Scheduled, Predictive
- Health checks & self-healing
- Spread across multiple AZs

## 💻 Commands / Example
```bash
aws elbv2 describe-load-balancers
aws elbv2 describe-target-health --target-group-arn <tg-arn>
aws autoscaling describe-auto-scaling-groups
aws autoscaling set-desired-capacity --auto-scaling-group-name myasg --desired-capacity 3
```

## ❓ Interview Questions
1. ALB vs NLB?
2. What is a target group and health check?
3. Scaling policy types?
4. Vertical vs horizontal scaling?

## 📝 Practice
- Create a Launch Template with nginx, an ASG across 2 AZs behind an ALB, and test scaling with a CPU target-tracking policy.
- ⚠️ Delete or stop resources after the lab to avoid charges.
