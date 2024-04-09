---
title : "Tạo Fileshare"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---
* Trong giao diện **Storage Gateway**, chọn **Gateways** từ bảng điều khiển bên trái, chọn ô vuông **filesgw -> Create file share**
![filegw](/public/images/4.filegw/4.3.1.png)
* **Gateway**: chọn **filesgw**
* **File share protocol: SMB**
* **S3 Bucket**: chọn **Bucket** bạn đã tạo 
* **User authentication: Guest access**
* Chọn **Customize configuration**
![filegw](/public/images/4.filegw/4.3.2.png)

* **S3 prefix name**: ```filegw/```
* **File share name**: ```haidang```
![filegw](/public/images/4.filegw/4.3.3.png)
* Cuộn xuống chọn **Set refresh interval** , cài đặt 5 minutes
* **Next**
![filegw](/public/images/4.filegw/4.3.4.png)
* Để mặc định , chọn **Next**
![filegw](/public/images/4.filegw/4.3.5.png)
* **Authentication method: Guest access -> Next**
![filegw](/public/images/4.filegw/4.3.6.png)
* Chọn **Create**
![filegw](/public/images/4.filegw/4.3.7.png)
* Tạo thành công
![filegw](/public/images/4.filegw/4.3.8.png)