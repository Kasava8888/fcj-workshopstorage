---
title : "PrivateLink"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Deploy a hybrid storage solution using EFS, Filegateway and DataSync
## Solution architecture overview
![diagram](/images/1.introduce/diagram1.png)


## Requirements
1. On **on-premise** environment
* Deploy **File gateway** to store data from **on-premise** to **S3 File Gateway**
2. On Cloud environment
* 4 **VPCs** belonging to 2 branches in 2 regions, 2 different accounts will connect to each other and use **EFS** to store data necessary for business.

* Deploy **DataSync** to automatically copy data from **EFS** to **S3 File Gateway** to serve **on-premise** users
### Content
 1. [Introduction](1-Introduce/)
 2. [Deploy Cross-account and Cross-region VPC environment](2-prepare/)
 3. [EFS Deployment](3-Efs/)
 4. [File Gateway Deployment ](4-Filegw/)
 5. [DataSync Deployment](5-Datasync/)
 6. [Cleanup](6-Cleanup/)