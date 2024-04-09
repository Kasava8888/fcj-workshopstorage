---
title : "Deploy peering with Transit gateway"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3. </b> "
---

In this section, we will deploy Peering VPC with **Transit Gateway** according to the following architecture
![diagram](/public/images/1.introduce/diagram1.png)
## Use CloudFormation to deploy a peering configured environment between VPCs in each account
1. Account **root**
* 2 VPCs: VPC1 and VPC2 belong to region us-east-1, each VPC has 1 Public subnet
* 2 EC2 Instances: Server1 and Server2
* 1 Transit Gateway has 2 Transit Gateway Attachments: TGA1 belongs to VPC1, TGA2 belongs to VPC2
2. Account DevUser
* 2 VPCs: VPC1 and VPC2 belong to region ap-southeast-1, each VPC has 1 Public subnet
* 2 EC2 Instances: Server1 and Server2
* 1 Transit Gateway has 2 Transit Gateway Attachments: TGA1 belongs to VPC1, TGA2 belongs to VPC2

### At the root account in Region N.Virginia
Download template to use [Template1.yaml](transitGW.yaml)
1. In the **CloudFormation** interface
* Select **Create stack**
![tgw](/public/images/2.prepare/2.3.1.png)
* Select **Choose an existing template**, select **Upload a template file -> Choose file** to upload the downloaded file -> **Next**
![tgw](/public/images/2.prepare/2.3.2.png)
* Enter **Stack name**: ```transitgw``` -> **Next**
![tgw](/public/images/2.prepare/2.3.3.png)
* Leave as default, scroll down and **Next**
![tgw](/public/images/2.prepare/2.3.4.png)
* Leave as default, scroll down and **Submit**
![tgw](/public/images/2.prepare/2.3.5.png)
2. Create success

![tgw](/public/images/2.prepare/2.3.9.png)
* Wait for the status to change to **Complete**

![tgw](/public/images/2.prepare/2.3.10.png)
3. Connect to Server1 and Server2 and ping between the two servers to check if peering is working or not
* In the **EC2** interface, select **Instances** from the left panel, check the box **server1 -> Connect**
![tgw](/public/images/2.prepare/2.3.11.png)
* In the **Connect to instance** interface, select **EC2 Instance Connect -> Connect using EC2 Instance Connect -> Connect**
![tgw](/public/images/2.prepare/2.3.12.png)
* Successfully connected and successfully pinged the private ip of **server2**
![tgw](/public/images/2.prepare/2.3.16.png)
* Do the same Connect to **server2** and successfully ping the private ip of **server1**
![tgw](/public/images/2.prepare/2.3.15.png)
### At DevUser account in Region Singapore
Download template to use [Template2.yaml](transitgw2.yaml)
1. Create **CloudFormation**
* Follow the same steps as the **root** account
![tgw](/public/images/2.prepare/2.3.17.png)
2. Connect to **Server3** and **Server4** and ping between the two servers to check if peering is working or not
* Follow the same steps as for the **root** account
![tgw](/public/images/2.prepare/2.3.18.png)
![tgw](/public/images/2.prepare/2.3.19.png)
![tgw](/public/images/2.prepare/2.3.20.png)
* Successfully connected and successfully pinged the private ip of **server4**
![tgw](/public/images/2.prepare/2.3.21.png)
## Implement Cross-region Cross-Account peering
### Create peering connection
1. At account **root**
* In the **VPC** interface, select **Transit gateway attachments** from the left panel, select **Create transit gateway attachment**
![tgw](/public/images/2.prepare/2.3.22.png)
* Enter **Name tag** : ```tga3```
* Select **Transit gateway ID**
* Select **Attachment type** : **Peering Connection**
* Select **Account** : **Other account**
![tgw](/public/images/2.prepare/2.3.23.png)
* Copy **Account Id** from **DevUser ** account
 
  
![tgw](/public/images/2.prepare/2.3.24.png)
* Copy **Transit gateway id** from **DevUser** account
![tgw](/public/images/2.prepare/2.3.25.png)
* Select **Region** : **ap-southeast-1** and enter the copied information -> **Create transit gateway attachment**
![tgw](/public/images/2.prepare/2.3.26.png)
* Created successfully and saw status as **Initiating Request**
![tgw](/public/images/2.prepare/2.3.27.png)
2. At account **DevUser**
* In the **VPC** interface, select **Transit gateway attachments** on the left panel, select the attachment square with status **Pending Acceptance** -> **Actions -> Accept transit gateway attachment**
![tgw](/public/images/2.prepare/2.3.28.png)
* **Accept**
![tgw](/public/images/2.prepare/2.3.29.png)
* Wait until acceptance is completed and the status changes to **Available**

![tgw](/public/images/2.prepare/2.3.30.png)
3. At account **root**, configure ****Transit gateway route tables****
* In VPC, select **Transit gateway route tables** from the left panel, select the default **route table** box -> **Create static route**
![tgw](/public/images/2.prepare/2.3.31.png)
* Enter **CIDR** : ```10.2.0.0/16```
* **Type: Active**
* **Choose attachment**: choose **tga3**
* **Create static route**
![tgw](/public/images/2.prepare/2.3.32.png)
* Do the same
![tgw](/public/images/2.prepare/2.3.33.png)
* Created successfully
![tgw](/public/images/2.prepare/2.3.34.png)
4. In the **DevUser** account, configure **Transit gateway route tables**
* Do the same as step 3
![tgw](/public/images/2.prepare/2.3.39.png)
![tgw](/public/images/2.prepare/2.3.40.png)
![tgw](/public/images/2.prepare/2.3.41.png)

5. At the **root** account, configure **Route tables**
* In **VPC,** select **Route tables**from the left panel, select the box **RTBpubsubvpc1 -> Routes -> Edit routes**
![tgw](/public/images/2.prepare/2.3.35.png)
* Add 2 routes as follows -> **Save changes**
  
![tgw](/public/images/2.prepare/2.3.36.png)
* Do the same with **RTBpubsubvpc2**
![tgw](/public/images/2.prepare/2.3.37.png)
![tgw](/public/images/2.prepare/2.3.38.png)
6. At **DevUser** account, configure **Route tables**
* Do the same as step 5
![tgw](/public/images/2.prepare/2.3.42.png)
![tgw](/public/images/2.prepare/2.3.43.png)
![tgw](/public/images/2.prepare/2.3.44.png)
![tgw](/public/images/2.prepare/2.3.45.png)
7. Check the results
* From **server4** successfully pinged to private ip of **server1**
![tgw](/public/images/2.prepare/2.3.46.png)
* From **server3** successfully pinged to private ip of **server1**
![tgw](/public/images/2.prepare/2.3.47.png)
* From **server2** successfully pinged the private ip of **server3** and **server4**
![tgw](/public/images/2.prepare/2.3.48.png)