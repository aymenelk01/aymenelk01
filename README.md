# Aymen Elkharchi
Who's Aymen Elkharchi?

**Junior Cloud Engineer | AWS | Terraform | Infrastructure as Code**  
**Based in Italy**

---

## About me

- I'm Junior Cloud Engineer with a Higher Technical Diploma in ICT from ITS Fabriano and hands-on experience designing and deploying production-grade AWS infrastructure from scratch. I build real systems — not tutorials — using Terraform, GitHub Actions CI/CD pipelines following the The AWS Well-Architected Framework and least privilege principe. Currently pursuing the AWS Solutions Architect Associate (SAA-C03) certification and building projects for my portfolio.
- I document what I build on LinkedIn.

---

## Tech Stack

- **Cloud Platform**: AWS (VPC, IAM, ECS Fargate, RDS/AURORA, EC2, ElastiCache, CloudFront, WAFv2, ALB, Cognito, SQS, Lambda, SNS, SES, Bedrock, ECR, Secrets Manager, SSM, CloudWatch, S3)
- **Infrastructure as Code**: Terraform — modular architecture, CI/CD integration
- **CI/CD**: GitHub Actions 
- **Containers:** Docker, ECS Fargate, 
---
## Educations
**Higher Technical Institute (ITS) Fabriano — 2024–2026**
- Higher Technical Diploma in ICT
- Coursework: Web Development, Database Design, Networking, Cloud Architecture

## Experience
**(Intership)Full Stack Developer — 2025**
- Built a full-stack web platform featuring secure file transfer via email and Google Drive integration, user authentication (login/sign up), an dashboard for users, and an AI chatbot for file analysis and user guidance.
- Stack: Angular, NestJS, MongoDB

**(Intership)Full Stack Developer — 2026**
- Built a Business Registry Platform — a comprehensive supply chain and business management solution for small to mid-sized enterprises. The platform covers customer and supplier registries, product catalogs, warehouse inventory tracking with real-time stock levels, complete order lifecycle management, this platform includes secure user authentication with the ability to create user accounts with specific roles and permissions, role-based access control, and Excel integration capabilities for seamless data import and export, enabling businesses to centralize their operations and improve operational efficiency through a single, unified web-based interface.
- Stack: Angular, Node.js, SQL Server
- **Currently designing the infrastructure of this web application on AWS.**

## Portfolio Projects

### 1️⃣ Three-tier e-commerce infrastructure on AWS

**Status**:  **COMPLETE** — All 6 modules built, tested, and deployed.

A production-grade infrastructure built entirely with **Terraform modules**, deployed in `eu-south-1` (Milan).

**Architecture**:
- **Network**: VPC with public/private/database subnets across 2 AZs, NAT Gateways, Gateway Endpoints for S3 + DynamoDB, DB subnet with no internet route
- **Compute**: Application Load Balancer + Auto Scaling Group + EC2 with Systems Manager (no bastion host)
- **Database**: RDS MySQL with slow query logging, DynamoDB session & user tables with TTL encryption, GSI
- **Storage**: S3 static bucket, logs bucket with lifecycle policies (STANDARD→IA→GLACIER→expire), state bucket with versioning
- **CDN**: CloudFront with Origin Access Control (OAC), SigV4 signing, S3 fully private, ALB restricted to CloudFront IPs

**Modules**: vpc, security, compute, database, storage, cdn

 **[View on GitHub for more informations](https://github.com/aymenelk01/Aws-Three-Tier-Infrastructure)**

---

### 2️⃣ Massar — AWS Redesign of Morocco's National Education Platform
**Status**:  **COMPLETE** — Infrastructure fully provisioned, application deployed, CI/CD pipelines live.
A production-grade AWS infrastructure redesign of the Moroccan Ministry of Education's Massar platform, built entirely with Terraform and automated via GitHub Actions.
Real-world context: The current Massar platform crashes annually on Baccalaureate results release day under millions of simultaneous requests. A security breach in March 2025 further exposed the platform's infrastructure gaps. This redesign addresses both.
Architecture:

- **Edge Security:** CloudFront + WAFv2 (SQL injection, XSS, rate limiting, IP reputation, Log4j protection)
- **Authentication:** Amazon Cognito (JWT-based, role groups for students, teachers, and admins)
- **Compute:** ECS Fargate on Graviton ARM64 — private subnets, no public IPs, auto-scaling 2–10 tasks on CPU utilization
- **Cache:** ElastiCache Redis 7 — look-aside caching absorbs read spike before hitting Aurora
- **Database:** Aurora Serverless v2 MySQL — scales in ACU increments, pay-per-use
- **Connection Pooling:** RDS Proxy with IAM database authentication — no static credentials
- **Async Processing:** SQS → Lambda → SES/SNS for notifications, SQS → Lambda → S3 for PDF diploma generation
- **AI:** Amazon Bedrock Nova Pro via Converse API for student academic guidance
- **Networking:** 3 AZs, no NAT Gateway — all AWS API traffic routed through VPC Interface Endpoints
- **CI/CD:** GitHub Actions with OIDC keyless auth, Checkov security gates, Infracost on every PR

**[View on GitHub for more informations](https://github.com/aymenelk01/massar-aws-infrastructure)**

---

## Learning Goals

- ✅ **AWS SAA-C03 Certification** — In progress. Hands-on labs with this infrastructure project.
- ✅ **Infrastructure as Code mastery** — Building modular, DRY, repeatable Terraform code following best practices.
- ✅ **Production-grade architecture** — Designing systems that follow AWS Well-Architected Framework principles.

---

## Beyond Tech

When I'm not building infrastructure, you'll find me:

- Playing football
- Gaming
- Photography & cameras
- Traveling
- Following politics

---

## Let's Connect

- **GitHub**: [aymenelk01](https://github.com/aymenelk01)
- **LinkedIn**: [Connect with me](www.linkedin.com/in/aymen-elkharchi-640a30312)
- **Email**: aymenelkharchi15@gmail.com
- **Phone:** +393314379373

---

**Currently**: Completing SAA-C03 certification • Building My third AWS architecture Porject using terraform  • Sharing learnings on LinkedIn

