---
title : "Lambda-and-notification"
date : 2025-12-01
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

### Lambda Processing + Notification

### API Gateway → Lambda
API Gateway receives webhook from SonarQube and passes payload to Lambda.

Lambda does:
1. Parse data from SonarQube.
2. Format message (project, error type, severity).
3. Send content to SNS topic.

![API](/images/5-Workshop/5.4-lambda-and-notification/api.png)

![API2](/images/5-Workshop/5.4-lambda-and-notification/api-gateway.png)

### SNS Notifications
SNS sends email to dev team:
- Report security errors.
- Report code errors.
- Report Quality Gate failures.
- Link directly to SonarQube dashboard.

![SNS](/images/5-Workshop/5.4-lambda-and-notification/SNS.png)

Benefits:
- Dev knows errors immediately.
- Reduced debugging time.
- Increase software quality and safety.
