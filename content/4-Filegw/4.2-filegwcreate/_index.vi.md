---
title : "Tạo File Gateway"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2. </b> "
---



1. Chờ **Agent** tạo xong và trở về giao diện tạo **Gateway Storage**
* Chọn ô vuông **I completed all the steps above and launched the EC2 Instance -> Next**
![filegw](/images/4.filegw/4.2.1.png)
* Sao chép ip public của **agent** và nhập vào -> **Puclic accessible -> Next**
![filegw](/images/4.filegw/4.2.2.png)
![filegw](/images/4.filegw/4.2.3.png)
* Chọn **Deactive logging**
* Chọn **No alarm**
* Chọn **Configure**
![filegw](/images/4.filegw/4.2.4.png)
2. Cấu hình **guest access SMB**
* Trong giao diện **Storage Gateway**, chọn **filegw -> Actions -> Edit SMB settings -> Guest access settings**
![filegw](/images/4.filegw/4.2.5.png)
* Nhập **password** -> **Save changes**
![filegw](/images/4.filegw/4.2.6.png)

