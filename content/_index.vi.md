---
title : "PrivateLink"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---

# Triển khai giải pháp lưu trữ lai sử dụng EFS, Filegateway và DataSync
## Tổng quan kiến trúc giải pháp
![diagram](/images/1.introduce/diagram1.png)


## Yêu cầu đặt ra
1. Trên môi trường **on-premise**
* Triển khai **File gateway** để lưu trữ dữ liệu từ **on-premise** lên **S3 File Gateway**
2. Trên môi trường Cloud 
* 4 **VPC** thuộc 2 chi nhánh ở 2 region, 2 tài khoản khác nhau sẽ kết nối với nhau và sử dụng **EFS** để lưu trữ dữ liệu cần thiết cho công việc kinh doanh

* Triển khai **DataSync** để sao chép dữ liệu tự động từ **EFS** tới **S3 File Gateway** để phục vụ người dùng **on-premise**


### Nội dung
 1. [Giới thiệu](1-Introduce/)
 2. [Triển khai môi trường VPC Cross-account và Cross-region](2-prepare/)
 3. [Triển khai EFS](3-Efs/)
 4. [Triển khai File Gateway](4-Filegw/)
 5. [Triển khai DataSync](5-Datasync/)
 6. [Dọn dẹp tài nguyên](6-Cleanup/)
