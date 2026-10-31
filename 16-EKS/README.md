# 16 – EKS – Elastic Kubernetes Service

**Category:** 💻 Containers – Kubernetes

## 📘 What is it?
Managed Kubernetes service – AWS runs and scales the control plane for you.

## 💡 Why it matters
Kubernetes is the industry standard for containers; EKS is how it runs on AWS in production.

## 🔑 Concepts
- Control plane (AWS managed) & worker nodes
- Node types: Managed node groups, self-managed, Fargate
- `eksctl` & `kubectl`
- IAM integration: access entries, IRSA / EKS Pod Identity
- AWS Load Balancer Controller (ALB/NLB from Ingress/Service)
- EBS/EFS CSI drivers for storage
- Cluster Autoscaler / Karpenter

## 💻 Commands / Example
```bash
eksctl create cluster --name demo --region ap-south-1 --nodegroup-name ng1 --node-type t3.medium --nodes 2
aws eks update-kubeconfig --name demo --region ap-south-1
kubectl get nodes
kubectl apply -f deployment.yaml
eksctl delete cluster --name demo --region ap-south-1
```

## ❓ Interview Questions
1. ECS vs EKS?
2. What does AWS manage in EKS?
3. How do pods get AWS permissions securely?
4. How do you expose an app on EKS?

## 📝 Practice
- Create an EKS cluster with eksctl, deploy nginx, expose it with a LoadBalancer service, then delete the cluster to avoid cost.
- ⚠️ Delete or stop resources after the lab to avoid charges.
