# 📊 Module 2 - Cloud Economics and Billing

## 1️⃣ Section 1: Fundamentals of pricing

### 🟠 AWS pricing model

The **three main cost drivers** in AWS are:

- **Compute** → charged per hour/second, varies by instance type.
- **Storage** → typically charged per GB.
- **Data transfer** → outbound is charged (aggregated across services), inbound is usually free within the same region (exceptions exist).

👉 Outbound data transfer charges appear on the bill as **Data Transfer Out**.

### 🟠 How do you pay for AWS?

At the end of each month, you pay for what you use. You can start or stop using a product at any time. No long-term contracts are required.

AWS follows a **utility-style model**: you pay only for what you use, with no long-term contracts.

Key principles:

1. **Pay for what you use** – no upfront infrastructure costs.
2. **Pay less when you reserve** – discounts with Reserved Instances (EC2, RDS).
3. **Pay less by using more** – tiered pricing with volume discounts (e.g., Amazon S3).
4. **Pay even less as AWS grows** – AWS continuously lowers costs as it scales.

### 🟠 Pay for what you use

With AWS, you pay only for the services that you consume with no large upfront expenses.

You can lower variable costs, so you no longer need to dedicate valuable resources to building costly infrastructure, including purchasing servers, software licenses, or leasing facilities.

Quickly adapt to changing business needs and redirect your focus on innovation and invention by paying only for what you use and for as long as you need it.

All AWS services are available on demand, require no long-term contracts, and have no complex licensing dependencies

### 🟠 Pay less when you reserve

For certain services like Amazon Elastic Compute Cloud (Amazon EC2) and Amazon Relational Database Service (Amazon RDS), you can invest in reserved capacity.

With Reserved Instances, you can save up to 75 percent over equivalent on-demand capacity.

Reserved Instances are available in **three options**:

- **All Upfront Reserved Instance (AURI)** → highest discount
- **Partial Upfront Reserved Instance (PURI**) → smaller upfront payment, medium discount
- **No Upfront Payments Reserved Instance (NURI**) → no initial payment, lowest discount

When you buy Reserved Instances, you receive a greater discount when you make a larger upfront payment. To maximize your savings, you can pay all upfront and receive the largest discount. Partial Upfront RIs offer lower discounts, but they give you the option to spend less upfront.

Lastly, you can choose to spend nothing upfront and receive a smaller discount, which enables you to free capital to spend on other projects.

By using reserved capacity, your organization can minimize risks, more predictably manage budgets, and comply with policies that require longer-term commitments.

### 🟠 Pay less by using more

For services like **Amazon Simple StorageService (Amazon S3)**, pricing is tiered, which means that you pay less per GB when you use more.

In addition, data transfer inis always free.

Multiple storage services deliver lower storage costs based on your needs.

As a result, as your AWS usage needs increase, you benefit from the economies of scale that enable you to increase adoption and keep costs under control.

### 🟠 Pay even less as AWS grows

As AWS grows:

- AWS focuses on lowering cost of doing business
- This practice results in AWS passing savings from economies of scale to you.
- Since 2006, AWS has reduced prices over **75 times**.
- Newer, higher-performing resources often replace older ones **at no extra cost**.

### 🟠 Custom pricing

• For high-volume or unique projects, AWS provides **custom pricing agreements**.

### 🟠 AWS Free Tier

- New customers get **12 months of free usage** for selected services (e.g., EC2 t2.micro, S3, EBS, Load Balancer, data transfer).
- Designed to let users explore AWS at no initial cost.

### 🟠 Services with no charge

Some services are included at **no additional cost**, such as:

- **Amazon Virtual Private Cloud (Amazon VPC)** → enables you to provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.
- **AWS Identity and Access Management (IAM)** → controls your users’ access to AWS services and resources.
- **Consolidated Billing** → is a billing feature in AWS Organizations to consolidate payment for multiple AWS accounts or multiple Amazon Internet Services Private Limited (AISPL) accounts*. Consolidated billing provides:•One bill for multiple accounts.
- The ability to **easily track each account’s charges**.
- The opportunity **to decrease charges as a result of volume pricing discounts** from combined usage.
- **Consolidate all of your accounts using Consolidated Billing and get tiered benefits.**
- **AWS Elastic Beanstalk** → is an even easier way for you to quickly deploy and manage applications in the AWS Cloud.
- **AWS CloudFormation** → gives developers and systems administrators an easy way to create a collection of related AWS resources and provision them in an orderly and predictable fashion.
- **Automatic Scalingautomatically** → adds or removes resources according to conditions you define. The resources you are using increase seamlessly during demand spikes to maintain performance and decrease automatically during demand lulls to minimize costs.
- **AWS OpsWorks** → is an application management service that makes it easy to deploy and operate applications of all shapes and sizes.

**Note:** The difference between **AWS accounts** and **AISPL accounts** (India) is the seller of record. AISPL bills in INR, while AWS Inc. bills in USD.

## 2️⃣ Section 2: Total Cost of Ownership

### 🟠 On-premises vs. cloud

- **On-Premises Infrastructure**
    - Installed locally on company hardware.
    - High **capital expenses**: facilities, hardware, licenses, IT staff.
    - **Scaling up** → expensive, time-consuming.
    - **Scaling down** → fixed costs remain.
- **Cloud Infrastructure**
    - Provided and maintained by AWS.
    - Pay only for what you use (**consumption-based model**).
    - Easy to scale up or down.
    - Costs are transparent and easier to estimate.

👉 On-premises focuses on **CapEx** (capital expenditure, long planning cycles).

👉 Cloud focuses on **OpEx** (operational expenditure, agility, and flexibility).

### 🟠 What is Total cost of Ownership (TCO)?

**Total Cost of Ownership (TCO)** is a financial estimate that is intended to help buyers and owners determine the direct and indirect costs of a product or system.

TCO includes the cost of a service, plus all the costs that are associated with owning the service.

**¿Why use TCO?**

- To compare the costs of running an **entire infrastructure environment or a specific workload** on-premises versus on AWS.
- To budget and **build the business case** for moving to the cloud

In resume, it helps to decide the most cost-effective deployment model.

### 🟠 TCO considerations

Some of the costs that are associated with data center management include:

- **Server costs for both hardware and software**, and facilities costs to house the equipment.
- **Storage costs for the hardware**, administration, and facilities.
- **Network costs for hardware**, administration, and facilities.
- **IT labor costs that are required to administer the entire solution**.

When you compare an on-premises to cloud solution, it is important to accurately assess the true costs of both options.

With the cloud, most costs are upfront and readily calculated. For example, cloud providers give transparent pricing based on different usage metrics, such as RAM, storage, and bandwidth, among others. Pricing is frequently fixed per unit of time.

**Resume:**

Key cost categories for data center management:

- **Servers**: hardware, software, facilities.
- **Storage**: hardware, administration, facilities.
- **Networking**: hardware, administration, facilities.
- **IT Labor**: ongoing operations and administration.

**Cloud**:

- Costs are upfront, transparent, based on metrics (RAM, storage, bandwidth).
- Easier to calculate and predict.

**On-Premises**:

- Costs are harder to determine, must include:
    - **Direct costs**: power, space, storage, IT operations.
    - **Indirect costs**: network, storage infrastructure, security, software, facilities, taxes, upgrades, admin staff.

### 🟠 On-premises versus all-in-cloud

- **On-Premises Setup**:
    - 1 VM, 4 CPUs, 16 GB RAM, Linux.
    - 100% utilization, optimized by RAM.
    - **3-year total cost**: $167,422.
- **AWS Setup**:
    - 1 m4.xlarge instance, 4 CPUs, 16 GB RAM.
    - 3-year **Partial Upfront Reserved Instance**.
    - **3-year total cost**: $7,509.
    - **Savings**: $159,913 (96% cheaper).

👉 **On-premises →** constant costs, even when unused.

👉 **AWS →** resources only billed when used, then decommissioned.

### 🟠 AWS Pricing Calculator

**AWS Pricing Calculator** help you to estimate a monthly AWS bill. You can use this tool to explore AWS services and create an estimate for the cost of your use cases on AWS. 

The **AWS Pricing Calculator** helps you:

- Estimate monthly costs of AWS services
- Identify opportunities for cost reduction
- Model your solutions before building them
- Explore price points and calculations behind your estimate
- Find the available instance types and contract terms that meet your needs

The AWS Pricing Calculator enables you to name your estimate and create and name groups of services. Groupsare containers that you add services to in order to organize and build your estimate. You can organize your groups and services by cost-center, department, product architecture, etc.

### 🟠 Reading an estimate

AWS Pricing Calculator estimates are broken into:

- **The total for your first 12 months** → The total estimate for your current group and all of the services and groups in your current group. It combines the upfront and monthly estimates.
- **Your total upfront** → How much you are estimated to pay upfront as you set up your AWS stack.
- **Your total monthly** → How much you're estimated to spend every month while you run your AWS stack.

Within a group, you can see how much each service is estimated to cost. If you want to price out different ways to build your AWS setup, you can use different groups for each variation of your setup and compare the estimates for the different setups. 

### 🟠 Additional benefit considerations

**Hard benefits (direct, measurable):**

- Lower spending on compute, storage, networking, security.
- Reduced hardware/software purchases.
- Lower operational costs (backup, disaster recovery).
- Reduced need for operations personnel.

**Soft benefits (indirect, harder to measure):**

- Service/application reuse with cloud tools.
- Higher developer productivity.
- Improved customer satisfaction.
- Agile processes → faster response to opportunities.
- Increased global reach.

👉 A full **ROI analysis** should consider **both hard and soft benefits**.

## 3️⃣ Section 3: AWS Organizations

### 🟠 Introduction to AWS Organizations

**AWS Organizations** → account management service that enables you to consolidate multiple AWS accounts into anorganizationthat you create and centrally manage. AWS Organizations include consolidated billing and account management capabilities that help you to better meet the budgetary, security, and compliance needs of your business.

**Key benefits**:

- Centrally managed **access policies** across multiple AWS accounts.
- **Controlled access** to AWS services.
- Automated AWS account creation and management.
- **Consolidated billing** across multiple AWS accounts.

### 🟠 AWS Organizations terminology

Hereis some terminology to understand the structure of AWS Organizations.

- **Root**: the top-level container for the organization.
- **Organizational Unit (OU)**:
    - A container for accounts within a root.
    - OUs can contain other OUs (tree-like hierarchy).
    - Policies attached to a node flow down to all children.
- **Account**: a standard AWS account holding resources.
- **Policies**:
    - Can be attached at root, OU, or account level.
    - Affect all IAM users, groups, and roles inside that account.
- Rules:
    - An OU has only one parent.
    - An account belongs to exactly one OU.

### 🟠 Key features and benefits

AWS Organizations enables you to:

- Create **Service Control Policies (SCPs)** that centrally control AWS services across multiple AWS accounts.
- Create **groups of accounts** and then attach policies to a group to ensure that the correct policies are applied across the accounts.
- Simplify **account management by using** application programming interfaces **(APIs)** to automate the creation and management of new AWS accounts.
- Simplify billing with a **single payment method** for all accounts:
    - Combined view of charges.
    - Access to **volume discounts** through aggregated usage.

With consolidated billing, you can see a combined view of charges that are incurred by all your accounts, and you can take advantage of pricing benefits from aggregated usage. Consolidated billing provides a central location to manage billing across all of your AWS accounts, and the ability to benefit from volume discounts.

### 🟠 Security with AWS Organizations

- **IAM Policies**:
    - Allow/deny access to services, resources, or API actions.
    - Apply to IAM users, groups, and roles.
    - **Cannot restrict the root user** of an account.
- **SCPs (Service Control Policies)**:
    - Apply at the **organization level** (root, OU, or account).
    - Restrict/allow services across accounts.
    - Affect **all identities** (users, groups, roles) **including root user**.

👉 IAM = access control inside an account.

👉 SCPs = broader guardrails across multiple accounts.

### 🟠 Organizations setup

Keep in mind that this process assumes that you have access to two existing AWS accounts, and that you can sign in to each account as an administrator.

Review these steps forsetting up AWS Organizations:

- **Step 1** → **Create an organization** using your main AWS account (becomes the management account). Invite or create member accounts.
- **Step 2** → create two organizational units in your new organization and place the member accounts in those OUs.
- **Step 3** → create service control policies, which enable you to apply restrictions to what actions can be delegated to users and roles in the member accounts. A service control policy is a type of organization control policy.
- **Step 4** → **Test policies** by signing in as users or using the IAM policy simulator.

### 🟠 Limits of AWS Organizations

- **Naming**: Unicode, max 250 characters.
- **Entities & limits**:
    - Accounts: varies.
    - Roots: 1.
    - OUs: up to 1,000.
    - Policies: up to 1,000.
    - Policy document size: max 5,120 bytes.
    - Max OU nesting: 5 levels.
    - Invitations per day: 20.
    - Member accounts created concurrently: 5.
    - Policies can be attached to unlimited entities.

### 🟠 Accessing AWS Organizations

You can manage Organizations through:

- **AWS Management Console** → web-based UI.
- **AWS CLI** → faster, command-line management.
- **AWS SDKs** → programmatic access with libraries for Java, Python, Ruby, .NET, iOS, Android, etc.
- **HTTPS Query API** → direct API calls (requires digitally signed requests).

## 4️⃣ Section 4: AWS Billing and Cost Management

### 🟠 Introducing AWS Billing and Cost Management

**AWS Billing and Cost Management** → service that you use to pay your AWS bill, monitor your usage, and budget your costs. Billing and Cost Management enables you to forecast and obtain a better idea of what your costs and usage might be in the future so that you can plan ahead.

**Features:**

- Custom time periods (daily or monthly view).
- Filtering and grouping of data by dimensions.
- **AWS Cost and Usage Report Tool** → detailed insights to identify optimization opportunities.

### 🟠 AWS Billing Dashboard

- Central view of AWS expenditure.
- Key graphs:
    - **Spend Summary** → past month spending, current month-to-date, forecast for this month.
    - **Month-to-Date Spend by Service** → shows top services used and their cost proportions.

### 🟠 Tools

Accessible from the billing dashboard:

- **AWS Bills**
- **AWS Cost Explorer**
- **AWS Budgets**
- **AWS Cost and Usage Reports**

### 🟠 Monthly Bills

- Provides **detailed breakdown** of costs:
    - By AWS service.
    - By AWS Region.
    - By linked account.
- Most up-to-date source for **monthly bill and usage information**.

### 🟠 Cost Explorer

The AWS Billing and Cost Management console includes the Cost Explorer page for viewing your AWS cost data as a graph.

- Tool for **visualizing and analyzing AWS cost and usage** over time.
- Default report shows **top cost-incurring services**.
- Monthly running costs → overview of last 3 months + forecast for next month (with confidence interval).

Cost Explorer enables you to:

- View charts of your costs.
- View cost data for the past 13 months.
- Forecast how much you are likely to spend over the next 3 months.
- Discover patterns in how much you spend on AWS resources over time and identify costproblem areas.
- Identify the services that you use the most
- View metrics, like which Availability Zones have the most traffic or which linked AWS account is used the most.

### 🟠 Forecast and track costs

**AWS Budgets** → uses the cost visualization that is provided by Cost Explorer to show you the status of your budgets and to provide forecasts of your estimated costs.

- Lets you:
    - Track budgets at monthly, quarterly, or yearly levels.
    - Customize start and end dates.
    - Set alerts when **actual or forecasted costs exceed budget**.
- Notifications sent via **email** or **Amazon SNS**.

### 🟠 Cost and usage reporting

The AWS Cost and Usage Report is a single location for accessing comprehensive information about your AWS costs and usage.

This tool lists the usage for each service category that is used by an account (and its users) in hourly or daily line items, and any tax that you activated for tax allocation purposes.

You can choose to have AWS to publish billing reports to an S3 bucket.

These reports can be updated once a day.

**Resume:**

- **Most comprehensive cost/usage data** in AWS.
- Provides detailed hourly/daily line items by:
    - Service category.
    - Account/user usage.
    - Tax allocations (if enabled).
- Reports can be delivered automatically to an **S3 bucket**, updated **daily**.

## 5️⃣ Section 5: Technical support

### 🟠 AWS support (1 of 2)

AWS Support can provide you with a unique combination of tools and expertise based on your current or future planned use cases

- AWS Support provides **tools + expertise** tailored to customer needs.
- Covers all types of customers:
    - Experimenting with AWS.
    - Running production workloads.
    - Using AWS for mission-critical business operations.
- Goal: enable customers to **plan, deploy, and optimize with confiden**

### 🟠 AWS support (2 of 2)

With AWS, customers can plan, deploy, and optimize with confidence.

If you would like proactive guidance, AWS Support has Technical Account Managers (TAMs)who are designated as that user’s primary point of contact. The TAM can provide guidance, architectural review, and continuous ongoing communication to keep you informed and prepared as you plan, deploy, and optimize your solutions.

If you want to ensure that you follow best practices to increase performance and fault tolerance in the AWS environment, AWS SupporthasAWS Trusted Advisor. AWS Trusted Advisor is like a customized cloud expert.It is an online resource that checks for opportunities to reduce monthly expenditures and increase productivity.

For account assistance, the Support Concierge is a billing and account expert who will provide quick and efficient analysis on billing and account issues. The concierge addresses all non-technical billing and account-level inquiries.

### 🟠 Support plans

AWS wants you to be able to plan, deploy, and optimize with confidence. We have developed specific plans to support you, including Basic, Developer, Business, and Enterprise support plans.

- **Basic Support (free)**
    - 24/7 access to customer service, docs, whitepapers, forums.
    - 6 core Trusted Advisor checks.
    - Personal Health Dashboard.
    - ❌ No technical case support.
- **Developer Support**
    - For testing/early development.
    - Technical guidance available.
    - Best for **non-production workloads**.
- **Business Support**
    - For **production workloads**.
    - Suitable for organizations using multiple key AWS services extensively.
    - Ensures workloads are **available, scalable, and secure**.
- **Enterprise Support**
    - For **mission-critical workloads**.
    - Focus on **proactive management** and best practices.
    - Includes **TAM** with deep knowledge of your use case and architecture.
    - Supports launches, migrations, and continuous optimization.

### 🟠 Case severity and response times

It addition to understanding the costs that are associated with different support plans, it is critical that you understand the service levels that are associated with each plan. In addition to the support plan you select, the case severity will drive the type of response that you receive.

There are five different severity levels:

- **Critical** → Business at risk, critical app functions unavailable.
- **Urgent** → Significant impact, important app functions unavailable.
- **High** → Important functions impaired or degraded.
- **Normal** → Non-critical functions abnormal, or time-sensitive dev question.
- **Low** → General dev question or feature request.

👉 **Basic Support Plan does not include case support**.

👉 Higher plans ensure faster response times according to severity.