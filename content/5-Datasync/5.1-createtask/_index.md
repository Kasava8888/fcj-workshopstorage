---
title : "Create Task"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

1. Create **Task** to move data from **EFS** to **S3 Bucket** on **Root** account
* In the **AWS Management Console** interface, select **DataSync**
![datasync](/images/5.datasync/5.1.1.png)
* In **DataSync** interface, select **Tasks** in the left control bar, select **Create task**
![datasync](/images/5.datasync/5.1.2.png)
* **Create a new location**
* Location type: EFS**
* **Region: US East**
* **File system: efs** we have created
![datasync](/images/5.datasync/5.1.3.png)
* **Subnet: Pubsubvpc1**
* **Security groups: SGec2vpc1**
* Select **TLS 1.2**
![datasync](/images/5.datasync/5.1.4.png)
* Other options leave default -> **Next**
![datasync](/images/5.datasync/5.1.5.png)
* **Location type: S3**
* **Region: US East**
* **S3 bucket**: Select the **bucket** we created
* **Folder**: enter ```filegw/```
* **IAM role**: Select **Auto Generated**
* Select **Next**
![datasync](/images/5.datasync/5.1.6.png)
* **Transfer mode**: **Transfer all data**
![datasync](/images/5.datasync/5.1.7.png)
* Leave other options as default -> **Next**
![datasync](/images/5.datasync/5.1.8.png)
* Scroll down -> **Create task**
![datasync](/images/5.datasync/5.1.9.png)
2. Run **Task**
* Select **Start -> Start with defaults**
![datasync](/images/5.datasync/5.1.10.png)
* Run successfully, wait until it says **complete**
![datasync](/images/5.datasync/5.1.11.png)