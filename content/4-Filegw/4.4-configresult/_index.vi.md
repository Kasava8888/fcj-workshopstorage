---
title : "Cấu hình ở on-premise và kiểm tra kết quả "
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4.4. </b> "
---
1. Trong giao diện **Storage Gateway**, chọn **File shares** từ bảng điều khiển bên trái, chọn **File share** vừa tạo 
![filegw](/images/4.filegw/4.4.1.png)
* Trong **Details** , sao chép **Example Commands**
![filegw](/images/4.filegw/4.4.2.png)
* Chỉnh sửa lại câu lệnh và dán vào cmd của máy cá nhân
* Trong câu lệnh mẫu [WindowsDriveLetter] thay bằng tên ổ, thường là chữ cái như Z , địa chỉ ip thay bằng ip public của agent
* Nhập password đã tạo
![filegw](/images/4.filegw/4.4.3.png)
* Trong PC xuất hiện một ổ Z, truy cập và tạo 1 file tên **hello.txt**
![filegw](/images/4.filegw/4.4.4.png)
![filegw](/images/4.filegw/4.4.5.png)
* Trong tài khoản **root**, truy cập **S3** , chọn **S3** chúng ta đã tạo, chọn **Folder filegw/** và kiểm tra sẽ thấy file vừa tạo trên máy tính cá nhân đã được lưu trữ trên **S3**
![filegw](/images/4.filegw/4.4.6.png)
![filegw](/images/4.filegw/4.4.7.png)

![filegw](/images/4.filegw/4.4.8.png)
* Thực hiện upload file trên **S3**
![filegw](/images/4.filegw/4.4.9.png)
![filegw](/images/4.filegw/4.4.10.png)
* Thực hiện **Refresh cache** trên **file share** để dữ liệu từ **S3** đồng bộ xuống **onpremise**
![filegw](/images/4.filegw/4.4.11.png)
![filegw](/images/4.filegw/4.4.12.png)
* Kiểm tra ổ Z trên máy tính và thấy kết quả
![filegw](/images/4.filegw/4.4.13.png)
