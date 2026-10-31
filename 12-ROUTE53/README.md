# 12 – Route 53

**Category:** 🌐 Networking – DNS

## 📘 What is it?
Highly available managed DNS service with domain registration and health checks.

## 💡 Why it matters
Connects your domain name to AWS resources and enables smart traffic routing and failover.

## 🔑 Concepts
- Hosted zones: public & private
- Records: A, AAAA, CNAME, MX, TXT, NS, SOA
- **Alias** record – AWS-specific, works at zone apex, free queries to AWS resources
- TTL
- Health checks

## 🔑 Routing Policies
- Simple
- Weighted
- Latency-based
- Failover
- Geolocation / Geoproximity
- Multivalue answer

## 💻 Commands / Example
```bash
aws route53 list-hosted-zones
aws route53 list-resource-record-sets --hosted-zone-id <zone-id>
nslookup example.com
dig example.com
```

## ❓ Interview Questions
1. CNAME vs Alias record?
2. Explain Route 53 routing policies.
3. What is TTL?
4. How do you set up DNS failover?

## 📝 Practice
- Point a domain to an ALB using an Alias record and configure failover routing to an S3 static site.
- ⚠️ Delete or stop resources after the lab to avoid charges.
