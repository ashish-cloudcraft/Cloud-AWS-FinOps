# 📦 Cloud-AWS-FinOps

**Cost Optimization and Automation for AWS Cloud Infrastructure**

This repository provides Lambda functions, scripts, and automation templates focused on **AWS Financial Operations (FinOps)**.  
The goal is to **reduce cloud costs**, **automate EC2 management**, and **optimize AWS resource usage** without impacting performance.

---

## 🚀 Features
- ✅ Auto Start/Stop EC2 instances based on time schedules
- ✅ Single Lambda function to smartly decide Start/Stop
- ✅ EventBridge (CloudWatch) scheduled triggers
- ✅ Instance management based on Tags
- ✅ Minimal IAM permissions for security
- ✅ CloudWatch logging for auditing actions
- ✅ Easy deployment using Terraform (coming soon)

---

## 🌩️ Use Cases
- Lower AWS costs by shutting down non-critical resources during off-hours
- Manage development/test environments automatically
- Scale manual environments without relying fully on AutoScaling Groups
- Improve production FinOps compliance for startups and enterprises

---

## 🛠️ Tech Stack
- AWS Lambda (Python 3.9+)
- Boto3 SDK
- Amazon EventBridge (Scheduled Rules)
- Amazon EC2 API
- (Optional) Terraform / AWS CDK for IaC

---

## 📋 Requirements
- AWS Account
- EC2 Instances to manage
- IAM Role for Lambda with permissions:
  - `ec2:StartInstances`
  - `ec2:StopInstances`
  - `ec2:DescribeInstances`
- Basic knowledge of AWS Lambda and CloudWatch

---

## 📑 How It Works
1. **Lambda function** checks the **current UTC time**.
2. If within **working hours**, it **starts EC2 instances**.
3. If outside working hours, it **stops EC2 instances**.
4. **EventBridge Rule** triggers Lambda on a schedule (e.g., every 15 minutes).
5. **Logs** are automatically pushed to **CloudWatch Logs**.

---

## 🖥️ Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/cloud-aws-finops.git
   cd cloud-aws-finops
2. Update the Lambda function:
   Set your correct INSTANCE_IDS
   
   Set your AWS REGION
   
   Set START_HOUR and STOP_HOUR in UTC
 
3. Create the AWS Lambda function:
    Use Python 3.9 runtime
    
    Attach IAM role with necessary EC2 permissions
    
    Add a CloudWatch EventBridge Rule for scheduled triggers
   
5. Monitor via CloudWatch Logs

## 📈 Future Roadmap
   SNS Notifications for start/stop events
   
   Smart dynamic tag-based instance management
   
   Cost reports via AWS Budgets API

## 🤝 Contributing
  Pull requests are welcome! 🙌
  
  For major changes, please open an issue first to discuss what you would like to change

## ✨ Maintainer
Created and maintained by Ashish.

