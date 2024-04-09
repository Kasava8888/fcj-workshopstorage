---
title : "Tạo EFS"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---
1. Trong giao diện **AWS Management Console** của tài khoản **Root** chọn **EFS**
![efs](/images/3.efs/3.1.1.png)
2. Trong giao diện **EFS**
* **Create file system**
![efs](/images/3.efs/3.1.2.png)
* Chọn **Customize**
![efs](/images/3.efs/3.1.3.png)

* Nhập **Name** : ```efs```
* **File system type: One Zone**
* **Availability Zone: us-east-1a**
![efs](/images/3.efs/3.1.4.png)
* **Transition into Archive : None**
* **Throughput mode: bursting**
* **Next**
![efs](/images/3.efs/3.1.5.png)
* Chọn **VPC1**
* Chọn **Security group : Sgec2vpc1**
* **Next**
![efs](/images/3.efs/3.1.6.png)
* **Next** 
![efs](/images/3.efs/3.1.7.png)
* **Create**
![efs](/images/3.efs/3.1.8.png)
3. Tạo thành công
![efs](/images/3.efs/3.1.9.png)
