---
title : "Configure on-premise and check the results"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4.4. </b> "
---

1. In the **Storage Gateway** interface, select **File shares** from the left panel, select the newly created **File share**
![filegw](/public/images/4.filegw/4.4.1.png)
* In **Details** , copy **Example Commands**
![filegw](/public/images/4.filegw/4.4.2.png)
* Edit the command and paste it into the cmd of your personal computer
* In the sample command [WindowsDriveLetter] replace with the drive name, usually a letter like Z, the ip address is replaced with the agent's public ip
* Enter the created password
![filegw](/public/images/4.filegw/4.4.3.png)
* A Z drive appears on the PC, access and create a file named **hello.txt**
![filegw](/public/images/4.filegw/4.4.4.png)
![filegw](/public/images/4.filegw/4.4.5.png)
* In the **root** account, access **S3**, select the **S3** we created, select **Folder filegw/** and check to see the newly created file on your personal computer has been stored on **S3**
![filegw](/public/images/4.filegw/4.4.6.png)
![filegw](/public/images/4.filegw/4.4.7.png)

![filegw](/public/images/4.filegw/4.4.8.png)
* Perform file upload on **S3**
![filegw](/public/images/4.filegw/4.4.9.png)
![filegw](/public/images/4.filegw/4.4.10.png)
* Perform **Refresh cache** on **file share** to synchronize data from **S3** to **onpremise**
![filegw](/public/images/4.filegw/4.4.11.png)
![filegw](/public/images/4.filegw/4.4.12.png)
* Check the Z drive on the computer and see the results
![filegw](/public/images/4.filegw/4.4.13.png)