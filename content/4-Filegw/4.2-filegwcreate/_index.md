---
title : "Create File Gateway"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2. </b> "
---


1. Wait for **Agent** to finish creating and return to the **Gateway Storage** creation interface
* Select the box **I completed all the steps above and launch the EC2 Instance -> Next**
![filegw](/public/images/4.filegw/4.2.1.png)
* Copy the public ip of **agent** and enter -> **Puclic accessible -> Next**
![filegw](/public/images/4.filegw/4.2.2.png)
![filegw](/public/images/4.filegw/4.2.3.png)
* Select **Deactive logging**
* Select **No alarm**
* Select **Configure**
![filegw](/public/images/4.filegw/4.2.4.png)
2. Configure **guest access SMB**
* In the **Storage Gateway** interface, select **filegw -> Actions -> Edit SMB settings -> Guest access settings**
![filegw](/public/images/4.filegw/4.2.5.png)
* Enter **password** -> **Save changes**
![filegw](/public/images/4.filegw/4.2.6.png)