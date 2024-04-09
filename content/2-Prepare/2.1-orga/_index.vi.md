---
title : "Sử dụng Organization"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1. </b> "
---



Trong bước này, chúng ta sẽ sử dụng **Organization** để tạo **OU** và **AWS Account** 

1. Trong giao diện **AWS Management Console**, tìm **Organization**
![**Organization**](/public/images/2.prepare/2.1.8.png)
2. Trong giao diện **Organization**
* Chọn **AWS account** ở bảng điều khiển bên trái
* Chọn ô vuông **Root** -> **Actions** -> **Create new**
![**Organization**](/public/images/2.prepare/2.1.1.png)
3. Trong giao diện tạo **OU**
* Nhập **Organiational unit name** : ``Dev``
* Chọn **Create Organizational unit**
![**Organization**](/public/images/2.prepare/2.1.2.png)
4. Trong giao diện **Organization**
* Chọn **AWS account** ở bảng điều khiển bên trái
* Chọn **Add an AWS account**
![**Organization**](/public/images/2.prepare/2.1.3.png)
5. Trong giao diện tạo account
* Nhập **AWS accounts name**: ```DevUser```
* Nhập email
* Click **Create AWS account** và chờ đợi việc tạo được hoàn tất
![**Organization**](/public/images/2.prepare/2.1.4.png)
6. Thực hiện di chuyển account vừa tạo vào **OU**
* Chọn ô vuông **DevUser** -> **Actions** -> **Move**
![**Organization**](/public/images/2.prepare/2.1.6.png)
* Trong mục **Destination** , click **Dev OU** -> **Move AWS account**
![**Organization**](/public/images/2.prepare/2.1.7.png)