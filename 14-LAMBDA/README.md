# 14 – Lambda

**Category:** 💻 Serverless Compute

## 📘 What is it?
Run code without managing servers – triggered by events, billed per request and duration.

## 💡 Why it matters
Perfect for automation, APIs and event-driven workflows with zero idle cost.

## 🔑 Concepts
- Function, handler, runtime (Python, Node.js, Java, etc.)
- Triggers: S3, API Gateway, SQS, EventBridge schedule, DynamoDB
- Execution role (IAM)
- Memory 128 MB – 10 GB (CPU scales with memory)
- Max timeout 15 minutes
- Cold start
- Environment variables, layers, versions & aliases
- Concurrency limits

## 💻 Commands / Example
```python
import json

def lambda_handler(event, context):
    print("Event:", json.dumps(event))
    return {"statusCode": 200, "body": "Hello from Lambda"}

# CLI
aws lambda list-functions
aws lambda invoke --function-name myfunc out.json
```

## ❓ Interview Questions
1. What is serverless?
2. Lambda max timeout?
3. What is a cold start?
4. Lambda vs EC2 – when to use which?

## 📝 Practice
- Create a Lambda (Python) triggered by EventBridge every evening to stop all dev EC2 instances.
- ⚠️ Delete or stop resources after the lab to avoid charges.
