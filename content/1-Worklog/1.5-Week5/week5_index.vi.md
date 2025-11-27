---
title: "Worklog Tuần 5"
date: 2025-10-06
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---


### Mục tiêu tuần 5:

* Để giúp quản lý các máy ảo, ổ đĩa và các tài nguyên khác của EC2, bài lab 27 này sẽ giúp bạn thực hành gán các metadata của mỗi tài nguyên dưới dạng Tag (Thẻ) và sử dụng Resource Group.
* Đặc quyền IAM tối thiểu (IAM least privilege)
* Đặc tả chính sách IAM cùng với các điều kiện (IAM policy conditions)
* Tìm hiểu về IAM Permission Boundary.
* Tìm hiểu về AWS Key Management Service (KMS), Amazon S3, AWS CloudTrail, AWS Athena.
* Ôn lại khái niệm về IAM, tạo User/Group, Role.
* Cấp quyền truy cập cho ứng dụng của bạn có thể truy cập tới các dịch vụ của AWS.
* Module 05
* Module 06

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | **Nhiệm vụ**:Xem và Thực hành Module 05 - Lab 27 và  Lab 28 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module05-LAB 27: Quản lý tài nguyên bằng Tag và Resource Groups <br>&emsp;  + Module05-LAB 28: Quản lý truy cập vào dịch vụ EC2 Resource Tag với AWS IAM.                                                                    | 06/10/2025   | 06/10/2025      |<https://000027.awsstudygroup.com/vi/0-intro/> <https://000028.awsstudygroup.com/vi/0-intro/>
| 3   | **Nhiệm vụ**:Xem và Thực hành Module 05 - Lab 30 và Lab 33 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module05-LAB 30: GIỚI HẠN QUYỀN CỦA USER VỚI IAM PERMISSION BOUNDARY <br>&emsp;  + Module05-LAB 33: <br>&emsp; + AWS Key Management Service (KMS)  <br>&emsp; + Amazon S3 <br>&emsp; + AWS CloudTrail <br>&emsp; + AWS Athena                             | 07/10/2025   | 07/10/2025      | <https://000033.awsstudygroup.com/vi/1-introduce/> <https://000030.awsstudygroup.com/vi/1-introduce/> |
| 4   | **Nhiệm vụ**: Xem và Thực hành Module 05 - Lab 44 và Lab 48 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module05-LAB 44: IAM ( User/Group, Role) <br>&emsp;  + Module05-LAB 48: Cấp quyền cho ứng dụng truy cập dịch vụ AWS với IAM Role | 08/10/2025   | 08/10/2025      | <https://000044.awsstudygroup.com/vi/1-iam-intro/> <https://000048.awsstudygroup.com/vi/> |
| 5   | **Nhiệm vụ**: Xem và thực hành Module 06 Lab 05 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; Lý thuyết: <br>&emsp; + Database Concepts <br>&emsp; + Amazon RDS <br>&emsp; + Amazon Aurora <br>&emsp; + Amazon Elasticache <br>&emsp; + Amazon Redshift         | 09/10/2025   | 09/10/2025       | <https://www.youtube.com/watch?v=OOD2RwWuLRw&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=217> |
| 6   | **Nhiệm vụ**: Xem và thực hành Module 06 Lab 05 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module06-LAB 05: Amazon Relational Database Service (Amazon RDS)                                                                  | 10/10/2025   | 10/10/2025      | <https://000005.awsstudygroup.com/vi/>|


### Kết quả đạt được tuần 5:

* Gán các metadata của mỗi tài nguyên dưới dạng Tag (Thẻ) và sử dụng Resource Group.
* Quản lý quyền truy cập dịch vụ EC2 với Resource Tag thông qua cấu hình chi tiết của các chính sách và IAM role với quyền cụ thể. Việc sử dụng Resource Tag sẽ cực kỳ hữu ích khi chúng ta mở rộng trong việc quản trị phi tập trung.


* Triển khai ứng dụng FCJ Management với Auto Scaling Group
  * Thiết lập đầy đủ hạ tầng mạng, khởi tạo EC2 Instance và Database Instance (Amazon RDS), triển khai dữ liệu và ứng dụng web.
  * Cấu hình thành công Load Balancer + Target Group, đảm bảo khả năng phân phối tải giữa các instance.
  * Tạo và kiểm thử Auto Scaling Group, hệ thống có khả năng mở rộng và thu hẹp tự động dựa trên tải thực tế.
  * Kiểm tra và đánh giá các giải pháp scaling, đảm bảo ứng dụng hoạt động ổn định và linh hoạt.

Tại sao sử dụng IAM Permission Boundary?
+ Thông thường, khi bạn trao quyền cho các IAM user, bạn nghĩ rằng chỉ cần xây dựng chính sách quyền cho user một cách cẩn thận, bạn sẽ có thể bỏ qua bước sử dụng Permission Boundary.

+ Tuy nhiên, khi số lượng user tăng lên và những thay đổi liên tục trong vai trò công việc của các user yêu cầu bạn phải tạo ra thêm nhiều chính sách quyền mới, thì việc quản lý quyền trở nên phức tạp, từ đó tạo những lỗ hổng cho leo thang đặc quyền (privilege escalation) trong các user.

Để đơn giản hóa công tác quản lý quyền, thay vì bạn phải chỉnh sửa từng chính sách quyền, bạn có thể áp dụng Permission Boundary một cách nhanh chóng và đồng loạt để giúp bạn đóng những lỗ hổng về privilege escalation.

Ứng dụng của IAM

  + IAM không có khả năng xác thực đối với ứng dụng. Ví dụ ở hệ thống on-prem, 1 ứng dụng như phần mềm sử dụng AD làm hệ thống xác thực, thì khi chuyển lên AWS cloud sẽ cần triển khai AWS Directory Service (cài đặt & migrate).

+ IAM không có khả năng quản lý xác thực đối với hệ điều hành. Sau khi các máy chủ ở hệ thống on-prem được migrate lên EC2, việc truy cập vào EC2 có thể thông qua AD hoặc LDAP đã được extend từ hệ thống on-prem hoặc chạy standalone.

+ Công nghệ xác thực

+ AWS Management Console
CLI - công cụ scripting
AWS SDKs  
+ Một số thao tác quan trọng thường làm với IAM như: Tạo User, Group, Role, Access policy

Cấp quyền cho ứng dụng truy cập dịch vụ AWS với IAM Role
* Cách thức cấp quyền truy cập cho ứng dụng thông qua accesskey/secretaccesskey và tại sao không nên sử dụng nó.
* Cách thức cấp quyền truy cập cho ứng dụng thông qua IAM Role trên EC2.





