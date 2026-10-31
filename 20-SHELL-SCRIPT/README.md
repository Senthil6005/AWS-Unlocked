# 20 – Shell Scripting with AWS CLI

**Category:** 🧑‍💻 Automation

## 📘 What is it?
Bash scripts combined with the AWS CLI to automate daily cloud operations.

## 💡 Why it matters
Fast way to automate backups, reports, cleanup and deployments directly from Linux or CloudShell.

## 🔑 Concepts
- Shebang, variables, arguments, `$?`
- if/else, loops, functions
- `--query` (JMESPath) and `--output text/json/table`
- `set -euo pipefail` for safe scripts
- Run with cron or EventBridge + SSM

## 💻 Commands / Example
```bash
#!/bin/bash
set -euo pipefail
REGION="ap-south-1"

# List running instances
aws ec2 describe-instances --region "$REGION" \
  --filters Name=instance-state-name,Values=running \
  --query 'Reservations[].Instances[].[InstanceId,InstanceType]' --output table

# Snapshot all volumes of an instance
for VOL in $(aws ec2 describe-volumes --region "$REGION" \
  --filters Name=attachment.instance-id,Values="$1" \
  --query 'Volumes[].VolumeId' --output text); do
  aws ec2 create-snapshot --volume-id "$VOL" --description "auto-backup $(date +%F)"
done
```

## ❓ Interview Questions
1. What is `--query` in AWS CLI?
2. How do you schedule a script that uses AWS CLI?
3. Why use `set -euo pipefail`?

## 📝 Practice
- Write a script that deletes EBS snapshots older than 7 days and schedule it with cron.
- ⚠️ Delete or stop resources after the lab to avoid charges.
