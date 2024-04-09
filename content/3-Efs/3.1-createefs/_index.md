---
title : "Create EFS"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1. </b> "
---
1. In the **AWS Management Console** interface of the **Root** account, select **EFS**
![efs](/images/3.efs/3.1.1.png)
2. In the **EFS** interface
* **Create file system**
![efs](/images/3.efs/3.1.2.png)
* Select **Customize**
![efs](/images/3.efs/3.1.3.png)

* Enter **Name** : ```efs```
* **File system type: One Zone**
* **Availability Zone: us-east-1a**
![efs](/images/3.efs/3.1.4.png)
* **Transition into Archive : None**
* **Throughput mode: bursting**
* **Next**
![efs](/images/3.efs/3.1.5.png)
* Select **VPC1**
* Select **Security group : Sgec2vpc1**
* **Next**
![efs](/images/3.efs/3.1.6.png)
* **Next**
![efs](/images/3.efs/3.1.7.png)
* **Create**
![efs](/images/3.efs/3.1.8.png)
3. Create success
![efs](/images/3.efs/3.1.9.png)