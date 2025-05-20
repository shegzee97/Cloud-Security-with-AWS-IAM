# 🛡️Cloud-Security-with-AWS-IAM
## 📘 Project Description
This beginner-friendly project focuses on securing two Amazon EC2 instances using AWS IAM. One EC2 instance represents a **Production Environment**, and the other represents a **Development Environment**. The project demonstrates how to manage user access, enforce least privilege policies, and associate IAM roles to EC2 instances using the AWS Console only.

---

## 🎯 Objectives
- Launch two EC2 instances: Production and Development
- Create IAM users with limited access
- Create and assign IAM roles to EC2 instances
- Apply least privilege principles
- Document the setup visually and clearly

---

## 🧰 Tools & Services Used
- AWS Management Console (no CLI)
- AWS IAM
- Amazon EC2
- IAM Policies and Roles

---

## 🗂️ Project Structure
```bash
aws-iam-ec2-security/
├── screenshots/               # Visual documentation of each step
│   ├── ec2-creation.png
│   ├── iam-role-creation.png
│   ├── iam-user-group.png
│   └── permissions-review.png
└── README.md                 # Project documentation
```

---

## 📝 Step-by-Step Guide

### Step 1: Set Up IAM User and Group
1. Log in to the [AWS Management Console](https://aws.amazon.com/console/)
2. Navigate to **IAM > Users** and create two users:
   - `dev-user` (Developer)
   - `prod-user` (Production Admin)
3. Create two groups:
   - `DevGroup` with access to the Dev EC2 instance only
   - `ProdGroup` with full access to the Prod EC2 instance
4. Attach managed policies like `AmazonEC2ReadOnlyAccess` or create custom policies to limit EC2 instance access by tags.

### Step 2: Launch EC2 Instances
1. Go to **EC2 > Instances**
2. Launch two EC2 instances:
   - Name one `Production-Server`
   - Name the other `Development-Server`
3. Use the **Amazon Linux 2 AMI** for both
4. Add tags like:
   - `Environment: Production`
   - `Environment: Development`

### Step 3: Create IAM Roles
1. Navigate to **IAM > Roles**
2. Create two roles:
   - `ProdEC2Role` with access to logging, monitoring
   - `DevEC2Role` with limited S3 or EC2 access (optional)
3. Use the **EC2** service as the trusted entity
4. Attach roles to the respective EC2 instances

### Step 4: Enforce Best Practices
- Enable MFA for all users
- Set password policies under **Account settings**
- Use tags and condition keys in IAM policies
- Regularly review access using IAM Access Analyzer

---

## 📸 Screenshots
Add screenshots for:
- IAM user and group creation
- IAM role assignment to EC2
- EC2 instance tagging
- Permissions summary

---

## 🎓 Key Takeaways
- IAM roles simplify secure access to AWS services from EC2
- Tag-based access control is powerful and flexible
- The AWS Console provides an intuitive interface for beginners

---

## 📜 License
MIT License — free for personal and commercial use

---

## 🏁 Roadmap
- [ ] Add billing alerts and monitoring
- [ ] Implement logging via CloudWatch
- [ ] Write a walkthrough blog post with visuals

---

## 🧳 Deployment Status
**Project is completed and deployed on AWS Free Tier. Ready for demonstration or enhancement.**
