# 🛡️ Module 4 - AWS Cloud Security  

## 1️⃣ Section 1: AWS Shared Responsibility Model

### 🟠 AWS Shared Responsibility Model

**Security and compliance** are a **shared responsibility** between **AWS** and the **customer**.  
This model is designed to **reduce the customer’s operational burden** while maintaining **flexibility and control** for deploying solutions on AWS.

The distinction between responsibilities is often referred to as:  
- 🔸 **Security “of” the cloud** → AWS responsibility.  
- 🔸 **Security “in” the cloud** → Customer responsibility.

AWS operates, manages, and controls components from the **virtualization layer down to the physical security** of the facilities where AWS services run.  
AWS is responsible for protecting the **infrastructure** (hardware, software, networking, and facilities) that powers the AWS Cloud.

The **customer**, on the other hand, is responsible for:  
- 🔐 **Encrypting data** at rest and in transit.  
- 🧱 Ensuring **secure network configurations**.  
- 👥 Managing **security credentials** and **user access**.  
- ⚙️ Maintaining and updating **operating systems** and **security groups** for any compute instances they launch.

---

### 🟠 AWS Responsibility: Security of the Cloud

**AWS is responsible for security *of* the cloud.**  
This includes managing and controlling infrastructure components from the **bare metal host operating system** and **hypervisor** down to **physical data center security**.

AWS protects the **global infrastructure** that runs all AWS services — including Regions, Availability Zones, and edge locations.

**AWS responsibilities include:**  

- 🏢 **Physical Security**
  - Data centers with **restricted access**, located in **nondescript facilities**.  
  - 24/7 security guards, **two-factor authentication**, access logging, **video surveillance**, and **secure media destruction (degaussing, shredding)**.

- 🖥️ **Hardware Infrastructure**
  - Servers, storage devices, and networking equipment that power the cloud.

- 💽 **Software Infrastructure**
  - Operating systems, service applications, and **virtualization software**.

- 🌐 **Network Infrastructure**
  - Routers, switches, firewalls, cabling, and redundant connections.  
  - AWS continuously monitors **network boundaries**, secures **access points**, and provides **intrusion detection and redundancy**.

🔎 AWS provides **third-party audit reports** (from independent auditors) that verify compliance with global **security standards and regulations**.  
Although customers cannot physically visit data centers, AWS ensures transparency through these reports.

---

### 🟠 Customer Responsibility: Security in the Cloud

While AWS manages the underlying infrastructure, **customers are responsible for securing everything they deploy or connect** within the AWS Cloud.

**Customer responsibilities include:**  
- Selecting and securing **operating systems** on EC2 instances.  
- Securing **applications** hosted on AWS resources.  
- Configuring **security groups**, **firewalls**, and **networks**.  
- Managing **user access and credentials** securely.  
- Implementing **encryption** for data at rest and in transit.  

Customers maintain **full control** over their content, including:  
- 📦 What data they choose to store on AWS.  
- 🧰 Which AWS services are used with that data.  
- 🌍 Where (in which Region) that data is stored.  
- 🧩 How the data is structured, masked, anonymized, or encrypted.  
- 👥 Who has access, and how those access rights are **granted, managed, and revoked**.

Customers retain responsibility for the **security of their own environment**, including applications, IAM configurations, and operating systems.

---

### 🟠 Service Characteristics and Security Responsibility

AWS offers multiple service models — **IaaS, PaaS, and SaaS** — each with different levels of shared responsibility.

| Service Model | Description | Example AWS Services | Customer Responsibility | AWS Responsibility |
|----------------|-------------|----------------------|--------------------------|--------------------|
| **IaaS (Infrastructure as a Service)** | Provides basic building blocks like compute, storage, and networking. | Amazon EC2 | Manage OS updates, security patches, apps, and firewall configurations. | Manages the underlying infrastructure (hardware, networking, virtualization). |
| **PaaS (Platform as a Service)** | Removes the need to manage hardware or OS. Focus is on deploying apps. | AWS Lambda, Amazon RDS | Manage data, classify assets, set permissions. | Handles OS and database patching, firewall setup, disaster recovery. |
| **SaaS (Software as a Service)** | Centrally hosted software accessed via web, API, or mobile. | AWS Trusted Advisor, AWS Shield, Amazon Chime | Use the service securely; no infrastructure management required. | Manages everything (infrastructure, platform, and application). |

---

### 🟠 Examples of SaaS Services

- **AWS Trusted Advisor** → Analyzes your AWS environment and provides **real-time recommendations** for best practices.  
  - Available to all accounts (with some advanced checks limited to Business or Enterprise Support plans).  

- **AWS Shield** → A **managed DDoS protection service** that automatically detects and mitigates attacks.  
  - AWS Shield Advanced offers **enhanced protections** and access to the **AWS DDoS Response Team**.  

- **Amazon Chime** → A communication service that allows you to **meet, chat, and call** within and outside your organization.  
  - Pay-as-you-go model, with no upfront fees or contracts.

---

### 🧾 Key Takeaways

✅ AWS and customers **share responsibility for security**.  
✅ **AWS** is responsible for **security *of* the cloud** — infrastructure, hardware, software, networking, and facilities.  
✅ **Customers** are responsible for **security *in* the cloud** — data, configurations, access management, and applications.  
✅ For **IaaS**, customers manage OS updates, patches, and firewalls.  
✅ For **PaaS**, AWS handles most of the infrastructure and OS security.  
✅ For **SaaS**, AWS manages the entire stack, and customers simply use the service securely.  
✅ In **IaaS**, customers have **more control and responsibility**.  
✅ In **PaaS** and **SaaS**, AWS assumes **greater security responsibilities**.

---

## 2️⃣ Section 2: AWS Identity and Access Management (IAM)

### 🟠 AWS Identity and Access Management Overview

**AWS Identity and Access Management (IAM)** enables you to control access to AWS compute, storage, database, and application services.  
It handles both **authentication** (who can sign in) and **authorization** (what actions they can perform).

IAM is a **centralized access management tool** that lets you define permissions to launch, configure, manage, and terminate resources in your AWS account.  
It provides **granular control** over resources — you can specify exactly which API calls users are authorized to make to each service.

Whether you use the **AWS Management Console**, the **AWS CLI**, or **SDKs**, every call to an AWS service is an **API call** authenticated through IAM.  
IAM allows you to manage **who can access what resources** and **how** they can access them.

You can assign different permission levels:  
- 👩‍💻 Some users may have **full administrative access**.  
- 👀 Others may have **read-only access** to limited resources (e.g., specific S3 buckets).  
- 💼 Some may have access only to **billing information** or account details.

IAM is a **feature of every AWS account** and is **free of charge**.

---

### 🟠 Essential IAM Components

To understand IAM, you must know its four key components:

| 🧱 Component | 🔍 Description |
|--------------|----------------|
| **IAM User** | Represents a person or application that interacts with AWS. Each has a **unique name** and **credentials** (passwords or keys). |
| **IAM Group** | A **collection of IAM users**. Helps manage permissions by assigning policies to groups instead of individuals. |
| **IAM Policy** | A **JSON document** that defines permissions. Specifies which actions are allowed or denied on which AWS resources. |
| **IAM Role** | Grants **temporary access** to AWS resources. Roles are not tied to a specific user and can be assumed by anyone authorized to do so. |

---

### 🟠 Authentication and Access Types

Authentication ensures that only verified users or systems can access AWS.  

When defining an **IAM user**, you can choose between two types of access:  

1. 🔹 **Programmatic access**  
   - Uses the **AWS CLI**, **SDKs**, or **APIs**.  
   - Requires an **Access Key ID** and a **Secret Access Key**.  

2. 🔹 **AWS Management Console access**  
   - Allows sign-in via a **web interface** with a username and password.  
   - Users must enter their **12-digit account ID or alias**.  
   - If **Multi-Factor Authentication (MFA)** is enabled, an **extra authentication code** is required.  

You can grant **one**, **both**, or **neither** access type depending on user needs.

---

### 🟠 Multi-Factor Authentication (MFA)

🔐 MFA adds an **extra layer of protection** by requiring a secondary authentication token in addition to a password.  

**Available MFA options:**  
- 📱 Virtual MFA apps — *Google Authenticator*, *Authy*, etc.  
- 🔑 U2F hardware security keys.  
- 💻 Physical MFA devices (key fobs, display cards).  

MFA is **strongly recommended** for all users — especially **root** and **administrative accounts**.

---

### 🟠 Authorization: What Actions Are Permitted

Authorization defines **what users, services, or applications can do** once authenticated.  

- By default, all IAM users have **no permissions**.  
- Access must be explicitly granted using **IAM policies** written in **JSON**.  
- Each policy lists allowed or denied actions for specified AWS resources.  

---

### 🟠 IAM Authorization Logic

When creating IAM policies, keep these principles in mind:  

- ❌ **No default permissions** — everything is denied unless explicitly allowed.  
- 🚫 **Explicit deny** always overrides any allow.  
- ✅ Follow the **Principle of Least Privilege** — grant only the permissions users need to perform their tasks.  
- 🌎 IAM settings are **global**, not regional (they apply across all Regions).  

---

### 🟠 IAM Policies

An **IAM policy** defines a set of permissions that can be attached to **users, groups, roles, or resources**.

**Policies specify:**  
- The **actions** users can perform.  
- The **resources** they can access.  
- The **conditions** under which access is granted or denied.  

**Policy Evaluation Rules:**  
- All relevant policies are evaluated together.  
- The **most restrictive rule** applies in case of conflict.  

**Types of IAM Policies:**  
- 🧩 **Identity-based policies**  
  - Attached to users, groups, or roles.  
  - Can be:  
    - **Managed policies** (reusable and standalone).  
    - **Inline policies** (embedded directly in one entity).  

- 🗂️ **Resource-based policies**  
  - Attached directly to an AWS resource (e.g., S3 bucket policies).  
  - Define who can access the resource and under what conditions.

---

### 🟠 Example: IAM Policy Document

IAM policies are written in **JSON** format.  

An example policy might:  
- Allow access only to a **specific DynamoDB table** and an **S3 bucket**.  
- Include an `"Effect": "Deny"` statement to block any other actions or resources.  
- Use `"NotResource"` to prevent use of other services, even if granted elsewhere.  

➡️ Remember: **Explicit Deny** overrides all other permissions.

---

### 🟠 Resource-Based Policies

While identity-based policies are linked to IAM users or groups, **resource-based policies** are attached directly to a resource (for example, an S3 bucket).  

To create one in AWS Management Console:  
1. Go to the **resource (e.g., S3 bucket)**.  
2. Open the **Permissions** tab.  
3. Click **Bucket Policy**, and define the **JSON-formatted policy**.  

**Example Scenario:**  
- The user *MaryMajor* can access the S3 bucket **photos** either by:  
  - An **identity-based policy** attached to her user.  
  - A **resource-based policy** on the bucket granting her access.  

If a **Deny** statement exists in the bucket policy, it **overrides any Allow** in identity-based policies.

---

### 🟠 IAM Permission Evaluation Process

When IAM evaluates permissions, it follows this order:  

1. 🔍 Check for any **explicit Deny**.  
2. ✅ If no Deny, check for **explicit Allow**.  
3. 🚫 If neither exists, the default is **Implicit Deny**.  

This ensures fine-grained and secure access control for every AWS identity.

---

### 🟠 IAM Groups

IAM Groups simplify permission management for multiple users.  

**Example:**  
Create a group called `Developers`, attach the required policies, and then add users.  
All users in that group automatically inherit the group’s permissions.

**Key characteristics:**  
- 👥 A group can contain **many users**.  
- 🔄 A user can belong to **multiple groups**.  
- 🧱 Groups **cannot be nested** (no group inside another group).  
- 🚫 There is **no default group** — all must be created manually.  

---

### 🟠 IAM Roles

An **IAM Role** is similar to a user but not tied to a specific person.  
It is designed to be **assumed temporarily** by whoever needs it.  

**Roles provide temporary security credentials** and are commonly used for:  
- 🤝 **Cross-account access** (between AWS accounts).  
- 📱 **Applications** that require temporary AWS access (without embedding credentials).  
- 🧑‍💻 **Delegating access** to third-party auditors or AWS services.  
- 🧩 **Federated access** — users authenticated through corporate directories (e.g., Active Directory).  

Roles are fundamental to building **secure, scalable, and compliant** AWS environments.

---

### 🧾 Key Takeaways

✅ IAM policies are written in **JSON** and define permissions precisely.  
✅ Policies can be attached to **users, groups, or roles**.  
✅ **IAM entities** include **users**, **groups**, and **roles**.  
✅ An **IAM user** represents a person or application with credentials.  
✅ An **IAM group** simplifies permission assignment to multiple users.  
✅ An **IAM role** provides **temporary, delegated access** to AWS resources.  

---



## 3️⃣ Section 3: Securing a New AWS Account

### 🟠 AWS Account Root User Access vs. IAM Access

When you first create an **AWS account**, you begin with a **single sign-in identity** that has complete access to all AWS services and resources in the account.  
This identity is called the **AWS account root user**, and it is accessed by signing in to the AWS Management Console using the **email address and password** you used when creating the account.

- The **root user** has and retains **full access** to all resources in the account.  
- Therefore, **AWS strongly recommends** that you **do not use root user credentials** for daily operations.

Instead, AWS recommends using **IAM** to create additional users and assign permissions following the **principle of least privilege**.  
For example:
- If you require administrator-level permissions, create an IAM user and grant full access to that user.  
- Later, you can modify or revoke those permissions by changing associated IAM policies.

If multiple users need access to the account:
- Create **unique credentials** for each user.  
- Define which resources each user can access.  
- Avoid **sharing the same credentials** among multiple users.

⚠️ Some specific administrative tasks can **only be performed by the root user**.  
You can find a full list of such tasks here:  
🔗 [Tasks that require root user credentials](https://docs.aws.amazon.com/general/latest/gr/root-vs-iam.html#aws_tasks-that-require-root).

---

### 🟠 Securing a New AWS Account: Account Root User

To stop using the **account root user** for daily operations, follow these steps:

1. **Create an IAM user for yourself**
   - While logged in as the root user, create a new IAM user with **AWS Management Console access** enabled.  
   - Do **not** attach permissions yet. Save the IAM user’s access keys if needed.
2. **Create an IAM group**
   - Give the group a descriptive name (for example, `FullAccess`).  
   - Attach IAM policies that grant full access to essential AWS services.  
   - Add your newly created IAM user to this group.
3. **Disable and remove root access keys**
   - If your root user has access keys, delete them immediately.
4. **Enable a password policy**
   - Apply a strong password policy for all IAM users.  
   - Copy the IAM user sign-in link from the IAM dashboard.
5. **Sign out as the root user**
   - Use the sign-in link to log in as your IAM user instead.
6. **Store root credentials securely**
   - Keep them in a **safe and restricted location**.

📘 For detailed steps, see the AWS guide:  
🔗 [Creating Your First IAM Admin User and Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html).

---

### 🟠 Securing a New AWS Account: MFA (Multi-Factor Authentication)

To enhance security, **enable MFA** for both the **root user** and **all IAM users**.

- MFA requires users to provide a **second form of authentication** (in addition to their password).  
- This protects against unauthorized access, even if passwords are compromised.

You can also enable MFA to secure **programmatic access** to AWS APIs.  
For configuration details, see:  
🔗 [Configuring MFA-Protected API Access](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_configure-api-require.html)

**MFA device options include:**
- 📱 Virtual MFA apps (e.g., *Google Authenticator*, *Authy*)
- 🔑 U2F security key devices
- 💻 Hardware MFA devices (key fobs or display cards)

---

### 🟠 Securing a New AWS Account: AWS CloudTrail

**AWS CloudTrail** is a service that records all **API requests** made to resources in your account, providing **operational auditing** and **security visibility**.

- CloudTrail is **enabled by default** for all AWS accounts.  
- It retains a record of the **last 90 days** of management event activity.  
- You can view or download these logs for **create**, **modify**, and **delete** operations.

You can extend log retention and enable event alerts by creating a **trail**.  
This allows you to:
- Store CloudTrail logs for **longer periods**.  
- Send notifications when **specific events occur**.  

📘 For detailed guidance, see:  
🔗 [Creating a Trail Using the Console (AWS Documentation)](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-a-trail-using-the-console-first-time.html)

You can also review the list of supported services here:  
🔗 [CloudTrail Service-Specific Topics](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-aws-service-specific-topics.html)

---

### 🟠 Securing a New AWS Account: Billing Reports

Another best practice for securing and managing your AWS account is to **enable billing reports**, such as the **AWS Cost and Usage Report**.

- These reports provide detailed insights into **resource usage** and **estimated costs**.  
- AWS delivers them automatically to an **Amazon S3 bucket** of your choice.  
- Reports are updated **at least once per day**.

The AWS Cost and Usage Report tracks:
- Hourly and daily usage by service.  
- Estimated charges for each AWS service.  

📘 Learn more here:  
🔗 [Creating an AWS Cost and Usage Report](https://docs.aws.amazon.com/cur/latest/userguide/cur-create.html)

---

### 🧾 Key Takeaways

✅ Enable **Multi-Factor Authentication (MFA)** for all users (including root).  
✅ **Delete root user access keys**.  
✅ Create **individual IAM users** and grant permissions following the **Principle of Least Privilege**.  
✅ Use **groups** to assign permissions efficiently.  
✅ Enforce a **strong password policy**.  
✅ Delegate permissions using **roles** instead of sharing credentials.  
✅ Monitor all account activity using **AWS CloudTrail**.

---

## 4️⃣ Section 4: Securing Accounts

### 🟠 AWS Organizations

**AWS Organizations** is an account management service that enables you to consolidate multiple AWS accounts into a single **organization** that you create and centrally manage.

This section focuses on the **security features** provided by AWS Organizations.

**Key security capabilities include:**

- 🧱 **Grouping accounts** into *Organizational Units (OUs)* and attaching **different access policies** to each OU.  
  Example: If you have accounts that should only access AWS services that meet certain **regulatory requirements**, you can group them into one OU and attach a policy that **blocks access** to non-compliant services.

- 🔐 **Integration with AWS Identity and Access Management (IAM)**:  
  AWS Organizations extends IAM control to the account level, allowing you to define what **users and roles** in an account (or group of accounts) can do.

- ⚙️ **Permission intersection**:  
  Effective permissions are determined by the intersection between:
  - The **AWS Organizations policy settings** (e.g., Service Control Policies), and  
  - The **IAM policies** applied within the account.  
  A user can access only what is allowed by **both** policy types.

- 🛡️ **Service Control Policies (SCPs)**:  
  These define the **maximum permissions** that member accounts in the organization can have.  
  SCPs can **restrict access** to specific AWS services, resources, or API actions.  
  Even administrators in member accounts cannot override these restrictions.

When AWS Organizations blocks access to a service, resource, or API action, **no user or role** in that account can access it — even if an admin explicitly grants permission.

---

### 🟠 AWS Organizations: Service Control Policies (SCPs)

SCPs provide **centralized control** over the maximum available permissions for all accounts within an organization.  
They ensure that every account operates within the organization’s access control boundaries.

**Key details:**

- SCPs are available **only when all features are enabled**, including **consolidated billing**.  
  📘 Learn more: [Enable All Features in AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_org_support-all-features.html)

- SCPs are **not available** if the organization uses only consolidated billing features.

- For instructions on enabling and managing SCPs, see:  
  [Enabling and Disabling a Policy Type on a Root](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies.html#enable_policies_on_root.SCPs)

**Comparison to IAM Policies:**

| Feature | Service Control Policy (SCP) | IAM Policy |
|----------|------------------------------|-------------|
| Purpose | Defines **maximum permissions** within an organization | Grants or denies permissions to specific identities |
| Syntax | JSON (similar to IAM policies) | JSON |
| Scope | Organization, Root, or OU level | Account or Resource level |
| Grants permissions? | ❌ No (it only limits) | ✅ Yes |

**Important notes:**
- Attaching an SCP to the **organization root** or an **OU** sets a **boundary** for what member accounts can do.  
- SCPs **do not replace IAM** — you still need to attach IAM policies to actually grant access.

Learn more about IAM policies:  
📘 [AWS IAM Policies Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

---

### 🟠 AWS Key Management Service (AWS KMS)

**AWS Key Management Service (AWS KMS)** enables you to **create, manage, and control encryption keys** used across AWS services and applications.

**Key characteristics:**

- 🧩 Uses **Hardware Security Modules (HSMs)** that are validated (or in the process of validation) under **Federal Information Processing Standards (FIPS) 140-2**.  
- 🔐 Provides **secure and resilient** key management infrastructure.  
- 🧾 Integrates with **AWS CloudTrail** to log all key usage for compliance and auditing.  
- 🪪 Manages **Customer Master Keys (CMKs)** that control access to **Data Encryption Keys (DEKs)**.  
- 🔄 You can **create, import, or rotate keys** as needed.  
- 🌐 Integrates with most AWS services (e.g., S3, EBS, RDS, Lambda) to manage encryption.

**Learn more:**  
📘 [AWS Key Management Service Features](https://aws.amazon.com/kms/features/)

---

### 🟠 Amazon Cognito

**Amazon Cognito** provides secure solutions for **user authentication and access control** within your applications.

**Core functionalities:**

- 🧍‍♂️ **Role-based access**: You can define roles and map users to roles, ensuring that applications access only authorized AWS resources.  
- 🌍 **Support for SAML 2.0 (Security Assertion Markup Language)**:  
  Cognito uses SAML — an open standard for exchanging **identity and security information** between identity providers and applications.  
  - Supports **Single Sign-On (SSO)** using corporate credentials (e.g., from Microsoft Active Directory).  
  - Enables seamless authentication across multiple applications.

**Compliance and Regulatory Support:**

Amazon Cognito helps organizations meet multiple **security and compliance requirements**, including those for **highly regulated industries** such as healthcare and finance.

**Compliance frameworks supported:**  
- 🏥 **HIPAA** – [AWS HIPAA Compliance](https://aws.amazon.com/compliance/hipaa-compliance/)  
- 💳 **PCI DSS** – [AWS PCI DSS FAQs](https://aws.amazon.com/compliance/pci-dss-level-1-faqs/)  
- 🧾 **AICPA SOC** – [AWS SOC FAQs](https://aws.amazon.com/compliance/soc-faqs/)  
- 🌐 **ISO/IEC Standards**:  
  - [ISO/IEC 27001](https://aws.amazon.com/compliance/iso-27001-faqs/)  
  - [ISO/IEC 27017](https://aws.amazon.com/compliance/iso-27017-faqs/)  
  - [ISO/IEC 27018](https://aws.amazon.com/compliance/iso-27018-faqs/)  
  - [ISO 9001](https://aws.amazon.com/compliance/iso-9001-faqs/)

By using Amazon Cognito, you can manage users securely while complying with key **international standards**.

---

### 🟠 AWS Shield

**AWS Shield** is a **managed Distributed Denial of Service (DDoS) protection** service designed to protect applications running on AWS.

**Key capabilities:**

- 🧠 Provides **always-on detection** and **automatic inline mitigations** to minimize downtime and latency.  
- 🛡️ Protects against multiple attack types, including:
  - **Infrastructure-layer attacks** (e.g., UDP floods)  
  - **State exhaustion attacks** (e.g., TCP SYN floods)  
  - **Application-layer attacks** (e.g., HTTP GET/POST floods)  

📘 For examples, refer to the [AWS WAF Developer Guide](https://docs.aws.amazon.com/waf/latest/developerguide/waf-chapter.html).

**AWS Shield Service Tiers:**

| Tier | Description | Cost |
|------|--------------|------|
| **AWS Shield Standard** | Enabled by default for all AWS customers. Provides baseline DDoS protection. | Free |
| **AWS Shield Advanced** | Offers enhanced protection against large or sophisticated attacks. Includes 24/7 DDoS Response Team (DRT) support. | Paid service (requires Enterprise or Business Support) |

**AWS Shield Advanced** extends protection to:  
- Amazon EC2  
- Elastic Load Balancing (ELB)  
- Amazon CloudFront  
- AWS Global Accelerator  
- Amazon Route 53

---

### 🧾 Key Takeaways

✅ **AWS Organizations** allows central management and security control across multiple accounts.  
✅ **Service Control Policies (SCPs)** define the **maximum permissions** available within the organization.  
✅ **AWS KMS** manages encryption keys securely using FIPS-compliant HSMs.  
✅ **Amazon Cognito** provides secure, standards-based authentication and supports regulatory compliance (HIPAA, PCI DSS, ISO, etc.).  
✅ **AWS Shield** offers managed DDoS protection — both free (Standard) and advanced (paid) tiers.  

---

## 5️⃣ Section 5: Securing Data on AWS

### 🟠 Encryption of Data at Rest

**Data encryption** is an essential tool for protecting digital information.  
It converts readable data into an unreadable format using a **secret key**.  
Even if an attacker gains access to the data, they cannot interpret it without the key.

**Data at rest** refers to information **physically stored** on disk or tape.  

AWS allows you to create **encrypted file systems** so that all data and metadata are automatically encrypted using the **Advanced Encryption Standard (AES)-256** algorithm.

When using **AWS Key Management Service (KMS)**, encryption and decryption are handled **automatically and transparently**, meaning you don’t need to modify your applications.

If your organization is subject to **corporate or regulatory policies** that require encryption, AWS recommends enabling encryption on **all services** that store data.

🔗 See supported services: [How AWS Services Use AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/service-integration.html)

---

### 🟠 Encryption of Data in Transit

**Data in transit** refers to data **moving across networks**.  
It is protected using **Transport Layer Security (TLS) 1.2** with **AES-256 encryption**.  
TLS was formerly known as **Secure Sockets Layer (SSL)**.

**AWS Certificate Manager (ACM)** allows you to provision, manage, and deploy **SSL/TLS certificates** to secure network communications and verify the identity of websites and resources.

**Key points:**

- HTTPS (TLS/SSL) protects traffic from **eavesdropping** and **man-in-the-middle attacks**.  
- AWS Certificate Manager also **handles certificate renewals automatically**.  
- HTTP traffic is not secure; always use **HTTPS** instead.

**Examples of encryption in transit:**

1. 🧩 An **EC2 instance** mounting an **Amazon EFS shared file system** — all data traffic is encrypted using TLS/SSL.  
   📘 Learn more: [Encryption of EFS Data in Transit](https://docs.aws.amazon.com/whitepapers/latest/efs-encrypted-file-systems/encryption-of-data-in-transit.html)

2. 🗄️ **AWS Storage Gateway** connecting on-premises infrastructure to **Amazon S3** — data is encrypted while traveling over the Internet.

---

### 🟠 Securing Amazon S3 Buckets and Objects

By default, **Amazon S3 buckets are private** and accessible only to users who are explicitly granted access.

**Best Practices for S3 Security:**

- 🚫 **Enable Amazon S3 Block Public Access**  
  - Overrides all other permissions or bucket policies.  
  - Prevents accidental public exposure of S3 data.

- 🧾 **Use IAM policies**  
  - Define which users or roles can access specific buckets and objects.

- 📜 **Use Bucket Policies**  
  - Define access permissions directly on the bucket.  
  - Useful when IAM authentication is not available.  
  - Bucket policies can grant **cross-account access** or **public access**, but must be written carefully.

- ❌ **Use Access Control Lists (ACLs)** only when necessary  
  - ACLs are an older access mechanism that predates IAM.  
  - Avoid overly permissive ACLs.

- 🔍 **Use AWS Trusted Advisor**  
  - Check for bucket permissions that may allow **global access**.

---

## 6️⃣ Section 6: Working to Ensure Compliance

### 🟠 AWS Compliance Programs

AWS works with **external certifying bodies** and **independent auditors** to provide customers with transparency into the **security policies, processes, and controls** implemented by AWS.

A full list of compliance programs is available here:  
🔗 [AWS Compliance Programs](https://aws.amazon.com/compliance/programs/)

For details on which AWS services are covered under specific compliance frameworks, visit:  
🔗 [AWS Services in Scope by Compliance Program](https://aws.amazon.com/compliance/services-in-scope/)

**Example: ISO/IEC 27001:2013 Certification**  
This certification defines requirements for establishing, maintaining, and improving an **Information Security Management System (ISMS)**.  
It demonstrates that AWS manages security in a **comprehensive and continuous** way.

AWS also supports customers in meeting **common regulations and legal requirements**, such as:

- 🏥 **Health Insurance Portability and Accountability Act (HIPAA)** – for healthcare data protection  
- 🇪🇺 **General Data Protection Regulation (GDPR)** – protects EU citizens’ privacy and data  
  📘 [AWS GDPR Center](https://aws.amazon.com/compliance/gdpr-center/)  
- 💳 **Payment Card Industry Data Security Standard (PCI DSS)** – for payment data protection  

---

### 🟠 AWS Config

**AWS Config** enables you to **assess, audit, and evaluate** the configurations of your AWS resources.  
It continuously monitors and records resource configurations and automatically evaluates them against predefined compliance rules.

**Capabilities:**

- 📋 Tracks changes and relationships between resources.  
- 🧾 Provides a detailed **configuration history** for auditing.  
- ⚙️ Detects and flags **non-compliant resources**.  
- 🌍 Operates as a **Regional service**, but can **aggregate results across Regions or accounts** for unified visibility.

**Benefits:**  
- Simplifies **compliance auditing**, **security analysis**, **change management**, and **operational troubleshooting**.  

---

### 🟠 AWS Artifact

**AWS Artifact** provides **on-demand access** to AWS **security and compliance documentation**, such as:  
- ISO certifications  
- PCI reports  
- Service Organization Control (SOC) reports  

**Key uses:**

- Submit compliance documents to **auditors or regulators** to demonstrate AWS security posture.  
- Use reports to **evaluate your own cloud architecture** and **internal controls**.  
- Manage **agreements and compliance documents** (e.g., Business Associate Agreement for HIPAA).

**Features:**

- AWS Artifact only provides documents about **AWS itself**.  
- Customers are responsible for their **own organization’s compliance**.  
- You can **review, accept, and track agreements** (such as HIPAA BAA) directly in Artifact.  
- Agreements can apply to **multiple AWS accounts** via **AWS Organizations**.

📘 Learn more: [Managing Agreements in AWS Artifact](https://docs.aws.amazon.com/artifact/latest/ug/managing-agreements.html)

---

### 🧾 Key Takeaways

✅ **AWS Compliance Programs** provide transparency into AWS security controls and certifications.  
✅ **AWS Config** continuously monitors configurations for compliance and security issues.  
✅ **AWS Artifact** offers access to official AWS compliance and audit reports for internal and external use.  

---