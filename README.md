
# 🚀 Production-Style vProfile Cloud Migration on AWS (Lift & Shift)

A production-style migration of the **vProfile multi-tier Java application** to **Amazon Web Services (AWS)** using the **Lift & Shift** migration strategy. This project focuses on building a scalable, highly available, and secure cloud architecture while minimizing application changes during migration.

---

## 📖 Overview

The original vProfile application was deployed on traditional virtual machines. This project migrates the application to AWS while preserving its architecture and enhancing it with cloud-native capabilities such as:

- High Availability
- Auto Scaling
- Load Balancing
- Secure Networking
- Centralized Artifact Storage
- DNS-based Service Discovery

The deployment closely resembles a production environment using core AWS services.

---

# 🏗️ Architecture

<p align="center">
<img src="architecture.png" width="900">
</p>

---

# ☁️ AWS Services Used

- Amazon EC2
- Application Load Balancer (ALB)
- Auto Scaling Groups
- Amazon Route 53
- Route 53 Private Hosted Zone
- Amazon S3
- Amazon Security Groups

---

# ⚙️ Technology Stack

| Category | Technologies |
|-----------|--------------|
| Cloud | AWS |
| Compute | Amazon EC2 |
| Load Balancing | Application Load Balancer |
| Scaling | Auto Scaling Group |
| Storage | Amazon S3 |
| DNS | Amazon Route 53 |
| Web Server | Apache Tomcat |
| Database | MySQL |
| Messaging | RabbitMQ |
| Caching | Memcached |
| OS | Ubuntu Linux |
| Language | Java |

---

# 🏛️ Architecture Components

## 🌐 DNS Layer

- Public domain configured using GoDaddy
- Amazon Route 53 manages DNS resolution
- Traffic routed securely to the Application Load Balancer

---

## ⚖️ Load Balancer

Application Load Balancer (ALB)

- Receives HTTPS requests
- Distributes traffic across multiple Tomcat instances
- Performs health checks
- Improves application availability

---

## 🚀 Application Tier

- Apache Tomcat deployed on EC2
- Multiple instances managed by Auto Scaling Group
- Automatically scales based on demand
- Downloads application artifacts from Amazon S3

---

## 📦 Storage Layer

Amazon S3 is used for

- WAR artifacts
- Deployment packages
- Centralized artifact management

---

## 🔐 Private Backend Services

Dedicated EC2 instances host

- MySQL Database
- RabbitMQ Message Broker
- Memcached Cache

Backend services communicate through a Route 53 Private Hosted Zone and are not publicly accessible.

---

## 🛡️ Security

Security Groups isolate every application layer.

- Internet → ALB (HTTPS)
- ALB → Tomcat (8080)
- Tomcat → MySQL
- Tomcat → RabbitMQ
- Tomcat → Memcached

No backend service is directly exposed to the Internet.

---

# 🔄 Deployment Workflow

```
User
    │
    ▼
Route 53
    │
    ▼
Application Load Balancer
    │
    ▼
Auto Scaling Group
    │
    ▼
Tomcat EC2 Instances
    │
    ▼
Route 53 Private Hosted Zone
    │
 ┌──┼─────────────┐
 ▼  ▼             ▼
MySQL RabbitMQ Memcached
    │
    ▼
Application Artifacts
(Amazon S3)
```

---

# 📂 Project Features

- Lift & Shift Cloud Migration
- Production-style Multi-tier Architecture
- High Availability
- Elastic Load Balancing
- Auto Scaling
- Private DNS Resolution
- Secure Network Segmentation
- Artifact Management using Amazon S3
- Layered Security Groups
- Production-style AWS Deployment

---

# 📈 Key Learning Outcomes

Through this project, I gained hands-on experience with

- AWS Cloud Architecture
- Lift & Shift Migration Strategy
- High Availability Design
- Auto Scaling Groups
- Application Load Balancing
- Route 53 Public & Private Hosted Zones
- Amazon EC2 Administration
- Security Group Design
- Cloud Networking
- Production Deployment Strategies

---

# 📁 Repository Structure

```
vprofile-aws-lift-shift/
│
├── scripts/
├── configuration/
├── deployment/
├── architecture.png
├── README.md
└── LICENSE
```

---

# 🚀 Future Improvements

- Infrastructure as Code using Terraform
- CI/CD with GitHub Actions
- Docker Containerization
- Kubernetes Deployment (Amazon EKS)
- GitOps using Argo CD
- Monitoring with Prometheus & Grafana
- Centralized Logging with Loki

---

# 👨‍💻 Author

**Eranga Kavishanka**

- AWS Certified Cloud Practitioner (AWS CCP)
- Kubernetes and Cloud Native Associate (KCNA)
- Software Engineering Undergraduate
- DevOps | Cloud | Site Reliability Engineering (SRE)

---

## ⭐ If you found this project useful, consider giving it a Star!

# vprofile-aws-lift-and-shift-


AWS Lift &amp; Shift Architecture for vProfile Application
 1. Created EC2 instances using user-data scripts
2. Configured security groups and key pairs
3. Built application using Maven
4. Uploaded artifact to S3
5. Deployed artifact to Tomcat servers
6. Configured ELB with HTTPS (ACM)
7. Mapped domain using Route 53
8. Enabled Auto Scaling Group
