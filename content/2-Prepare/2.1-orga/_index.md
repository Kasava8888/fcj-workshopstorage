---
title : "Use Organization"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1. </b> "
---
In this step, we will use **Organization** to create **OU** and **Aws account**

1. In the **AWS Management Console** interface, find **Organization**
![**Organization**](/public/images/2.prepare/2.1.8.png)
2. In the **Organization** interface
* Select **AWS account** on the left panel
* Select the box **Root** -> **Actions** -> **Create new**
![**Organization**](/public/images/2.prepare/2.1.1.png)
3. In the **OU** creation interface
* Enter **Organiational unit name** : ``Dev``
* Select **Create Organizational unit**
![**Organization**](/public/images/2.prepare/2.1.2.png)
4. In the **Organization** interface
* Select **AWS account** on the left panel
* Select **Add an AWS account**
![**Organization**](/public/images/2.prepare/2.1.3.png)
5. In the account creation interface
* Enter **AWS accounts name**: ```DevUser```
* Enter email
* Click **Create AWS account** and wait for the creation to complete
![**Organization**](/public/images/2.prepare/2.1.4.png)
6. Move the newly created account to **OU**
* Select the box **DevUser** -> **Actions** -> **Move**
![**Organization**](/public/images/2.prepare/2.1.6.png)
* In the **Destination** section, click **Dev OU** -> **Move AWS account**
![**Organization**](/public/images/2.prepare/2.1.7.png)