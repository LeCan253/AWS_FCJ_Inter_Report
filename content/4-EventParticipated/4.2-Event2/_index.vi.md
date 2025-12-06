---
title: "Event 2"
date: 2025-09-30
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# Báo cáo tổng kết: “AWS Cloud Mastery Series #2”

### Mục tiêu sự kiện

- Hiểu tư duy và văn hóa DevOps  
- Xây dựng pipeline CI/CD với các dịch vụ DevOps của AWS  
- Ứng dụng Infrastructure as Code (IaC)  
- Triển khai container, giám sát hệ thống và quan sát toàn diện  

### Các điểm nổi bật

#### Tư duy DevOps & Nền tảng văn hóa
Sự kiện mở đầu bằng phần tóm tắt nội dung AI/ML buổi trước, sau đó chuyển sang DevOps — nhấn mạnh:

- Tinh thần hợp tác và trách nhiệm chung giữa các nhóm kỹ thuật  
- Tự động hóa quy trình, cải tiến liên tục, vòng phản hồi nhanh  
- Các chỉ số DevOps quan trọng: DORA, MTTR, tần suất triển khai  

Phần này giúp làm rõ vì sao DevOps là trọng tâm của tổ chức kỹ thuật hiện đại.

#### Dịch vụ DevOps của AWS – CI/CD Pipeline
Sự kiện giới thiệu hệ thống công cụ DevOps trên AWS:

**Quản lý mã nguồn:**  
AWS CodeCommit và chiến lược làm việc với Git như GitFlow, trunk-based development  

**Build & Kiểm thử:**  
Cấu hình CodeBuild, kiểm thử đơn vị và kiểm thử tích hợp  

**Triển khai:**  
- Blue/green deployment với CodeDeploy  
- Canary và rolling update để đảm bảo an toàn sản xuất  

**Điều phối pipeline:**  
CodePipeline để tự động hóa toàn bộ quy trình CI/CD  

**Demo thực tế:**  
Thiết lập pipeline từ commit → build → deploy, cho thấy mức độ tối ưu khi tự động hóa.

#### Infrastructure as Code (IaC)
Phần chuyên sâu về IaC với AWS:

**AWS CloudFormation:**  
Sử dụng template, quản lý stack và theo dõi drift  

**AWS CDK:**  
- Các construct cấp cao  
- Mẫu cấu hình có thể tái sử dụng  
- Hỗ trợ đa ngôn ngữ (TS, Python, Java…)  

**Demo:**  
So sánh triển khai hạ tầng bằng CloudFormation và CDK  

**Thảo luận:**  
Khi nào nên dùng CloudFormation, khi nào CDK phù hợp hơn  

### Những điểm rút ra

#### Tư duy DevOps
- **Ưu tiên tự động hóa:** giảm thao tác thủ công  
- **Triển khai liên tục:** đẩy nhỏ, đẩy thường xuyên để giảm rủi ro  
- **Ra quyết định dựa trên dữ liệu:** sử dụng DORA, MTTR…  

#### Kiến trúc kỹ thuật
- **CI/CD:** quy trình triển khai đáng tin cậy  
- **IaC:** hạ tầng nhất quán, dễ kiểm soát và version control  
- **Container:** lựa chọn giữa ECS, EKS và App Runner  
- **Observability:** quan sát toàn hệ thống bằng log/metric/trace  

#### Chiến lược hiện đại hóa
- Áp dụng microservices + container hóa  
- Chuẩn hóa hạ tầng bằng IaC  
- Tăng độ an toàn triển khai với canary, blue/green, automated testing  
- Cải thiện xử lý sự cố nhờ quan sát và postmortem rõ ràng  

### Ứng dụng vào công việc
- Thiết lập CI/CD bằng CodePipeline, CodeBuild, CodeDeploy  
- Dùng IaC cho mọi môi trường để tránh cấu hình thủ công  
- Container hóa ứng dụng, cân nhắc ECS/EKS/App Runner  
- Tạo dashboard CloudWatch và kích hoạt X-Ray tracing  
- Áp dụng DevOps: feature flags, A/B testing, rollback tự động  

### Trải nghiệm sự kiện

#### Học hỏi từ chuyên gia AWS
Diễn giả chia sẻ hành trình DevOps thực tế từ startup đến enterprise, làm rõ lợi ích của continuous delivery và tự động hóa.

#### Demo kỹ thuật trực quan
- Trọn vẹn pipeline CI/CD  
- IaC bằng CloudFormation & CDK  
- Triển khai container trên ECS/EKS/App Runner  
- Cài đặt hệ thống quan sát với CloudWatch/X-Ray  

#### Khám phá công cụ container & observability
Học cách Docker tăng tốc microservices  
Hiểu vai trò của ECR trong bảo mật container  
Xây dựng dashboard và phân tích trace hệ thống phân tán  

#### Best Practices & Ví dụ thực tế
Phân tích sự cố, root cause, postmortem  
Chia sẻ DevOps journey trong doanh nghiệp  
Khẳng định vai trò của feature flags và triển khai tự động  

#### Bài học rút ra
- DevOps là văn hóa + tự động hóa, không chỉ là công cụ  
- IaC rất cần thiết để mở rộng nhanh và chính xác  
- Container & CI/CD giúp tăng tốc độ phát hành  
- Observability là chìa khóa của độ tin cậy hệ thống  
