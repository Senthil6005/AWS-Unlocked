# 17 – CloudFormation

**Category:** 🏗️ Infrastructure as Code

## 📘 What is it?
AWS native IaC service – define resources in YAML/JSON templates and deploy them as stacks.

## 💡 Why it matters
Repeatable, version-controlled infrastructure with automatic rollback on failure.

## 🔑 Concepts
- Template sections: Parameters, Mappings, Conditions, Resources (required), Outputs
- Stack, StackSets (multi-account/region)
- Change Sets – preview changes
- Intrinsic functions: `!Ref`, `!GetAtt`, `!Sub`, `!Join`
- Drift detection
- Rollback on failure
- Nested stacks

## 💻 Commands / Example
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Resources:
  MyBucket:
    Type: AWS::S3::Bucket
Outputs:
  BucketName:
    Value: !Ref MyBucket

# CLI
aws cloudformation deploy --template-file s3.yaml --stack-name demo-stack
aws cloudformation describe-stacks --stack-name demo-stack
aws cloudformation delete-stack --stack-name demo-stack
```

## ❓ Interview Questions
1. CloudFormation vs Terraform?
2. What is a Change Set?
3. What is drift detection?
4. What happens if stack creation fails?

## 📝 Practice
- Write a template that creates a VPC, subnet and EC2 with a parameter for instance type.
- ⚠️ Delete or stop resources after the lab to avoid charges.
