---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

## Giới thiệu về AWS Organization

**AWS Organizations** là dịch vụ quản lý tài khoản cho phép bạn hợp nhất nhiều tài khoản AWS thành một tổ chức do bạn tạo và quản lý tập trung. **AWS Organizations** bao gồm khả năng quản lý tài khoản và thanh toán tổng hợp cho phép bạn đáp ứng tốt hơn các nhu cầu về ngân sách, bảo mật và tuân thủ của doanh nghiệp mình. Với tư cách là quản trị viên của một tổ chức, bạn có thể tạo tài khoản trong tổ chức của mình và mời các tài khoản hiện có tham gia tổ chức.
* **AWS Organization**: Đây là tập hợp các tài khoản AWS được tổ chức lại theo một cách cụ thể, giúp bạn quản lý chúng một cách dễ dàng hơn.

* **Organizational Unit (OU)**: Một phân đơn vị trong **AWS Organization**, cho phép bạn nhóm các tài khoản lại với nhau. Mỗi OU có thể chứa nhiều OU con khác.

* **Management Account**: Đây là tài khoản quản lý có quyền cao nhất trong **AWS Organization**. Tài khoản này có thể kiểm soát tất cả các tài khoản khác và chịu trách nhiệm về việc thanh toán chi phí tổng hợp của các tài khoản thành viên.
## Giới thiệu về AWS Single-Sign-On 
**AWS IAM Identity Center (SSO)** là dịch vụ AWS được khuyên dùng để quản lý quyền truy cập của người dùng vào tài nguyên AWS. Đây là nơi duy nhất mà bạn có thể chỉ định người dùng trong lực lượng lao động của mình, còn được gọi là danh tính lực lượng lao động , quyền truy cập nhất quán vào nhiều tài khoản và ứng dụng AWS. **AWS IAM Identity Center** được cung cấp miễn phí.

Với **AWS IAM Identity Center**, bạn có thể tạo hoặc kết nối người dùng trong lực lượng lao động và quản lý tập trung quyền truy cập của họ trên tất cả các tài khoản và ứng dụng AWS của họ. Bạn có thể sử dụng quyền của nhiều tài khoản để cấp quyền truy cập cho người dùng trong lực lượng lao động của mình vào tài khoản AWS. Bạn có thể sử dụng chức năng gán ứng dụng để gán cho người dùng quyền truy cập vào các ứng dụng do khách hàng quản lý và do AWS quản lý.
## Giới thiệu về AWS Transit Gateway

Để giải quyết giới hạn của **Peering Conenction**, **AWS Transite Gateway** được dùng để kết nối các **VPC** và mạng **on-premises** thông qua một hub trung tâm. Điều này đơn giản hoá mạng và kết thúc các mối quan hệ định tuyến phức tạp. Nó hoạt động như một cloud router - mỗi kết nối mới chỉ thực hiện 1 lần.


**AWS Transit Gateway Attachment** là một công cụ để gán các subnet của từng **VPC** cần kết nối với nhau vào một **TGW** đã được khởi tạo. **Transit Gateway Attachment** hoạt động dựa trên quy mô của **Availability Zone** (AZ-level). Trong **VPC**, khi một subnet ở một **AZ** có **Transit Gateway Attachment** với một **TGW**, các subnet khác trong cùng **AZ** đều có thể kết nối tới **TGW** đó
## Giới thiệu về AWS EFS
**Amazon Elastic File System (Amazon EFS)** cung cấp khả năng lưu trữ tệp hoàn toàn linh hoạt, không cần máy chủ để bạn có thể chia sẻ dữ liệu tệp mà không cần cung cấp hay quản lý dung lượng và hiệu suất lưu trữ. **Amazon EFS** được xây dựng để mở rộng quy mô lên petabyte theo yêu cầu mà không làm gián đoạn ứng dụng, tự động tăng và thu nhỏ khi bạn thêm và xóa tệp. Vì **Amazon EFS** có giao diện dịch vụ web đơn giản nên bạn có thể tạo và đặt cấu hình hệ thống tệp một cách nhanh chóng và dễ dàng. Dịch vụ này quản lý tất cả cơ sở hạ tầng lưu trữ tệp cho bạn, nghĩa là bạn có thể tránh được sự phức tạp khi triển khai, vá lỗi và duy trì các cấu hình hệ thống tệp phức tạp.

**Amazon EFS** hỗ trợ giao thức **Network File System** phiên bản 4 (**NFSv4.1** và **NFSv4.0**), do đó, các ứng dụng và công cụ mà bạn sử dụng ngày nay hoạt động liền mạch với **Amazon EFS**. **Amazon EFS** có thể truy cập được trên hầu hết các loại phiên bản điện toán của **Amazon Web Services**, bao gồm **Amazon EC2, Amazon ECS, Amazon EKS, AWS Lambda và AWS Fargate**.

Dịch vụ này được thiết kế để có khả năng mở rộng cao, tính sẵn sàng cao và độ bền cao. **Amazon EFS** cung cấp các loại hệ thống tệp sau để đáp ứng nhu cầu về độ khả dụng và độ bền của bạn:

**Regional** (Được khuyến nghị) – Hệ thống tệp khu vực (được khuyến nghị) lưu trữ dữ liệu dự phòng trên nhiều Vùng sẵn sàng được phân tách theo địa lý trong Khu vực AWS. Việc lưu trữ dữ liệu trên nhiều Vùng sẵn sàng mang lại tính khả dụng liên tục cho dữ liệu, ngay cả khi một hoặc nhiều Vùng sẵn sàng trong Khu vực AWS không khả dụng.

**One Zone** – Hệ thống tệp một vùng lưu trữ dữ liệu trong một Vùng sẵn sàng duy nhất trong Khu vực AWS. Việc lưu trữ dữ liệu trong một Vùng sẵn sàng duy nhất cung cấp tính khả dụng liên tục cho dữ liệu. Tuy nhiên, trong trường hợp không chắc xảy ra mất mát hoặc hư hỏng toàn bộ hoặc một phần Vùng sẵn sàng, dữ liệu được lưu trữ trong các loại hệ thống tệp này có thể bị mất.
## Giới thiệu về AWS File Storage Gateway
**File Gateway** của AWS là giải pháp sao lưu và khôi phục dữ liệu **On-premises** tối ưu, hỗ trợ các giao thức tiêu chuẩn như **NFS** và **SMB**, tích hợp sâu vào **Amazon S3**. Điểm đặc biệt là việc tối ưu hóa chi phí và dung lượng, cho phép doanh nghiệp giảm bớt gánh nặng về lưu trữ **On-premises**. Thêm vào đó, bộ nhớ cache cục bộ của **File Gateway** giúp tăng cường tốc độ và giảm độ trễ, nâng cao khả năng khôi phục dữ liệu một cách nhanh chóng. Ngoài ra việc tích hợp **S3 Lifecycle Policies** cung cấp khả năng lưu trữ tự động vào các tier có chi phí thấp hơn, như **Amazon S3 Glacier**, đem lại linh hoạt và hiệu quả trong việc quản lý dữ liệu.
## Giới thiệu về DataSync
**AWS DataSync** là dịch vụ bảo mật trực tuyến giúp tự động hóa và đẩy nhanh quá trình di chuyển dữ liệu giữa không gian lưu trữ tại chỗ và dịch vụ Lưu trữ của **AWS**. **DataSync** có thể sao chép dữ liệu giữa giao thức chia sẻ Hệ thống tệp mạng (**NFS**), giao thức chia sẻ Khối thông điệp máy chủ (**SMB**), Hệ thống tệp phân tán **Hadoop (HDFS)**, vị trí lưu trữ đối tượng tự quản lý, **AWS Snowcone**, vùng lưu trữ trên Dịch vụ lưu trữ đơn giản của **Amazon** (**Amazon S3**), hệ thống tệp trên Hệ thống tệp linh hoạt của **Amazon** (**Amazon EFS**), hệ thống tệp **Amazon FSx** dành cho **Windows File Server**, hệ thống tệp **Amazon FSx** dành cho **Lustre**, hệ thống tệp **Amazon FSz** dành cho **OpenZFS** và hệ thống tệp **Amazon FSx** dành cho **NetApp ONTAP**.

**AWS DataSync** còn được dùng để truyền dữ liệu giữa các dịch vụ lưu trữ của **AWS**, giúp bạn dễ dàng sao chép, lưu trữ hoặc chia sẻ dữ liệu ứng dụng.