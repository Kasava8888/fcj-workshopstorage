---
title : "Sử dụng Single-Sign-On"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2. </b> "
---
## Kích hoạt SSO
1. Trong **AWS Management Console**, Chọn **IAM Identity Center**
![sso](/images/2.prepare/2.2.1.png)
2. Chọn **Enable**
![sso](/images/2.prepare/2.2.23.png)
## Tạo Group
1. Trong giao diện **SSO**
* Chọn **Groups** từ bảng điều khiển bên trái -> **Create group**
![sso](/images/2.prepare/2.2.2.png)
2. Trong giao diện tạo **Group**
* Nhập **Group name** : ```DevGroup```
* Chọn **Create group**
![sso](/images/2.prepare/2.2.3.png)
## Tạo User
1. Trong giao diện **SSO**
* Chọn **Users** từ bảng điều khiển bên trái -> **Add user**
![sso](/images/2.prepare/2.2.4.png)
2. Trong giao diện tạo user
* Nhập **Username** : ```DevUser```
* Mục **Password** , chọn **Send an email**
* Nhập email và thông tin
![sso](/images/2.prepare/2.2.5.png)
* Click **Next**
![sso](/images/2.prepare/2.2.6.png)
* Chọn ô vuông **DevGroup** -> **Next**
![sso](/images/2.prepare/2.2.7.png)
* Cuộn xuống dưới cùng chọn **Add user**
![sso](/images/2.prepare/2.2.8.png)
3. Thêm user thành công 
![sso](/images/2.prepare/2.2.9.png)
4. Kiểm tra email của tài khoản root
![sso](/images/2.prepare/2.2.10.png)
 * Click **Accept invitation**
![sso](/images/2.prepare/2.2.11.png)
* Thiết lập password cho tài khoản **SSO**
![sso](/images/2.prepare/2.2.12.png)
* Đăng ký MFA bằng phương thức Authenticator app
![sso](/images/2.prepare/2.2.13.png)
* Tải ứng dụng **Goole Authenticator** và quét mã QR
![sso](/images/2.prepare/2.2.14.png)
## Tạo Permission sets
1. Trong giao diện **SSO**
* Chọn **Permission sets** từ bảng điều khiển bên trái -> Chọn **Create permission set** 
![sso](/images/2.prepare/2.2.15.png)
2. Trong giao diện tạo **permission set**
* Trong mục **type**, chọn **Predefined permission set** 
* Trong mục **Policy for predefined permission set** chọn **AdministratorAccess -> Next**
![sso](/images/2.prepare/2.2.16.png)
* **Next**
![sso](/images/2.prepare/2.2.17.png)
## Tiến hành Assign user organization
1. Trong giao diện **SSO**
* Chọn **AWS accounts** từ bảng điều khiển bên trái
* Chọn ô vuông **DevUser** trong **OU Dev** -> Chọn **Assign users or groups**
![sso](/images/2.prepare/2.2.18.png)
2. Trong giao diện **assign users and groups**
* Chọn ô vuông **DevGroup -> Next**
![sso](/images/2.prepare/2.2.19.png)
* Chọn ô vuông A**dministratorAccess -> Next**
![sso](/images/2.prepare/2.2.20.png)
* **Submit**
![sso](/images/2.prepare/2.2.24.png)
## Đăng nhập bằng SSO
1. Trong giao diện **SSO**
* Chọn **Dashboard** từ bảng điều khiển bên trái, sao chép **AWS access portal URL**
![sso](/images/2.prepare/2.2.25.png)
2. Trong giao diện đăng nhập
* Nhập tài khoản, mật khẩu và xác thực MFA 
* Chọn đăng nhập vào **DevUser** với quyền **AdministratorAccess**
![sso](/images/2.prepare/2.2.21.png)
* Đăng nhập thành công
![sso](/images/2.prepare/2.2.22.png)
