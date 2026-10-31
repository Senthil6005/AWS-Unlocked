# 11 – ECS – Elastic Container Service

**Category:** 💻 Containers

## 📘 What is it?
AWS-managed container orchestration service to run Docker containers.

## 💡 Why it matters
Simpler than Kubernetes for many teams; deeply integrated with ALB, IAM and CloudWatch.

## 🔑 Concepts
- Cluster, Task Definition, Task, Service
- Launch types: **Fargate** (serverless) vs **EC2**
- ECR – Elastic Container Registry for images
- Task role (app permissions) vs Task execution role (pull image, logs)
- Service auto scaling & ALB integration
- awsvpc network mode

## 💻 Commands / Example
```bash
aws ecr create-repository --repository-name myapp
aws ecr get-login-password | docker login --username AWS --password-stdin <account-id>.dkr.ecr.ap-south-1.amazonaws.com
docker push <account-id>.dkr.ecr.ap-south-1.amazonaws.com/myapp:1.0
aws ecs list-clusters
aws ecs list-services --cluster mycluster
```

## ❓ Interview Questions
1. Fargate vs EC2 launch type?
2. Task vs Service?
3. Task role vs execution role?
4. ECS vs EKS?

## 📝 Practice
- Push a Docker image to ECR and run it on ECS Fargate behind an ALB.
- ⚠️ Delete or stop resources after the lab to avoid charges.
