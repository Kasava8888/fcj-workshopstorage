---
title : "Introduction"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
## Introducing the AWS Organization

**AWS Organizations** is an account management service that allows you to consolidate multiple AWS accounts into one organization that you create and centrally manage. **AWS Organizations** includes consolidated billing and account management capabilities that enable you to better meet the budgeting, security, and compliance needs of your business. As an admin of an organization, you can create accounts in your organization and invite existing accounts to join your organization.
* **AWS Organization**: This is a collection of AWS accounts organized in a specific way, helping you manage them more easily.

* **Organizational Unit (OU)**: A subdivision within **AWS Organization**, allowing you to group accounts together. Each OU can contain many other child OUs.
* **Management Account**: This is the management account with the highest authority in **AWS Organization**. This account can control all other accounts and is responsible for paying aggregate fees of member accounts.
## Introducing AWS Single-Sign-On
**AWS IAM Identity Center (SSO)** is a recommended AWS service for managing user access to AWS resources. This is the only place where you can assign users in your workforce, also known as workforce identities, consistent access to multiple AWS accounts and applications. **AWS IAM Identity Center** is available at no additional charge.

With **AWS IAM Identity Center**, you can create or connect workforce users and centrally manage their access across all their AWS accounts and applications. You can use cross-account permissions to give users in your workforce access to your AWS account. You can use application assignments to assign users access to customer-managed and AWS-managed applications.
## Introducing AWS Transit Gateway

To address the limitation of **Peering Conenction**, **AWS Transite Gateway** is used to connect **VPCs** and **on-premises** networks through a central hub. This simplifies the network and ends complex routing relationships. It works like a cloud router - each new connection is only made once.


**AWS Transit Gateway Attachment** is a tool to assign subnets of each **VPC** that need to connect to each other into an initialized **TGW**. **Transit Gateway Attachment** operates based on the scale of the **Availability Zone** (AZ-level). In **VPC**, when a subnet in an **AZ** has a **Transit Gateway Attachment** with a **TGW**, other subnets in the same **AZ** can connect to that **TGW** 
## Introducing AWS EFS
**Amazon Elastic File System (Amazon EFS)** provides completely flexible, serverless file storage so you can share file data without provisioning or managing capacity and performance storage. **Amazon EFS** is built to scale up to petabytes on demand without application disruption, automatically growing and shrinking as you add and remove files. Because **Amazon EFS** has a simple web services interface, you can create and configure file systems quickly and easily. It manages all of your file storage infrastructure for you, meaning you can avoid the hassle of deploying, patching, and maintaining complex file system configurations.
**Amazon EFS** supports **Network File System** protocol version 4 (**NFSv4.1** and **NFSv4.0**), so the applications and tools you use Today's apps work seamlessly with **Amazon EFS**. **Amazon EFS** is accessible on most **Amazon Web Services** compute instance types, including **Amazon EC2, Amazon ECS, Amazon EKS, AWS Lambda, and AWS Fargate**.

The service is designed for high scalability, high availability, and durability. **Amazon EFS** offers the following file system types to meet your availability and durability needs:

**Regional** (Recommended) – Regional file systems (recommended) store redundant data across multiple geographically separated Availability Zones within an AWS Region. Storing data across multiple Availability Zones provides continuous availability of data, even when one or more Availability Zones in an AWS Region are unavailable.

**One Zone** – A single zone file system stores data in a single Availability Zone within an AWS Region. Storing data in a single Availability Zone provides continuous data availability. However, in the unlikely event of loss or damage to all or part of an Availability Zone, data stored in these types of file systems may be lost.
## Introducing AWS File Storage Gateway
AWS's **File Gateway** is the ultimate **On-premises** data backup and recovery solution, supporting standard protocols such as **NFS** and **SMB**, integrated deep into **Amazon S3**. A special feature is the optimization of cost and capacity, allowing businesses to reduce the burden of **On-premises** storage. Additionally, **File Gateway**'s local cache enhances speed and reduces latency, enhancing the ability to recover data quickly. Additionally, the integration of **S3 Lifecycle Policies** provides automatic storage capabilities into lower-cost tiers, such as **Amazon S3 Glacier**, providing flexibility and efficiency in data management.
## About DataSync
**AWS DataSync** is an online security service that automates and accelerates data movement between on-premises storage and **AWS** Storage services. **DataSync** can copy data between Network File System (**NFS**) share protocol, Server Message Block (**SMB**) share protocol, Distributed File System **Hadoop (HDFS)**, self-managed object storage, **AWS Snowcone**, bucket on **Amazon** Simple Storage Service (**Amazon S3**) , file system on **Amazon** Elastic File System** (**Amazon EFS**), **Amazon FSx** file system for **Windows File Server**, **Amazon file system FSx** is for **Lustre**, **Amazon FSz** file system is for **OpenZFS** and **Amazon FSx** file system is for **NetApp ONTAP**.

**AWS DataSync** is also used to transfer data between **AWS** storage services, making it easy to copy, store, or share application data.