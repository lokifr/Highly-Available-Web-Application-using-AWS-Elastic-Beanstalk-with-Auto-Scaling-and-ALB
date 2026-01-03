# Highly Available Web Application using AWS Elastic Beanstalk with Auto Scaling and ALB

## 📌 Project Overview
This project demonstrates the deployment of a **highly available web application** on AWS using **Elastic Beanstalk**.  
The application automatically scales based on load and remains available even when individual EC2 instances fail.

Elastic Beanstalk abstracts infrastructure management while internally using **EC2, Application Load Balancer, Auto Scaling Group, and CloudWatch**.

---

## 🏗️ Architecture
- AWS Elastic Beanstalk (Web Server Environment)
- Application Load Balancer (managed by Elastic Beanstalk)
- Auto Scaling Group
- Multiple EC2 instances across Availability Zones
- CloudWatch metrics and alarms
- Node.js web application

**Traffic Flow:**
User → Application Load Balancer → EC2 Instances (Auto Scaling Group)

---

## ⚙️ How Elastic Beanstalk Works in This Project
Elastic Beanstalk automatically:
- Creates and manages EC2 instances
- Configures an Application Load Balancer
- Sets up an Auto Scaling Group
- Performs health checks
- Replaces unhealthy instances
- Integrates CloudWatch for monitoring and scaling

The developer only provides the application code.

---

## 🧩 Application Details
- Backend: Node.js
- The application displays the **hostname of the EC2 instance** serving the request
- Hostname change on refresh proves load balancing and high availability

---

## 🧪 High Availability & Auto Scaling Testing

### 1️⃣ Load Balancing Test
- The application shows the instance hostname
- Refreshing the page shows different hostnames
- Confirms traffic distribution through ALB

### 2️⃣ Instance Failure Test
- One EC2 instance was manually terminated
- Application remained accessible
- Auto Scaling Group automatically launched a replacement instance

### 3️⃣ Auto Scaling Test
- Concurrent HTTP requests were generated to simulate traffic
- CPU utilization increased beyond the configured threshold
- Auto Scaling Group launched additional EC2 instances
- When load stopped, instances scaled down automatically

---

## 📊 Monitoring
- CPU utilization monitored using Amazon CloudWatch
- Scaling decisions triggered based on CPU thresholds
- Auto Scaling activity verified through AWS Console

---

## 🛠️ Technologies Used
- AWS Elastic Beanstalk
- Amazon EC2
- Application Load Balancer
- Auto Scaling Group
- Amazon CloudWatch

# Some screenshots of the project
<img width="1916" height="906" alt="Screenshot 2026-01-03 003140" src="https://github.com/user-attachments/assets/8e9eba96-44eb-477e-a13e-1ed36cc2058a" />

<img width="1919" height="908" alt="Screenshot 2026-01-03 003148" src="https://github.com/user-attachments/assets/08a6a33c-9a75-4efb-aa52-9dd703ef09f3" />


<img width="1919" height="912" alt="Screenshot 2026-01-03 003157" src="https://github.com/user-attachments/assets/683ab621-63d2-40fb-ba19-794670265fb0" />
