# 05 – Linux for AWS

**Category:** 🧑‍💻 Foundation

## 📘 What is it?
The operating system running on most EC2 instances (Amazon Linux, Ubuntu, RHEL).

## 💡 Why it matters
Every AWS engineer manages EC2 servers through the Linux command line.

## 🔑 Must-Know Topics
- File system hierarchy, navigation, file management
- Users, groups & permissions
- Package management (`dnf`/`yum` on Amazon Linux, `apt` on Ubuntu)
- Services with `systemctl`
- Processes, disk (`df`, `lsblk`, mount), networking (`ss`, `curl`)
- SSH, `scp`, cron
- 📘 Full 20-day Linux course: see the **Linux-Unlocked** repo

## 💻 Commands / Example
```bash
cat /etc/os-release
sudo dnf install -y httpd
sudo systemctl enable --now httpd
lsblk ; df -h
curl http://169.254.169.254/latest/meta-data/   # needs IMDSv2 token on newer instances
```

## ❓ Interview Questions
1. Default user for Amazon Linux vs Ubuntu?
2. How do you mount an EBS volume?
3. How do you check which port a service listens on?

## 📝 Practice
- On EC2: install Apache, deploy a sample HTML page, and schedule a cron job to back up logs to S3.
- ⚠️ Delete or stop resources after the lab to avoid charges.
