# 18 – CodeDeploy & CodePipeline

**Category:** 🏗️ CI/CD

## 📘 What is it?
CodePipeline orchestrates release stages; CodeDeploy automates deployments to EC2, on-premises, Lambda and ECS.

## 💡 Why it matters
AWS native CI/CD – from GitHub commit to production deployment automatically.

## 🔑 CodePipeline
- Stages: Source (GitHub/CodeCommit/S3) → Build (CodeBuild) → Deploy
- Artifacts stored in S3
- Manual approval actions

## 🔑 CodeBuild
- Managed build service using `buildspec.yml`

## 🔑 CodeDeploy
- `appspec.yml` with lifecycle hooks (BeforeInstall, AfterInstall, ApplicationStart, ValidateService)
- CodeDeploy agent on EC2
- Deployment types: In-place & Blue/Green
- Deployment configs: AllAtOnce, HalfAtATime, OneAtATime

## 💻 Commands / Example
```yaml
# appspec.yml (EC2)
version: 0.0
os: linux
files:
  - source: /
    destination: /var/www/html
hooks:
  AfterInstall:
    - location: scripts/restart.sh
      timeout: 300

# Check agent
sudo systemctl status codedeploy-agent
```

## ❓ Interview Questions
1. In-place vs Blue/Green deployment?
2. What is appspec.yml vs buildspec.yml?
3. CodePipeline vs Jenkins?

## 📝 Practice
- Build a pipeline: GitHub → CodeBuild → CodeDeploy to EC2 behind an ALB.
- ⚠️ Delete or stop resources after the lab to avoid charges.
