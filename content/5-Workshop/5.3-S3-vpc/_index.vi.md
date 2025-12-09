---
title : "Truy cập S3 từ VPC"
date :  2025-09-30 
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

# SonarQube Analysis Architecture

### Sonar Scanner → SonarQube
Trong giai đoạn build, Sonar Scanner thực hiện:
- Phân tích chất lượng code.
- Phát hiện bug.
- Phát hiện lỗ hổng bảo mật (Security Hotspots, Vulnerabilities).
- Tính toán code smell, độ phức tạp, duplication.

Kết quả được gửi tới:
- **SonarQube Server (EC2)**  
- SonarQube xử lý, lưu kết quả vào database của nó.

### Webhook Trigger
Khi quá trình phân tích hoàn tất:
- SonarQube gọi HTTP POST tới API Gateway endpoint.
- Payload chứa:
  - Tên project
  - Trạng thái Quality Gate (Pass/Fail)
  - Summary lỗi (bugs, vulnerabilities, code smells,…)
