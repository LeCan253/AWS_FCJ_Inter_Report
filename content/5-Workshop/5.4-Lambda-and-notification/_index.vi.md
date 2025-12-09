---
title : "Lambda-and-notification"
date :  2025-12-01 
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

### Lambda Processing + Notification

### API Gateway → Lambda
API Gateway nhận webhook từ SonarQube và chuyển payload cho Lambda.

Lambda thực hiện:
1. Parse dữ liệu từ SonarQube.
2. Format message (project, loại lỗi, mức độ nghiêm trọng).
3. Gửi nội dung sang SNS topic.

![API](/images/5-Workshop/5.4-lambda-and-notification/api.png)

![API2](/images/5-Workshop/5.4-lambda-and-notification/api-gateway.png)


### SNS Notifications
SNS gửi email đến nhóm dev:
- Báo lỗi bảo mật.
- Báo lỗi code.
- Báo fail Quality Gate.
- Link trực tiếp tới dashboard SonarQube.

![SNS](/images/5-Workshop/5.4-lambda-and-notification/SNS.png)

Lợi ích:
- Dev biết lỗi ngay lập tức.
- Giảm thời gian debug.
- Tăng chất lượng và tính an toàn của phần mềm.

