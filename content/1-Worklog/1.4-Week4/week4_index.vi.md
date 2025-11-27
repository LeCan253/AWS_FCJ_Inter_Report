---
title: "Worklog Tuần 4"
date: 2025-09-29
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Mục tiêu tuần 4:

* Thực hành về VM Import/Export, một bài tập được xây dựng dựa trên kiến thức từ các bài lab trước. Để hoàn thành bài lab này, bạn cần cài đặt sẵn AWS CLI và một môi trường ảo hóa (như VMware Workstation).
* Thực hiện việc tạo môi trường cho workshop, bao gồm việc tạo S3 bucket và tạo EC2 Instance sử dụng AMI Storage Gateway mà AWS đã cung cấp sẵn
* Amazon S3.
* Lý thuyết 
+ Share Responsibility Model
+ Amazon Identity and access management
+ Amazon Cognito
+ AWS Organization
+ AWS Identity Center
+ Amazon Key Management Service
+ AWS Security Hub

* Module 04

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | **Nhiệm vụ**: Xem và Thực hành Module 04 - Lab 14 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module04- Lab14: VM Import/Export (Để hoàn thành bài lab này, bạn cần cài đặt sẵn AWS CLI và một môi trường ảo hóa (như VMware Workstation))                                                                      | 29/09/2025   | 29/09/2025      |<https://000014.awsstudygroup.com/vi/>
| 3   | **Nhiệm vụ**: Xem và Thực hành Module 04 - Lab 24 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module04- Lab24:  tạo S3 bucket và tạo EC2 Instance sử dụng AMI Storage Gateway <br>&emsp; - Create Storage Gateway <br>&emsp; - Create File Shares <br>&emsp; - Mount File shares on On-premises machine <br>&emsp; - Clean up resources                                  | 30/09/2025   | 30/09/2025      | <https://000024.awsstudygroup.com/vi/1-prepare/> |
| 4   | **Nhiệm vụ**: Xem và Thực hành Module 04 - Lab 57 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module04- Lab57:  Hiểu về Amazon Simple Storage Service (Amazon S3) và sự khác biệt cơ bản giữa S3 Bucket và Object  | 01/10/2025   | 01/10/2025      | <https://000057.awsstudygroup.com/vi/> |
| 5   | **Nhiệm vụ**:Xem lý thuyết Module 05: 01 -> 08 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Share Responsibility Model <br>&emsp; + Amazon Identity and access management <br>&emsp; + Amazon Cognito <br>&emsp; + AWS Organization  <br>&emsp; + AWS Identity Center <br>&emsp; + Amazon Key Management Service <br>&emsp; + AWS Security Hub           | 02/10/2025   | 02/10/2025       | <https://www.youtube.com/watch?v=tsobAlSg19g&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=150> |
| 6   | **Nhiệm vụ**: + Xem và Thực hành Module 05 - Lab 18 ở Youtube AWS Study Group <br> + Xem và Thực hành Module 05 - Lab 22 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module05-LAB 18: AWS Security <br>&emsp;  + Module05-LAB 22: Tối ưu chi phí EC2 với Lambda.                                                                                       | 03/10/2025   | 03/10/2025      | <https://000022.awsstudygroup.com/vi/> <https://000018.awsstudygroup.com/vi/>|


### Kết quả đạt được tuần 4:

* Triển khai VM Import/Export 
  * VM Import/Export là một dịch vụ cho phép bạn import các máy ảo (VM) từ môi trường ảo hóa của bạn vào Amazon EC2 và ngược lại. Tính năng này cho phép bạn:

- Chuyển dịch các ứng dụng và tài nguyên hạ tầng từ môi trường ảo hóa on-premises sang Amazon EC2
- Sao lưu máy ảo của bạn vào EC2
- Tạo một kho lưu trữ các máy ảo để dự phòng và phục hồi sau sự cố

* Triển khai File Storage Gateway
  * Cách tạo Storage Gateway
  * Cách tạo File Shares
  * Cách kết nối File shares ở máy On-premise

* Amazon Simple Storage Service (Amazon S3) là một dịch vụ lưu trữ dạng đối tượng (object) cung cấp khả năng mở rộng theo yêu cầu sử dụng, đảm bảo tính khả dụng của dữ liệu, độ bảo mật và hiệu năng ở mức cao nhất.

* S3 được xây dựng để đáp ứng yêu cầu của khách hàng thuộc mọi quy mô và ngành nghề. Dịch vụ này có thể được sử dụng để lưu trữ và bảo vệ bất kỳ lượng dữ liệu nào.

* Bắt đầu với AWS Security Hub
* Sử dụng Lambda function để tối ưu hóa chi phí cho hệ thống của bạn trên môi trường AWS. Chúng ta sẽ sử dụng Lambda function để tự động bật và tắt máy chủ cho các máy chủ chỉ cần hoạt động trong vài tiếng mỗi ngày.


