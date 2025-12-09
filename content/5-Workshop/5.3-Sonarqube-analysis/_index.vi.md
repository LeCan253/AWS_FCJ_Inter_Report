---
title : "Sonarqube-analysis"
date :  2025-12-01 
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

### SonarQube Analysis Architecture

### Sonar Scanner → SonarQube
Trong giai đoạn build, Sonar Scanner thực hiện:
- Phân tích chất lượng code.
- Phát hiện bug.
- Phát hiện lỗ hổng bảo mật (Security Hotspots, Vulnerabilities).
- Tính toán code smell, độ phức tạp, duplication.

![Sonar](/images/5-Workshop/5.3-sonarqube-analysis/SonarQubeNotifier.png)

Kết quả được gửi tới:
- **SonarQube Server (EC2)**  
- SonarQube xử lý, lưu kết quả vào database của nó.

![EC2](/images/5-Workshop/5.3-sonarqube-analysis/EC2.png)

### Webhook Trigger
Khi quá trình phân tích hoàn tất:
- SonarQube gọi HTTP POST tới API Gateway endpoint.
- Payload chứa:
  - Tên project
  - Trạng thái Quality Gate (Pass/Fail)
  - Summary lỗi (bugs, vulnerabilities, code smells,…)

