---
title : "Giới thiệu"
date :  2025-12-01 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### Giới thiệu về VPC Endpoint

+ VPC Endpoint là một thiết bị ảo trong VPC, cho phép tài nguyên nội bộ (EC2, Lambda, CodeBuild, CodePipeline…) truy cập các dịch vụ AWS mà không cần đi qua Internet công cộng. Điều này giúp giảm rủi ro, tăng tính bảo mật và đảm bảo độ sẵn sàng cao.
+ Với Gateway Endpoint, các dịch vụ như Amazon S3 có thể được truy cập trực tiếp từ VPC mà không qua Internet.
+ Với Interface Endpoint (AWS PrivateLink), các dịch vụ như Security Hub, ECR API, SNS, hoặc CodeGuru Reviewer có thể được truy cập riêng tư giữa các dịch vụ trong AWS, giúp pipeline DevSecOps hoạt động an toàn và ổn định ngay cả khi không mở Internet outbound.

#### Tổng quan về workshop

+ Pipeline sử dụng một VPC duy nhất, trong đó các dịch vụ CI/CD và bảo mật được kết nối nội bộ thông qua VPC Endpoint:
+ **Security VPC** là nơi đặt các tài nguyên chính của pipeline như CodeBuild, Lambda phục vụ việc phân tích, gateway endpoint để truy cập S3, và interface endpoint để kết nối với Security Hub, ECR, CodeGuru Reviewer, SNS,… VPC này mô phỏng môi trường cloud thực tế, nơi mọi hoạt động scan – build – phân tích đều được xử lý trong mạng riêng tư.
+ **Trong pipeline, CodeBuild** sẽ lần lượt quét lỗ hổng trong image/container bằng Trivy , uét bảo mật Python/JS bằng Bandit , phân tích chất lượng mã nguồn với SonarQube , ẩy kết quả cảnh báo lên AWS Security Hub ,gửi cảnh báo real-time qua SNS

![overview](/images/5-Workshop/5.1-Workshop-overview/diagram1.png)
