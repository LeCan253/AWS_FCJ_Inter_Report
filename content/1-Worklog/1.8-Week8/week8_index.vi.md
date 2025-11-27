---
title: "Worklog Tuần 8"
date: 2025-10-27
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

* Chuẩn bị và cài đặt tài nguyên làm workshop.

Tìm hiểu về:
* Các khái niệm nền tảng của Serverless Computing
* Thực hành xây dựng Lambda function được kích hoạt bởi sự kiện từ S3
* Cách tương tác và lưu trữ dữ liệu vào DynamoDB thông qua Lambda

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | **Nhiệm vụ**:  Chuẩn bị và cài đặt tài nguyên làm workshop. <br>&emsp; + Tải Hugo Theme<br>&emsp; + Tải Snagit <br>&emsp; + Tải Active Presenter <br>&emsp; + Tải Draw.io                                                                   | 27/10/2025   | 27/10/2025      | <https://van-hoang-kha.github.io/1-introduce/> |
| 3   | **Nhiệm vụ**:  + xem lại lý thuyết Week5:  Amazon ECS and Fargate **Thực hành:** <br>&emsp;   Xem và nắm rõ lại lý thuyết Week 5 ở web AWS Special Force Portal (đầy đủ hơn trên youtobe).        | 28/10/2025   | 28/10/2025      | <> |
| 4   |  **Nhiệm vụ**:  + xem lại lý thuyết Week 6: Observability & Cost Management **Thực hành:** <br>&emsp;   + Xem và nắm rõ lại lý thuyết Week 6 ở web AWS Special Force Portal (đầy đủ hơn trên youtobe). | 29/10/2025   | 29/10/2025      |  <> |
| 5   |   **Nhiệm vụ**:  + xem lại lý thuyết Week 7: Migrate & Modernize with AWS **Thực hành:** <br>&emsp;   + Xem và nắm rõ lại lý thuyết Week 7 ở web AWS Special Force Portal (đầy đủ hơn trên youtobe).         | 30/10/2025   | 30/10/2025       | |
| 6   |    **Nhiệm vụ**:  lab 78 : Serverless - Lambda tương tác với S3 và DynamoDB **Thực hành:** <br>&emsp;   + Lab 78: Serverless - Tương tác giữa Lambda với S3 và DynamoDB                                                                                  | 31/10/2025   | 31/10/2025      | <https://000078.awsstudygroup.com/vi/> |

### Kết quả đạt được tuần 8:

 Cách triển khai Hugo
* Tải các công cụ, phần mềm hỗ trợ
* Cách triển khai cấu trúc file
* Cách viết nội dung
* Các bước tiến hành hoàn thành Workshop

Tổng quan về Serverless trên AWS
* Kiến trúc Serverless
* Các thành phần chính: Lambda, S3, DynamoDB
* Use cases phổ biến

Xây dựng Lambda Function xử lý ảnh
* Tạo và cấu hình Lambda function
* Thiết lập trigger từ S3
* Xử lý resize ảnh với Lambda Layers
* Best practices về bảo mật và tối ưu

Lambda và tương tác với DynamoDB

* Tạo bảng DynamoDB với partition key và sort key
* Cấu hình IAM roles và permissions
* Thao tác CRUD cơ bản với DynamoDB SDK
* Monitoring và troubleshooting
