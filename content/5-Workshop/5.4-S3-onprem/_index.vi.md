---
title : "Truy cập S3 từ môi trường truyền thống"
date :  2025-09-30 
weight : 4 
chapter : false
pre : " <b> 5.4. </b> "
---

# Lambda Processing + Notification

### API Gateway → Lambda
API Gateway nhận webhook từ SonarQube và chuyển payload cho Lambda.

Lambda thực hiện:
1. Parse dữ liệu từ SonarQube.
2. Format message (project, loại lỗi, mức độ nghiêm trọng).
3. Gửi nội dung sang SNS topic.

### SNS Notifications
SNS gửi email đến nhóm dev:
- Báo lỗi bảo mật.
- Báo lỗi code.
- Báo fail Quality Gate.
- Link trực tiếp tới dashboard SonarQube.

Lợi ích:
- Dev biết lỗi ngay lập tức.
- Giảm thời gian debug.
- Tăng chất lượng và tính an toàn của phần mềm.



