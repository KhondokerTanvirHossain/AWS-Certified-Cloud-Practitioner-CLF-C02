# AWS Knowledge - CLF-C02 (Cloud Practitioner)

This document contains my AWS knowledge learned during the AWS Certified Cloud Practitioner (CLF-C02) course. It serves as a reference and a guide to various AWS services and concepts.

## Table of Contents

- [Introduction to AWS](#introduction-to-aws)
- [AWS Global Infrastructure](#aws-global-infrastructure)
- [Core AWS Services](#core-aws-services)
  - [Compute](#compute)
  - [Storage](#storage)
  - [Networking](#networking)
- [Security and Compliance](#security-and-compliance)
- [Cloud Technology and Services](#cloud-technology-and-services)
- [Billing and Pricing](#billing-and-pricing)
- [Additional Topics](#additional-topics)
- [Resources](#resources)

---

## Introduction to Cloud Computing and AWS

### What is cloud

[Cloud computing](#https://www.ibm.com/topics/cloud-computing) refers to the delivery of computing services, like storage and processing, over the internet rather than relying on local data centers. AWS provides these services through a global network of servers organized in data centers.

[Virtualization](#https://aws.amazon.com/what-is/virtualization/) is a key technology that allows AWS to divide physical servers into virtual machines (VMs). Each VM operates independently with its own resources (e.g., memory, storage) and is offered on a pay-as-you-go basis, similar to utilities like electricity.

Cloud computing enables businesses to scale without upfront infrastructure costs, with AWS offering services across various categories, such as:

    Compute (e.g., EC2)
    Storage (e.g., S3)
    Networking (e.g., VPC)
    Security (e.g., IAM)

By familiarizing yourself with these categories, you gain a better understanding of how AWS services work and can utilize them efficiently.

### Introducing Cloud Computing and Deployment Models

In this lesson, we explore the key concepts of cloud computing, comparing **CapEx** (Capital Expenditures) with **OpEx** (Operating Expenses), followed by an introduction to cloud computing models and deployment models.

### CapEx vs. OpEx

- **CapEx**: Upfront investments in fixed assets like equipment, property, and software.
- **OpEx**: Ongoing costs to support daily operations, such as salaries, rent, and utilities.

### Six Advantages of Cloud Computing

1. **Global Deployment**: Launch applications worldwide at the click of a button.
2. **Focus on Development**: AWS manages the infrastructure, allowing you to focus on building applications.
3. **Lower Costs**: AWS’s scale enables lower pay-as-you-go prices.
4. **Faster Innovation**: AWS services help speed up development and delivery.
5. **Elasticity**: Resources scale automatically with demand.
6. **Cost Efficiency**: Pay only for what you use without upfront investments.

### Benefits of Cloud Computing

- **High Availability**: Systems designed to operate continuously with minimal failures.
- **Elasticity**: Provision resources as needed, saving time and costs.
- **Agility**: Cloud services allow for faster innovation and speed to market.
- **Durability**: Long-term data protection ensures data integrity.

### Cloud Computing Models

1. **Infrastructure as a Service (IaaS)**: Rent and manage building blocks like servers and networks. Example: AWS EC2.
2. **Software as a Service (SaaS)**: Use complete applications on demand. Example: Web-based email.
3. **Platform as a Service (PaaS)**: Provides tools for developers to build applications without managing underlying infrastructure. Example: AWS Elastic Beanstalk.

### Cloud Deployment Models

1. **Private Cloud**: Resources are hosted on-premises, providing more control and security but lacking cloud flexibility.
2. **Public Cloud**: AWS, Azure, GCP provide the hardware and services, offering all cloud benefits like scalability and cost-efficiency.
3. **Hybrid Cloud**: Combines private and public clouds, often with sensitive data stored locally while leveraging cloud services for scalability. Secure connections such as VPN or AWS Direct Connect link private and public clouds.

---

## AWS Availability Zones (AZs)

### AWS Regions

An AWS **Region** is a physical location that groups AWS services and infrastructure based on geographic areas. Each region operates independently and is isolated from other regions, ensuring that if one region is affected by an event such as a natural disaster, other regions remain unaffected. Resources and services within a region do not automatically replicate to other regions, so replication must be done manually.

For example, the **US East** geographic location includes the **Ohio** and **North Virginia** regions. Each region is designed to provide independence in terms of resource management and failure isolation.

### AWS Availability Zones (AZs)

AWS regions consist of multiple **Availability Zones (AZs)**, which are sets of one or more data centers located in separate facilities within a region. Each AZ has independent power, networking, and connectivity, ensuring fault tolerance. While the number of data centers in an AZ is not explicitly documented by AWS, an AZ typically consists of several discrete data centers.

AZs are connected via low-latency links to ensure high availability. If one AZ experiences failure, applications running across multiple AZs will remain functional in the remaining zones. This redundancy supports both **high availability** and **fault tolerance** for critical applications.

### Key Characteristics

- **Regions** are isolated and resource-specific.
- **Availability Zones** are fault-tolerant and connected via low-latency links.
- Deploying applications across multiple AZs enhances both high availability and fault tolerance.

### Scenarios

- An application running in a single AZ (e.g., **us-east-1a**) is **not fault-tolerant**. For fault tolerance, it must span multiple AZs.
- If an application running across multiple AZs experiences downtime, the entire region may be out of service.

---

## Edge Locations and Local Zones

### Latency

**Latency** refers to the amount of time between a user's request and the corresponding response from a server. Lower latency is desirable as it means faster load times and a better user experience.

### Local Zones

**Local Zones** are extensions of AWS Regions that place compute, storage, database, and other select AWS services closer to end-users. This proximity allows for applications that require ultra-low latency, typically in the single-digit milliseconds, such as real-time gaming or live video streaming.

Key characteristics of Local Zones:

- Extend AWS Regions by providing infrastructure closer to users.
- Offer high-bandwidth and secure connections between local workloads and those running in the parent AWS Region.
- Ideal for latency-sensitive applications.

### Edge Locations

**Edge Locations** are sites that AWS CloudFront uses to cache copies of your content for faster delivery to users across the globe. They are not used to launch resources but serve as global endpoints to reduce latency by delivering content closer to where users are located.

Key characteristics of Edge Locations:

- Help reduce latency by caching content via AWS CloudFront.
- There are more Edge Locations than AWS Regions and Availability Zones.
- Utilize the AWS global network backbone for efficient content delivery.

### Scenarios

1. **Scenario**: You need to ensure millisecond latency for a new application.
   - **Solution**: Use **Local Zones** to place services closer to end-users.

2. **Scenario**: You want to lower latency for a website available on two continents.
   - **Solution**: Utilize **Edge Locations** through AWS CloudFront to cache content closer to users.

---


## Introducing the Frameworks

### Cloud Adoption Framework Overview

The AWS **Cloud Adoption Framework (CAF)** helps businesses use AWS to digitally transform and accelerate outcomes. It consists of six **perspectives** that cover foundational capabilities:

1. **Security**: Focuses on governance, security assurance, and incident response.
2. **Business**: Addresses strategy, innovation, and business insights.
3. **Platform**: Covers infrastructure, applications, and modern development practices.
4. **Operations**: Ensures successful workload delivery and includes monitoring and management.
5. **Governance**: Minimizes risks and includes program management and cloud financials.
6. **People**: Focuses on leadership, workforce transformation, and organizational design.

The framework also includes four **transformation domains**: technology, process, organizational, and product transformation, and follows a phased **journey**: **Envision**, **Align**, **Launch**, and **Scale**.

### Well-Architected Framework Overview

The **Well-Architected Framework** is designed to help businesses build secure, efficient, and reliable applications in the cloud. It includes six key pillars:

1. **Security**: Protects data and systems.
2. **Cost Optimization**: Manages cloud costs effectively.
3. **Performance Efficiency**: Maximizes the efficient use of resources.
4. **Operational Excellence**: Ensures the successful operation of workloads.
5. **Reliability**: Focuses on system recovery and disaster resilience.
6. **Sustainability**: Minimizes environmental impact by optimizing resource usage.

The framework emphasizes general **design principles**, such as automating processes, testing at production scale, and using data to drive architectural decisions.

Here's a concise and formal version of the transcript for your chapter on "AWS Management Console and Accessing AWS":

---

## AWS Management Console and Accessing AWS

### AWS Management Console

The **AWS Management Console** is the most popular and user-friendly way to interact with AWS resources, accessible via a web browser. It is especially useful for non-technical roles, like project managers, as well as technical roles such as engineers or developers. The console allows users to search for services, create, modify, or terminate resources within an AWS account.

#### Root User

The **root user** is the most powerful account in AWS. It is created when setting up an AWS account and has full control, including the ability to delete the account and all resources. For security, it is critical to:
- Enable **Multi-Factor Authentication (MFA)** on the root user.
- Avoid using the root user for day-to-day tasks. Instead, create new users or groups using **IAM (Identity and Access Management)**.

#### Other Ways to Access AWS

- **CLI (Command Line Interface)**: The CLI allows access to AWS resources through a terminal using commands. It is preferred by developers and engineers for automating tasks and gaining programmatic access via API calls.
  
- **SDKs (Software Development Kits)**: SDKs allow developers to interact with AWS resources programmatically using languages like Java, Python, and C#. They provide another way to access AWS outside the console.

---

## Exploring Your Amazon Web Services (AWS) Account

In this lesson, we will walk through the process of creating and securing an AWS account, setting up a root user, and creating a daily user for managing AWS resources.

### Creating an AWS Account

To create an AWS account:
1. Navigate to the AWS signup page and enter your **email address** and **account name**.
2. Verify your email, set a **password**, and complete the billing information.
3. Confirm your identity via **mobile phone**.
4. Choose a support plan (for this demonstration, select **Basic Support**).
5. Log in for the first time using the **root user** credentials.

### Securing the Root User

The root user is the most powerful account and should be secured immediately:
1. Log in to the **AWS Management Console** with the root user.
2. Go to **IAM (Identity and Access Management)**.
3. Set up **Multi-Factor Authentication (MFA)** using an authenticator app like Google Authenticator or Duo Mobile.
4. Verify the MFA setup by entering the generated code.

### Creating a Daily User

To create a daily user for regular account access:
1. In the IAM dashboard, select **Users** and click **Create User**.
2. Name the user (e.g., "Daily User") and grant **console access**.
3. Set a **custom password** for the user. Optionally, uncheck "Require password reset" for this demonstration.
4. Attach the **AdministratorAccess** policy to give the user administrative permissions (for demonstration purposes).
5. Complete the user setup and save the **account ID** for future logins.

### Logging In as the Daily User

1. Sign out from the root user session.
2. Select **IAM User** on the login page, input your **account ID**, and enter the **username** and **password** for the daily user.
3. You are now logged in as the daily user, ready to manage AWS resources.

---

## Foundations of Cloud Computing Review

### Service Categories

- **Read the AWS Services Whitepaper**: This will help you quickly identify which services fit specific categories (e.g., EC2 is a compute service, while S3 is not).
- **Know the Six Advantages of Cloud Computing**:
  1. Global deployment in minutes.
  2. Eliminate data center expenses.
  3. Stop guessing capacity.
  4. Increase speed and agility.
  5. Benefit from economies of scale.
  6. Trade fixed expenses for variable ones.

### Cloud Benefits

Understand cloud benefits, including:

- **High Availability**: Systems designed to operate without failure for a long period.
- **Elasticity**: The ability to scale resources based on demand.
- **Agility**: Rapidly adapt to changes in business requirements.
- **Durability**: Long-term data integrity and protection.

### Cloud Computing Models In a nut shell

- **IaaS (Infrastructure as a Service)**: Renting computing resources (e.g., hosting a website).
- **SaaS (Software as a Service)**: Accessing complete applications via the web (e.g., email).
- **PaaS (Platform as a Service)**: Developing applications without managing infrastructure (e.g., using developer tools on a cloud platform).

### Cloud Deployment Models in a nut shell

- **Private Cloud**: Resources hosted on-premises or in your own data center.
- **Public Cloud**: Utilizing cloud providers like AWS to run everything.
- **Hybrid Cloud**: Combining private and public clouds with secure connections, such as **Direct Connect**.

### Regions and Availability Zones

- **Regions** consist of two or more **Availability Zones (AZs)**.
- **AZs** are made up of multiple data centers and provide **high availability** and **fault tolerance**.
- **Edge Locations** reduce latency by caching content closer to users through **CloudFront**.
- **Local Zones** bring AWS services closer to users for millisecond latency in applications like real-time gaming.

### Cloud Adoption Framework

- **Phases**: Envision, Align, Launch, and Scale (continuous process).
- **Benefits**: Reduces business risks, improves ESG (Environmental, Social, and Governance), grows revenue, and increases operational efficiency.

### Well-Architected Framework

- Six pillars:
  1. **Security**
  2. **Cost Optimization**
  3. **Performance Efficiency**
  4. **Operational Excellence**
  5. **Reliability**
  6. **Sustainability**

Understand how to apply services that align with each pillar.

### AWS Management Console in a nut shell

- **Root User**: Most powerful user in AWS, capable of deleting accounts and resources. Protect it using **MFA**.
- **Daily Users/Groups**: Create users for daily tasks.
- AWS resources can be managed through the **AWS Console**, **CLI**, and **SDKs**.
- Remember to check the **region** before making changes to any resources.

---

This concise version captures all the important tips for the exam while keeping it structured and clear. Let me know if you'd like to adjust or add anything!

## AWS Global Infrastructure

- **Regions**: Geographical areas where AWS has data centers (e.g., us-east-1, eu-west-1).
- **Availability Zones (AZs)**: Isolated locations within regions (typically multiple AZs per region).
- **Edge Locations**: For content delivery via services like CloudFront.

---

## Core AWS Services

### Compute

- **Amazon EC2**: Elastic Compute Cloud for scalable virtual machines.
  - **EC2 Instance Types**: General Purpose, Compute Optimized, Memory Optimized, etc.
  - **Elastic Load Balancing (ELB)**: Distribute traffic across multiple EC2 instances.
  - **Auto Scaling**: Automatically adjust capacity based on demand.

- **AWS Lambda**: Run code without provisioning or managing servers (serverless).

### Storage

- **Amazon S3 (Simple Storage Service)**: Object storage built to store and retrieve any amount of data.
  - **Storage Classes**: Standard, Infrequent Access, Glacier, etc.
  - **S3 Bucket Policies**: Access management for S3 buckets.

- **Amazon EBS (Elastic Block Store)**: Block storage for EC2 instances.

- **Amazon Glacier**: Long-term archival storage.

### Networking

- **Amazon VPC (Virtual Private Cloud)**: Isolated networks within AWS.
  - **Subnets**: Logical divisions of VPCs.
  - **Security Groups**: Firewall rules for EC2 instances.
  - **NACLs (Network Access Control Lists)**: Firewall rules at the subnet level.

- **Amazon Route 53**: Scalable DNS and domain name management.

---

## Security and Compliance

- **IAM (Identity and Access Management)**: Manage access to AWS services.
  - **Users, Groups, Roles, and Policies**: Core IAM components.
  - **MFA (Multi-Factor Authentication)**: Add extra security.

- **AWS Shield**: DDoS protection for applications.
- **AWS WAF (Web Application Firewall)**: Protects web applications from common web exploits.

---

## Cloud Technology and Services

---

## Billing and Pricing

- **Free Tier**: AWS offers a 12-month free tier for certain services.
- **Pay-as-you-go**: Only pay for what you use, with no upfront costs.
- **Cost Management Tools**:
  - **AWS Cost Explorer**: Analyze and manage AWS spending.
  - **AWS Budgets**: Set custom budgets and get alerts.

---

## Additional Topics

- **CloudFormation**: Infrastructure as code for automating resource provisioning.
- **Elastic Beanstalk**: Platform as a service (PaaS) to deploy and manage applications.

---

## Resources

- [AWS Documentation](https://aws.amazon.com/documentation/)
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Whitepapers](https://aws.amazon.com/whitepapers/)