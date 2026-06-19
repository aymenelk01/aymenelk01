# Aymen-Elkharchi
Who's Aymen Elkharchi?

**Junior Cloud Engineer | AWS Builder | Infrastructure as Code**  
Based in Italy

---

## About me

I'm an aspiring Junior Cloud Engineer with a foundation in networking and cloud fundamentals. I'm actively building production-grade cloud infrastructure on AWS and pursuing the **AWS Solutions Architect Associate (SAA-C03) certification**.

My approach: hands-on infrastructure as code, architectural design patterns, and shipping real systems. I document my learning journey on LinkedIn to share what I build.

---

## Tech Stack

- **Cloud Platform**: AWS (VPC, EC2, RDS/AURORA, S3, CloudFront, ALB, ASG, DynamoDB, IAM, ECS)
- **Infrastructure as Code**: Terraform (modular architecture, multi-module projects)
- **Networking**: VLSM, VLANs, security groups, routing, NAT Gateways, VPC Endpoints

---

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

**Key implementations**: Security group chaining (ALB→EC2→RDS), SSM Session Manager access, CloudWatch agents collecting nginx + system metrics, RDS slow query logging, least privilege IAM roles, S3 image sync via cron, Terraform best practices (modular, DRY, depends_on for circular deps, create_before_destroy lifecycle)

**Modules**: vpc, security, compute, database, storage, cdn

 **[View on GitHub](https://github.com/aymenelk01/Aws-Three-Tier-Infrastructure)**

---

### 2️⃣ Massar — AWS redesign of Moroccan education platform

**Status**: **IN PROGRESS** — VPC module and architecture finalized, building remaining modules.

An architecture study redesigning the Moroccan Ministry of Education's Massar platform for AWS, handling **495,000 simultaneous users** during results release.

**Real-world context**: Current Massar (Azure) had a security breach (March 2025). AWS redesign adds WAF, auto-scaling, and proper traffic shaping.

**Architecture**:
- **Security boundary**: CloudFront + WAF (SQL injection, XSS, rate limiting, geo-restriction to Morocco)
- **Load balancing**: ALB (no NAT Gateway needed)
- **Authentication**: Amazon Cognito (8M+ users, Code Massar as username)
- **Compute**: ECS Fargate in private app subnets (30-60s scaling vs EC2's 3-5min)
- **Cache layer**: ElastiCache Redis (absorbs read spike before Aurora)
- **Database**: Aurora Serverless v2 MySQL (auto-scales for spike days, pay-per-use)
- **Connection pooling**: RDS Proxy (prevents Aurora exhaustion during scaling)
- **Notifications**: SQS → Lambda → SNS (shapes 500k notifications over time, prevents spike collapse)
- **Storage**: S3 for student documents, transcripts, certificates
- **Networking**: 3 AZs, Interface Endpoints for ECR/CloudWatch Logs (no internet egress needed)

**Architectural decisions**: ECS Fargate (no OS patching), Aurora Serverless v2 (cost optimization), RDS Proxy (connection safety), Interface Endpoints (no NAT Gateway), eu-south-1 region (data sovereignty, closest to Morocco)

**Modules planned**: vpc (in progress), security, ecr, ecs, cognito, database, cache, storage, cdn, notifications

**Next**: Finish VPC module → build security module → remaining 8 modules → mock Massar app (Flask/Node.js) → containerize → GitHub

**[View on GitHub](https://github.com/aymenelk01/massar-aws-infrastructure)**

---

## Learning Goals

- ✅ **AWS SAA-C03 Certification** — In progress with freeCodeCamp (~6 hrs/day, 3-month timeline). Hands-on labs with this infrastructure project.
- ✅ **Infrastructure as Code mastery** — Building modular, DRY, repeatable Terraform code following best practices.
- ✅ **Production-grade architecture** — Designing systems that follow AWS Well-Architected Framework principles (security, reliability, cost optimization).

---

## Beyond Tech

When I'm not building infrastructure, you'll find me:

- ⚽ Playing football
- 🎮 Gaming
- 📸 Photography & cameras
- ✈️ Traveling
- 🗳️ Following politics

---

## Let's Connect

- **GitHub**: [aymenelk01](https://github.com/aymenelk01)
- **LinkedIn**: [Connect with me](www.linkedin.com/in/aymen-elkharchi-640a30312)
- **Email**: aymenelkharchi15@gmail.com

---

**Currently**: Completing SAA-C03 certification • Building Massar AWS architecture (VPC module in progress) • Sharing learnings on LinkedIn

```
Built with AWS • Terraform • ☕ • 🇮🇹
```
