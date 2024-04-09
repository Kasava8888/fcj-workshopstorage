---
title : "Create Fileshare"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---


* In the **Storage Gateway** interface, select **Gateways** from the left panel, select the box **filesgw -> Create file share**
![filegw](/images/4.filegw/4.3.1.png)
* **Gateway**: select **filesgw**
* **File sharing protocol: SMB**
* **S3 Bucket**: select the **Bucket** you created
* **User authentication: Guest access**
* Select **Customize configuration**
![filegw](/images/4.filegw/4.3.2.png)

* **S3 prefix name**: ```filegw/```
* **File share name**: ```haidang```
![filegw](/images/4.filegw/4.3.3.png)
* Scroll down to select **Set refresh interval**, set to 5 minutes
* **Next**
![filegw](/images/4.filegw/4.3.4.png)
* Leave as default, select **Next**
![filegw](/images/4.filegw/4.3.5.png)
* **Authentication method: Guest access -> Next**
![filegw](/images/4.filegw/4.3.6.png)
* Select **Create**
![filegw](/images/4.filegw/4.3.7.png)
* Created successfully
![filegw](/images/4.filegw/4.3.8.png)