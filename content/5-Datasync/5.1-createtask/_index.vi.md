---
title : "Tạo Task"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 5.1. </b> "
---
1. Tạo **Task** di chuyển dữ liệu từ **EFS** sang **S3 Bucket** trên tài khoản **Root**
* Trong giao diện **AWS Management Console**, chọn **DataSync**
![datasync](/images/5.datasync/5.1.1.png)
* Trong giao diện **DataSync**, chọn **Tasks** ở thanh điều khiển bên trái, chọn **Create task**
![datasync](/images/5.datasync/5.1.2.png)
* **Create a new location**
* L**ocation type: EFS**
* **Region: US East**
* **File system: efs** chúng ta đã tạo
![datasync](/images/5.datasync/5.1.3.png)
* **Subnet: Pubsubvpc1**
* **Security groups: SGec2vpc1**
* Chọn **TLS 1.2**
![datasync](/images/5.datasync/5.1.4.png)
* Các tùy chọn khác để mặc định -> **Next**
![datasync](/images/5.datasync/5.1.5.png)
* **Location type: S3**
* **Region: US East**
* **S3 bucket**: Chọn **bucket** chúng ta đã tạo
* **Folder**: nhập ```filegw/```
* **IAM role**: Chọn **Auto Generated**
* Chọn **Next**
![datasync](/images/5.datasync/5.1.6.png)
* **Tranfer mode**: **Transfer all data**
![datasync](/images/5.datasync/5.1.7.png)
* Để các tùy chọn khác mặc định -> **Next**
![datasync](/images/5.datasync/5.1.8.png)
* Cuộn xuống -> **Create task**
![datasync](/images/5.datasync/5.1.9.png)
2. Chạy **Task**
* Chọn **Start -> Start with defaults**
![datasync](/images/5.datasync/5.1.10.png)
* Chạy thành công, chờ đến khi báo **complete**
![datasync](/images/5.datasync/5.1.11.png)
