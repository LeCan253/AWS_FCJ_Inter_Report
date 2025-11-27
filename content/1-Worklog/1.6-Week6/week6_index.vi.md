---
title: "Worklog Tuần 6"
date: 2025-10-13
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---


### Mục tiêu tuần 6:

* Chúng ta sẽ tận dụng AWS Glue để làm data catalogue. Amazon Athena được sử dụng để truy vấn data trong data lake và Amazon QuickSight để biểu diễn data.
* Tìm hiểu về Amazon DynamoDB.
* Tìm hiểu về AWS Glue & Amazon Athena.
* Workshop về Analytics trên AWS
* Module 07

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | **Nhiệm vụ**: Xem và Thực hành Module 07 - Lab 35 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module07-LAB 35: DataLake on AWS <br>&emsp;                        | 13/10/2025   | 13/10/2025      |<https://000035.awsstudygroup.com/vi/1-introduce/>
| 3   |  **Nhiệm vụ**: Xem và Thực hành Module 07 - Lab 39 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module07-LAB 39: Amazon DynamoDB Immersion Day                                    | 14/10/2025   | 14/10/2025      | <https://000039.awsstudygroup.com/vi/> |
| 4   | **Nhiệm vụ**: Xem và Thực hành Module 07 - Lab 40 ở Youtube AWS Study Grou <br> **Thực hành:** <br>&emsp; + Module07-LAB 40: AWS Glue & Amazon Athena  | 15/10/2025   | 15/10/2025      | <https://000040.awsstudygroup.com/vi/> |
| 5   |  **Nhiệm vụ**: Xem và Thực hành Module 07 - Lab 60 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module07-LAB 60: Làm việc với Amazon DynamoDB          | 16/10/2025   | 16/10/2025       | <https://000060.awsstudygroup.com/vi/1-using-tags> |
| 6   | **Nhiệm vụ**: Xem và Thực hành Module 07 - Lab 72 ở Youtube AWS Study Group <br> **Thực hành:** <br>&emsp; + Module07-LAB 72: Analytics on AWS workshop                                                                                    | 17/10/2025   | 17/10/2025      | <https://000072.awsstudygroup.com/vi/1-using-tags>|

### Kết quả đạt được tuần 6:
Data Lake là một thuật ngữ chuyên môn có liên quan đến Big Data (Dữ liệu lớn). Data Lake đơn giản là nơi chứa dữ liệu thô (chưa xử lý) chờ được xử lý phân tích và đưa ra các đánh giá nhận xét (insight).

Data Lake có các tính chất sau:
  * Thu thập mọi thứ – chứa tất cả dữ liệu dạng thô hoặc đã được xử lý trong khoảng thời gian dài.
  * Đa người dùng – cho phép nhiều người dùng tinh chỉnh, khám phá và làm phong phú dữ liệu.
  * Truy cập linh hoạt – hỗ trợ nhiều cách thức truy cập dữ liệu (access pattern) trên cơ sở hạ tầng dùng chung: lô (batch), tương tác, trực tuyến, tìm kiếm, trong bộ nhớ và các công cụ xử lý khác.

Tìm hiểu và DynamoDB
  * https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html

Amazon DynamoDB là một dịch vụ cơ sở dữ liệu NoSQL được quản lý hoàn toàn, cung cấp hiệu suất nhanh và có thể dự đoán được với khả năng mở rộng liền mạch. DynamoDB cho phép giảm bớt gánh nặng quản trị của việc vận hành và mở rộng cơ sở dữ liệu phân tán, cung cấp phần cứng, thiết lập và cấu hình, sao chép, vá lỗi phần mềm hoặc mở rộng cụm. DynamoDB cũng cung cấp mã hóa ở trạng thái nghỉ.

  * DynamoDB tạo các table cơ sở dữ liệu có thể lưu trữ và truy xuất bất kỳ lượng dữ liệu nào và phục vụ bất kỳ mức lưu lượng yêu cầu nào. Có thể tăng hoặc giảm quy mô công suất thông qua table của mình mà không có thời gian chết hoặc giảm hiệu suất.
  * DynamoDB cung cấp khả năng sao lưu theo yêu cầu. Nó cho phép bạn tạo bản sao lưu đầy đủ các table để lưu giữ và lưu trữ lâu dài cho các nhu cầu tuân thủ quy định.
  * Có thể tạo bản sao lưu theo yêu cầu và bật khôi phục tại thời điểm cho các table Amazon DynamoDB. Khôi phục theo thời gian giúp bảo vệ table khỏi các thao tác ghi hoặc xóa ngẫu nhiên. Với khôi phục theo thời gian, có thể khôi phục table về bất kỳ thời điểm nào trong 35 ngày qua.
  * DynamoDB cho phép tự động xóa các item đã hết hạn khỏi table giúp giảm mức sử dụng bộ nhớ và chi phí lưu trữ dữ liệu không còn phù hợp.

Workshop Analytics on AWS

* 1 Thiết kế kiến trúc Data Lake serverless (serverless data lake).
* 2 Xây dựng đường ống xử lý dữ liệu và Data Lake bằng cách sử dụng Amazon S3 để lưu trữ dữ liệu.
* 3 Sử dụng Amazon Kinesis để xử lý dữ liệu trực tiếp (real-time streaming data).
* 4 Sử dụng Amazon Kinesis Data Analytics để phân tích dữ liệu trực tiếp (real-time data analysis).
* 5 Sử dụng AWS Glue để tự động lưu trữ dữ liệu trong danh mục (catalog datasets).
* 6 Chuyển đổi dữ liệu (Data Transformation).
* 7 Chạy các script ETL tương tác trong Jupyter notebook trên AWS Glue Studio bằng cách sử dụng phiên tương tác của AWS Glue.
* 8 Sử dụng Glue Studio để chạy và giám sát các ETL jobs trên AWS Glue.
* 9 Sử dụng Glue DataBrew để chuẩn bị dữ liệu.
* 10 Sử dụng EMR để chạy job biến đổi Spark.
* 11 Tải dữ liệu lên Amazon Redshift từ Glue.
* 12 Giới thiệu về các phương pháp thiết kế tốt nhất của Amazon Redshift.
* 13 Truy vấn dữ liệu bằng Amazon Athena và trực quan hóa nó bằng Amazon QuickSight.
* 14 Dọn dẹp tài nguyên


