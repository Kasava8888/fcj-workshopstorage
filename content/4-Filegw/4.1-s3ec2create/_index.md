---
title : "Create S3 Bucket and Agent for Storage Gateway"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

1. On **Root** account, create **S3 Bucket**
* In the **S3** interface, select **Create bucket**
![filegw](/images/4.filegw/4.1.1.png)
* In the **bucket** creation interface, enter **Bucket name**, Bucket name must be unique
* Leave it as default, scroll down and **Create bucket**
![filegw](/images/4.filegw/4.1.2.png)

![filegw](/images/4.filegw/4.1.3.png)
2. On **Root** account, create **Agent** for **Storage Gateway**
* In **AWS Management Console**, select **Storage Gateway**
![filegw](/images/4.filegw/4.1.4.png)
* In **Storage Gateway**, select **Create gateway**
![filegw](/images/4.filegw/4.1.5.png)
* Enter **Gateway name**: ```filegw```
* **Gateway type: Amazon S3 File Gateway**
![filegw](/images/4.filegw/4.1.6.png)
* **Launch Instance**
![filegw](/images/4.filegw/4.1.7.png)
* In the **Launch instance** interface, enter **Name**: ```agent```
![filegw](/images/4.filegw/4.1.8.png)
* **Type: m4.large**
![filegw](/images/4.filegw/4.1.9.png)
* Choose an existing **key pair** or create a **key pair**
![filegw](/images/4.filegw/4.1.10.png)
* Add **http** and **smb** rules for **security groups**
![filegw](/images/4.filegw/4.1.11.png)
* **Configure storage**: select **Add new volume**

![filegw](/images/4.filegw/4.1.12.png)
* Add 150gb gp3 volume and **Launch instance**
![filegw](/images/4.filegw/4.1.13.png)
* Created successfully
![filegw](/images/4.filegw/4.1.14.png)