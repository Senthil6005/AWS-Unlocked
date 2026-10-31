# 19 – CloudFront & CloudTrail

**Category:** 🌐 CDN & 🔐 Auditing

## 📘 What is it?
CloudFront is a global CDN that caches content at edge locations; CloudTrail records every API call made in your account.

## 💡 Why it matters
CloudFront makes apps faster and more secure; CloudTrail answers 'who did what, when' – critical for security audits.

## 🔑 CloudFront
- Distribution, origin (S3, ALB, EC2, custom), edge locations
- Caching, TTL & invalidation
- HTTPS with ACM certificates (must be in us-east-1 for CloudFront)
- Origin Access Control (OAC) – keep S3 bucket private
- Integration with AWS WAF & Shield

## 🔑 CloudTrail
- Records API activity (console, CLI, SDK)
- Event history – last 90 days free
- Trail – store logs in S3 long term
- Management events vs data events
- Log file integrity validation

## 💻 Commands / Example
```bash
aws cloudfront list-distributions
aws cloudfront create-invalidation --distribution-id <id> --paths "/*"
aws cloudtrail lookup-events --lookup-attributes AttributeKey=EventName,AttributeValue=TerminateInstances --max-results 5
```

## ❓ Interview Questions
1. What is a CDN?
2. What is cache invalidation?
3. How do you keep an S3 origin private?
4. CloudTrail vs CloudWatch?
5. How do you find who terminated an instance?

## 📝 Practice
- Serve a private S3 website through CloudFront with OAC, then use CloudTrail to find who changed the bucket policy.
- ⚠️ Delete or stop resources after the lab to avoid charges.
