---
title : "Triển khai peering với Transit gateway"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 2.3. </b> "
---

Trong phần này, chúng ta sẽ triển khai Peering VPC với **Transit Gateway** theo kiến trúc sau
![diagram](/public/images/1.introduce/diagram1.png)
## Sử dụng CloudFormation để triển khai môi trường đã cấu hình peering giữa các VPC trong mỗi tài khoản
1. Account **root**  
* 2 VPC: VPC1 và VPC2 thuộc region us-east-1, mỗi VPC có 1 Public subnet
* 2 EC2 Instance : Server1 và Server2
* 1 Transit Gateway có 2 Transit Gateway Attachment : TGA1 thuộc VPC1 , TGA2 thuộc VPC2
2. Account DevUser
* 2 VPC: VPC1 và VPC2 thuộc region ap-southeast-1, mỗi VPC có 1 Public subnet
* 2 EC2 Instance : Server1 và Server2
* 1 Transit Gateway có 2 Transit Gateway Attachment : TGA1 thuộc VPC1 , TGA2 thuộc VPC2

### Tại tài khoản root thuộc Region N.Virginia
Tải xuống mẫu để sử dụng [Template1.yaml](transitGW.yaml)
1. Trong giao diện **CloudFormation**
* Chọn **Create stack**
![tgw](/public/images/2.prepare/2.3.1.png)
* Chọn **Choose an existing template**, chọn **Upload a template file -> Choose file** để upload file vừa tải về -> **Next**
![tgw](/public/images/2.prepare/2.3.2.png)
* Nhập **Stack name**: ```transitgw``` -> **Next**
![tgw](/public/images/2.prepare/2.3.3.png)
* Để mặc định, cuộn xuống và **Next**
![tgw](/public/images/2.prepare/2.3.4.png)
* Để mặc định, cuộn xuống và **Submit**
![tgw](/public/images/2.prepare/2.3.5.png)
2. Tạo thành công 

![tgw](/public/images/2.prepare/2.3.9.png)
* Chờ trạng thái chuyển sang **Complete**

![tgw](/public/images/2.prepare/2.3.10.png)
3. Kết nối tới Server1 và Server2 và ping giữa 2 server để kiểm tra peering đã hoạt động hay chưa
* Trong giao diện **EC2**, chọn **Instances** từ bảng điều khiển bên trái, chọn ô vuông **server1 -> Connect**
![tgw](/public/images/2.prepare/2.3.11.png)
* Trong giao diện **Connect to instance** , chọn **EC2 Instance Connect -> Connect using EC2 Instance Connect -> Connect**
![tgw](/public/images/2.prepare/2.3.12.png)
* Connect thành công và ping thành công tới ip private của **server2**
![tgw](/public/images/2.prepare/2.3.16.png)
* Làm tương tự Connect tới **server2** và ping thành công tới ip private của **server1**
![tgw](/public/images/2.prepare/2.3.15.png)

### Tại tài khoản DevUser thuộc Region Singapore
Tải xuống mẫu để sử dụng [Template2.yaml](transitgw2.yaml)
1. Tạo **CloudFormation**
* Làm tương tự các bước như tài khoản **root**
![tgw](/public/images/2.prepare/2.3.17.png)
2. Kết nối tới **Server3** và **Server4** và ping giữa 2 server để kiểm tra peering đã hoạt động hay chưa 
* Làm tương tự các bước như ở tài khoản **root**
![tgw](/public/images/2.prepare/2.3.18.png)
![tgw](/public/images/2.prepare/2.3.19.png)
![tgw](/public/images/2.prepare/2.3.20.png)
* Connect thành công và ping thành công tới ip private của **server4**
![tgw](/public/images/2.prepare/2.3.21.png)
## Triển khai peering Cross-region Cross-Account
### Tạo kết nối peering 
1. Tại tài khoản **root** 
* Trong giao diện **VPC**, chọn **Transit gateway attachments** từ bảng điều khiển bên trái, chọn **Create transit gateway attachment**
![tgw](/public/images/2.prepare/2.3.22.png)
* Nhập **Name tag** : ```tga3```
* Chọn **Transit gateway ID**
* Chọn **Attachment type** : **Peering Connection**
* Chọn **Account** : **Other account**
![tgw](/public/images/2.prepare/2.3.23.png)
* Sao chép **Account Id** từ tài khoản **DevUser ** 
 
  
![tgw](/public/images/2.prepare/2.3.24.png)
* Sao chép **Transit gateway id** từ tài khoản **DevUser**
![tgw](/public/images/2.prepare/2.3.25.png)
* Chọn **Region** : **ap-southeast-1** và nhập thông tin vừa sao chép vào -> **Create transit gateway attachment**
![tgw](/public/images/2.prepare/2.3.26.png)
* Tạo thành công và thấy trạng thái là **Initiating Request** 
![tgw](/public/images/2.prepare/2.3.27.png)
2. Tại tài khoản **DevUser**
* Trong giao diện **VPC**, chọn **Transit gateway attachments** ở bảng điều khiển bên trái, chọn ô vuông attachment với trạng thái **Pending Acceptance** -> **Actions -> Accept transit gateway attachment**
![tgw](/public/images/2.prepare/2.3.28.png)
* **Accept**
![tgw](/public/images/2.prepare/2.3.29.png)
* Chờ cho tới khi việc accept hoàn tất và trạng thái chuyển sang **Available**

![tgw](/public/images/2.prepare/2.3.30.png)
3. Tại tài khoản **root**, cấu hình ****Transit gateway route tables****
* Trong VPC , chọn **Transit gateway route tables** từ bảng điều khiển bên trái, chọn ô vuông **route table** mặc định -> **Create static route**
![tgw](/public/images/2.prepare/2.3.31.png)
* Nhập **CIDR** : ```10.2.0.0/16```
* **Type: Active**
* **Choose attachment**: chọn **tga3**
* **Create static route**
![tgw](/public/images/2.prepare/2.3.32.png)
* Làm tương tự
![tgw](/public/images/2.prepare/2.3.33.png)
* Tạo thành công
![tgw](/public/images/2.prepare/2.3.34.png)
4. Tại tài khoản **DevUser**, cấu hình **Transit gateway route tables**
* Làm tương tự như bước 3
![tgw](/public/images/2.prepare/2.3.39.png)
![tgw](/public/images/2.prepare/2.3.40.png)
![tgw](/public/images/2.prepare/2.3.41.png)

5. Tại tài khoản **root**, cấu hình **Route tables**
* Trong **VPC,** chọn **Route tables**từ bảng điều khiển bên trái, chọn ô vuông **RTBpubsubvpc1 -> Routes -> Edit routes**
![tgw](/public/images/2.prepare/2.3.35.png)
* Thêm 2 routes như sau -> **Save changes**
  
![tgw](/public/images/2.prepare/2.3.36.png)
* Làm tương tự với **RTBpubsubvpc2**
![tgw](/public/images/2.prepare/2.3.37.png)
![tgw](/public/images/2.prepare/2.3.38.png)
6. Tại tài khoản **DevUser**, cấu hình **Route tables**
* Làm tương tự như bước 5
![tgw](/public/images/2.prepare/2.3.42.png)
![tgw](/public/images/2.prepare/2.3.43.png)
![tgw](/public/images/2.prepare/2.3.44.png)
![tgw](/public/images/2.prepare/2.3.45.png)
7. Kiểm tra kết quả
* Từ **server4** ping thành công tới ip private của **server1**
![tgw](/public/images/2.prepare/2.3.46.png)
* Từ **server3** ping thành công tới ip private của **server1**
![tgw](/public/images/2.prepare/2.3.47.png)
* Từ **server2** ping thành công tới ip private của **server3** và **server4**
![tgw](/public/images/2.prepare/2.3.48.png)











