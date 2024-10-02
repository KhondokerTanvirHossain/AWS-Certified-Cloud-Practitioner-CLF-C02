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

## Introduction to AWS

Amazon Web Services (AWS) is a secure cloud services platform offering compute power, database storage, content delivery, and other functionality to help businesses scale and grow.

Key benefits of AWS:
- **Scalability:** On-demand resources.
- **Cost-effective:** Pay-as-you-go pricing.
- **Flexibility:** Multiple services for different workloads.

---

## Foundations of Cloud Computing

[Cloud computing](#https://www.ibm.com/topics/cloud-computing) refers to the delivery of computing services, like storage and processing, over the internet rather than relying on local data centers. AWS provides these services through a global network of servers organized in data centers.

[Virtualization](#https://aws.amazon.com/what-is/virtualization/) is a key technology that allows AWS to divide physical servers into virtual machines (VMs). Each VM operates independently with its own resources (e.g., memory, storage) and is offered on a pay-as-you-go basis, similar to utilities like electricity.

Cloud computing enables businesses to scale without upfront infrastructure costs, with AWS offering services across various categories, such as:

    Compute (e.g., EC2)
    Storage (e.g., S3)
    Networking (e.g., VPC)
    Security (e.g., IAM)

By familiarizing yourself with these categories, you gain a better understanding of how AWS services work and can utilize them efficiently.

---

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