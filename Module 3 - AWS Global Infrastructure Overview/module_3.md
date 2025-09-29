# 🌎 Module 3 - AWS Global Infrastructure Overview

## 1️⃣ Section 1: AWS Global Infrastructure

### 🟠 AWS Global Infrastructure

- Designed for: **flexibility, reliability, scalability, security**.
- Provides **high-quality global network performance**.

### 🟠 AWS Regions

- AWS has **22 Regions worldwide**.
- **Region** = geographical location with one or more **Availability Zones (AZs)**.
- **Availability Zones** = one or more **data centers**.
- **Isolation**:
    - Regions are independent for **fault tolerance** and **stability**.
    - Resources are **not automatically replicated** across Regions.
    - If replication is required, the **customer is responsible**.
- **Region enablement**:
    - Regions before **March 20, 2019** → enabled by default.
    - Regions after (e.g., Hong Kong, Bahrain) → must be manually enabled.
- **Restricted Regions**:
    - **China (Beijing, Ningxia)** → only with AWS China accounts.
    - **AWS GovCloud (US)** → for US government workloads, regulatory compliance.

### 🟠 Selecting a Region

When choosing a Region, consider:

1. **Data governance & legal requirements**
    - Example: EU Data Protection Directive may restrict where data can be stored.
2. **Latency**
    - Best practice: choose a Region **closest to your users/systems**.
    - Tool: [CloudPing](http://www.cloudping.info/) → measure latency to Regions.
3. **Service availability**
    - Not all services are in all Regions → check before deploying.
4. **Cost variation**
    - Example (On-Demand EC2 t3.medium, Linux):
        - **US East (Ohio)**: $0.0416/hour
        - **Asia Pacific (Tokyo)**: $0.0544/hour

### 🟠 Availability Zones

- Each Region has multiple **AZs** (usually 3).
- **AZ features**:
    - Isolated locations with their own power and infrastructure.
    - Physically separated by **many kilometers**, but within **100 km**.
    - Contain **multiple data centers** (up to hundreds of thousands of servers).
    - Connected with **high-bandwidth, low-latency, redundant fiber**.
    - Support **synchronous replication**.
- **Benefits**:
    - Build apps that are **highly available, fault tolerant, and scalable**.
    - Protects against local disasters (e.g., lightning, tornadoes, earthquakes).
- **Best practices**:
    - Distribute systems across **multiple AZs**.
    - Design apps to survive **temporary or prolonged AZ failures**.

### 🟠 AWS data centers

- **Most granular choice** customers can make = **AZ**, not individual data centers.
- Data centers = actual **physical sites** where data resides.
- **Design principles**:
    - Sites chosen to **reduce environmental risk**.
    - Redundant design anticipating/tolerating failures.
    - Critical systems **backed up across AZs**.
    - Continuous monitoring ensures capacity.
    - Locations are **undisclosed** and access is restricted.
    - Automated failover → reroutes traffic during failures.
- **Technology**: AWS uses **custom-built networking equipment** from multiple **Original Device Manufacturers (ODMs)**.

### 🟠 Points of Presence

Amazon CloudFront is a content delivery network (CDN) used to distribute content to end users to reduce latency.

Amazon Route 53 is a Domain Name System (DNS) service.Requests going to either one of these services will be routed to the nearest edge location automatically in order to lower latency.

- Support services like:
    - **Amazon CloudFront** (CDN).
    - **Amazon Route 53** (DNS).
    - **AWS Shield**.
    - **AWS WAF**.
- Located in **major cities worldwide**.
- Purpose:
    - Route requests to the **nearest edge location** to reduce latency.
    - Continuously optimize connectivity and routing.
- **Regional Edge Caches**:
    - Store less frequently accessed content.
    - Reduce need to fetch data from the origin server.

### 🟠 AWS infrastructure features

The AWS Global Infrastructure has several valuable features:

- First, it is elasticand scalable. This means resources can dynamically adjust to increases or decreases in capacity requirements. It can also rapidly adjust to accommodate growth.
- Second, this infrastructure is fault tolerant, which means it has built-in component redundancy which enables it to continue operations despite a failed component.
- Finally, it requires minimal to no human intervention, while providing high availability with minimal down time.

**Resume:**

- **Elastic & Scalable** → resources adjust dynamically to demand.
- **Fault Tolerant** → redundancy ensures continued operation despite failures.
- **Highly Available & Automated** → minimal downtime, minimal human intervention.

## 2️⃣ Section 2: AWS services and service category overview

### 🟠 AWS foundational services

- Built on: **Regions, AZs, PoPs**.
- Deliver: **networking, compute, storage, databases**.
- On-demand utility → **available in seconds, pay-as-you-go**.

### 🟠 AWS categories of services

- AWS has **23 service categories**.
- Exam focus categories:
    - **Compute**
    - **Storage**
    - **Database**
    - **Networking & Content Delivery**
    - **Security, Identity & Compliance**
    - **Management & Governance**
    - **Cost Management**

### 🟠 Storage service category

- **Amazon S3** → object storage, scalable, secure, used for web apps, backup, IoT, analytics.
- **Amazon EBS** → block storage for EC2, high performance, used for DBs, analytics, containers.
- **Amazon EFS** → managed NFS file system, scales to petabytes, grows/shrinks automatically.
- **Amazon S3 Glacier** → low-cost archival storage, 11 9s durability, compliance.

### 🟠 Compute service category

- **Amazon EC2** → resizable compute capacity (VMs).
- **EC2 Auto Scaling** → adjust instances based on conditions.
- **Amazon ECS** → container orchestration for Docker.
- **Amazon ECR** → container registry for Docker images.
- **Elastic Beanstalk** → simple web app deployment.
- **AWS Lambda** → run code without servers (serverless), pay per execution.
- **Amazon EKS** → managed Kubernetes service.
- **AWS Fargate** → run containers without managing servers/clusters.

### 🟠 Database service category

- **Amazon RDS** → managed relational DB, automates provisioning, patching, backups.
- **Amazon Aurora** → MySQL/PostgreSQL-compatible, 3–5x faster than standard DBs.
- **Amazon Redshift** → petabyte-scale data warehouse, queries on Redshift + S3.
- **Amazon DynamoDB** → key-value/document NoSQL DB, millisecond latency, built-in security.

### 🟠 Networking and content delivery service category

- **Amazon VPC** → isolated networks in the AWS Cloud.
- **Elastic Load Balancing (ELB)** → distributes traffic across multiple resources.
- **Amazon CloudFront** → global CDN, low latency content delivery.
- **AWS Transit Gateway** → connect VPCs and on-prem networks to one gateway.
- **Amazon Route 53** → scalable DNS service, routes domains to apps.
- **AWS Direct Connect** → dedicated private connection to AWS.
- **AWS VPN** → secure tunnels to AWS.

### 🟠 Security, identity and compliance service category

- **IAM** → manage users, groups, permissions.
- **AWS Organizations** → multi-account management with SCPs.
- **Amazon Cognito** → user authentication and access for apps.
- **AWS Artifact** → compliance/security reports and agreements.
- **AWS KMS** → encryption key management.
- **AWS Shield** → managed DDoS protection.

### 🟠 AWS cost management service category

- **AWS Cost and Usage Report** → detailed billing and usage.
- **AWS Budgets** → alerts when forecasted/actual usage exceeds budget.
- **AWS Cost Explorer** → visualize and analyze costs.

### 🟠 Management and governance service category

- **AWS Management Console** → web-based management interface.
- **AWS Config** → track resource inventory and changes.
- **Amazon CloudWatch** → monitor resources and apps.
- **AWS Auto Scaling** → scale multiple resources dynamically.
- **AWS CLI** → unified command-line management tool.
- **AWS Trusted Advisor** → optimization insights (cost, performance, security).
- **AWS Well-Architected Tool** → review workloads against best practices.
- **AWS CloudTrail** → track API calls and user activity.
