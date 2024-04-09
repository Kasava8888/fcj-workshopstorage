---
title : "Cấu hình sử dụng EFS tại các máy chủ"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
1. Cấu hình **security group** 
* Trong giao diện **EC2**, chọn **Security groups** bên bảng điều khiển bên trái, chọn **SGec2vpc1 -> Inbound rules -> Edit inbound rules**
![efs](/images/3.efs/3.1.12.png)
* Thêm rule cho phép **NFS**
* **Save rules**
![efs](/images/3.efs/3.1.13.png)

2. Thực hiện mount vào từng server
* Tại giao diện **EFS**, chọn efs
![efs](/images/3.efs/3.1.9.png)
* **Attach**
![efs](/images/3.efs/3.1.10.png)
* Chọn **Mount via IP**, sao chép lệnh mount  
![efs](/images/3.efs/3.1.11.png)
* Truy cập **server1**, chỉnh sửa lại lệnh mount và chạy chuỗi lệnh sau 

![efs](/images/3.efs/3.1.14.png)
* Làm tương tự với **server2**
![efs](/images/3.efs/3.1.15.png)
* Làm tương tự với **server3**
![efs](/images/3.efs/3.1.16.png)
* Làm tương tự với **server4**
![efs](/images/3.efs/3.1.17.png)
3. Cấu hình file /etc/fstab để mount tự động mỗi khi khởi động máy chủ 
```
vi /etc/fstab
```
* Nhập i để vào insert mode, thêm dòng sau vào file cấu hình 
```
<ip>:/	/efs nfs4	nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport 0 0
```
* ```nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport``` lấy ở trong câu lệnh copy từ efs 
* Nhấn nút **Esc** , nhập ```:wq!``` - > **enter** để lưu lại file

![efs](/images/3.efs/3.1.20.png)