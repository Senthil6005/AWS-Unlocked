# 13 – SNS, SQS, SES & CloudWatch

**Category:** 📨 Integration & 📊 Monitoring

## 📘 What is it?
Messaging, email and monitoring services that connect and observe your applications.

## 💡 Why it matters
Decouple applications, send notifications, and monitor everything with alarms and logs.

## 🔑 SNS – Simple Notification Service
- Pub/Sub: topics & subscribers (email, SMS, SQS, Lambda, HTTP)
- Push-based, fan-out pattern

## 🔑 SQS – Simple Queue Service
- Message queue, pull-based – decouples producers & consumers
- Standard (at-least-once, best-effort order) vs FIFO (exactly-once processing, ordered)
- Visibility timeout, Dead Letter Queue (DLQ), long polling

## 🔑 SES – Simple Email Service
- Send transactional & marketing emails
- Verify domains/emails; new accounts start in sandbox

## 🔑 CloudWatch
- Metrics (default EC2 metrics don't include memory/disk – needs CloudWatch Agent)
- Alarms → SNS notifications / Auto Scaling actions
- Logs, Log Groups, Logs Insights
- Dashboards
- EventBridge (formerly CloudWatch Events) for event rules & schedules

## 💻 Commands / Example
```bash
aws sns create-topic --name alerts
aws sns subscribe --topic-arn <arn> --protocol email --notification-endpoint <your-email>
aws sqs create-queue --queue-name orders
aws sqs send-message --queue-url <url> --message-body "order-101"
aws cloudwatch put-metric-alarm --alarm-name high-cpu --metric-name CPUUtilization --namespace AWS/EC2 --statistic Average --period 300 --threshold 80 --comparison-operator GreaterThanThreshold --evaluation-periods 1 --alarm-actions <sns-arn>
```

## ❓ Interview Questions
1. SNS vs SQS?
2. Standard vs FIFO queue?
3. What is a Dead Letter Queue?
4. How do you monitor EC2 memory usage?
5. What is the fan-out pattern?

## 📝 Practice
- Create a CloudWatch alarm on EC2 CPU > 80% that sends an email through SNS.
- ⚠️ Delete or stop resources after the lab to avoid charges.
