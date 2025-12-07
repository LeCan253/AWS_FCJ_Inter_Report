---
title: "Event 3"
date: 2025-12-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---
# Báo cáo tổng kết: “AWS CLOUD MASTER SERIES #3”

### Mục tiêu sự kiện

- Hiểu sâu hơn về trụ cột Bảo mật trong AWS Well-Architected Framework  
- Nắm vững các phương pháp bảo mật hiện đại: Zero Trust, Least Privilege, Defense in Depth  
- Xây dựng tư duy thiết kế hệ thống an toàn từ giai đoạn kiến trúc  
- Ứng dụng bảo mật vào danh tính, phát hiện mối đe dọa, mạng, dữ liệu và ứng phó sự cố  

### Các điểm nổi bật

#### Nền tảng bảo mật
Workshop giới thiệu vai trò của Security Pillar và lý do nó là nền tảng của kiến trúc an toàn.  
Các nguyên tắc quan trọng được nhấn mạnh:

- **Least Privilege** – cấp đúng quyền cần thiết  
- **Zero Trust** – luôn xác minh mọi yêu cầu  
- **Defense in Depth** – bảo mật nhiều lớp từ ngoài vào trong  

Người tham dự cũng được nhắc lại mô hình Shared Responsibility và các rủi ro bảo mật phổ biến tại Việt Nam.

#### Trụ cột 1 — Identity & Access Management (IAM)
Nội dung chính bao gồm:

- Quản lý danh tính theo hướng role-based, tránh dùng long-term credentials  
- Tập trung hóa danh tính nhân sự với IAM Identity Center  
- Tổ chức nhiều tài khoản bằng SCP và permission boundaries  
- Tăng cường bảo mật truy cập: MFA, xoay vòng credential, Access Analyzer  
- **Demo nhanh:** kiểm tra và mô phỏng quyền IAM  

#### Trụ cột 2 — Phát hiện & Giám sát
Workshop trình bày cách thiết lập hệ thống phát hiện mối đe dọa:

- CloudTrail cho giám sát cấp tổ chức  
- GuardDuty cho phân tích hành vi đe dọa  
- Security Hub tổng hợp và chuẩn hóa cảnh báo  
- Logging đa lớp: VPC Flow Logs, ALB Logs, S3 Access Logs  
- EventBridge cho cảnh báo tự động  
- Khái niệm “Detection-as-Code” giúp chuẩn hóa quy tắc giám sát  

#### Trụ cột 3 — Bảo vệ hạ tầng
Các nội dung chính:

- Thiết kế VPC an toàn với phân vùng mạng hợp lý  
- So sánh và cách chọn Security Group và NACL  
- Bảo vệ biên mạng với AWS WAF, Shield, Network Firewall  
- Kiểm soát workload trên EC2, ECS, EKS  

#### Trụ cột 4 — Bảo vệ dữ liệu
Bao gồm các chủ đề:

- Quản lý khóa và mã hóa bằng AWS KMS  
- Áp dụng mã hóa cho S3, EBS, RDS, DynamoDB  
- Quản lý secret bằng Secrets Manager và Parameter Store  
- Phân loại dữ liệu và guardrails theo tuân thủ  

#### Trụ cột 5 — Ứng phó sự cố
Người tham dự được hướng dẫn:

- Chu trình Incident Response theo AWS  
- Các playbook thường gặp: rò rỉ khóa IAM, S3 bị public, EC2 bị xâm nhập  
- Kỹ thuật cô lập tài nguyên, snapshot, thu thập bằng chứng  
- Tự động hóa IR bằng Lambda và Step Functions  

### Những điểm rút ra

#### Tư duy thiết kế bảo mật
- Bảo mật phải được đặt từ đầu, không thêm vào sau  
- Danh tính là lớp bảo mật cốt lõi  
- Luôn phải logging và giám sát liên tục  

#### Triển khai kỹ thuật
- Chuẩn hóa danh tính với IAM Identity Center  
- Bật logging và threat detection toàn tổ chức  
- Thiết kế VPC phân tách rõ ràng và bảo vệ nhiều lớp  
- Áp dụng mã hóa, KMS, xoay vòng secret nhất quán  

#### Vận hành & Quản trị
- Xây dựng playbook IR có thể lặp lại  
- Tự động hóa remediation bất cứ khi nào có thể  
- Thiết lập governance với AWS Organizations và SCP  

### Ứng dụng vào công việc

- Rà soát lại IAM theo mô hình hiện đại  
- Triển khai CloudTrail, GuardDuty, Security Hub toàn hệ thống  
- Củng cố mạng bằng segmentation và dịch vụ bảo vệ lớp biên  
- Mã hóa dữ liệu theo chuẩn và duy trì secret rotation  
- Xây dựng playbook IR tích hợp automation  

### Trải nghiệm sự kiện

#### Học hỏi từ chuyên gia AWS
Chuyên gia chia sẻ nhiều case thực tế tại Việt Nam và cách xử lý hiệu quả.

#### Demo trực quan
Người tham dự được xem mô phỏng IAM, phát hiện mối đe dọa, và tự động hóa IR.

#### Tư duy chiến lược
Security được coi là sự kết hợp giữa kỹ thuật, quy trình, văn hóa và quản trị.

#### Kết nối & giao lưu
Trao đổi trực tiếp với chuyên gia giúp hiểu rõ hơn về thách thức bảo mật doanh nghiệp.

> Workshop giúp mình nâng cao tư duy bảo mật và áp dụng thực tiễn vào việc xây dựng hệ thống an toàn, bền vững trên AWS.
