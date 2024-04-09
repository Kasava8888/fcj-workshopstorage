---
title : "Tạo S3 Bucket và Agent cho Storage Gateway"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1. </b> "
---
1. Trên tài khoản **Root** , tạo **S3 Bucket**
* Trong giao diện **S3**, chọn **Create bucket**
![filegw](/images/4.filegw/4.1.1.png)
* Trong giao diện tạo **bucket**, nhập **Bucket name**, Bucket name phải là duy nhất
* Để mặc định, cuộn xuống và **Create bucket**
![filegw](/images/4.filegw/4.1.2.png)

![filegw](/images/4.filegw/4.1.3.png)
2. Trên tài khoản **Root**, tạo **Agent** cho **Storage Gateway**
* Trong **AWS Management Console**, chọn **Storage Gateway**
![filegw](/images/4.filegw/4.1.4.png)
* Trong **Storage Gateway**, chọn **Create gateway**
![filegw](/images/4.filegw/4.1.5.png)
* Nhập **Gateway name**: ```filegw```
* **Gateway type: Amazon S3 File Gateway**
![filegw](/images/4.filegw/4.1.6.png)
* **Launch Instance**
![filegw](/images/4.filegw/4.1.7.png)
* Trong giao diện **Launch instance**, nhập **Name**: ```agent```
![filegw](/images/4.filegw/4.1.8.png)
* **Type: m4.large**
![filegw](/images/4.filegw/4.1.9.png)
* Chọn **key pair** sẵn có hoặc tạo **key pair**
![filegw](/images/4.filegw/4.1.10.png)
* Thêm rule **http** và **smb** cho **security groups**
![filegw](/images/4.filegw/4.1.11.png)
* **Configure storage**: chọn **Add new volume**

![filegw](/images/4.filegw/4.1.12.png)
* Thêm 150gb volumn gp3 và **Launch instance**
![filegw](/images/4.filegw/4.1.13.png)
* Tạo thành công
![filegw](/images/4.filegw/4.1.14.png)
