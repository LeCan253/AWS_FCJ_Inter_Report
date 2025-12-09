---
title: "Blog 2"
date: 2025-09-30
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# Bảng thông tin real-time từ cơ sở dữ liệu nguồn tới kho dữ liệu đám mây trên AWS

**Tác giả:** Ofir Eshel  
**Ngày:** 27/02/2025  
**Danh mục:** Amazon Aurora • Amazon EC2 • Amazon QuickSight • Amazon Redshift • AWS DMS • IAM • Secrets Manager • Kinesis • RDS MySQL • Serverless • Technical Guide  

---

## 1. Giới thiệu

Các tổ chức ngày nay cần các bảng điều khiển (dashboard) **thời gian thực hoặc gần thời gian thực** để hiển thị dữ liệu cho khách hàng mà không làm ảnh hưởng đến hệ thống cơ sở dữ liệu sản xuất. Bài viết trình bày kiến trúc AWS end-to-end giúp truyền dữ liệu thay đổi (CDC) từ database nguồn lên kho dữ liệu đám mây và trực quan hóa bằng Amazon QuickSight, với độ trễ thấp và không tác động hiệu năng hệ thống.

---

## 2. Kiến trúc tổng quan

Giải pháp giả định hệ thống có nhiều văn phòng ghi nhận lượt truy cập và muốn hiển thị:

- **Số người đang chờ**
- **Thời gian chờ hiện tại**
- **Dashboard nhúng vào website**
- **Khai thác dữ liệu BI trên kho dữ liệu**
- **Không tải nặng lên database nguồn**

### Thành phần chính:

- **AWS DMS** – thu nhận thay đổi dữ liệu (CDC) từ RDS MySQL  
- **Kinesis Data Streams** – truyền dữ liệu streaming  
- **Amazon Redshift Serverless** – phân tích & lưu trữ dạng kho dữ liệu  
- **Amazon QuickSight** – hiển thị dashboard real-time  

---

## 3. Điều kiện tiên quyết

- Tài khoản AWS có quyền sử dụng các dịch vụ trên
- Kiến thức cơ bản về AWS Console
- Hiểu về database, VPC, IAM

---

## 4. Cấu hình cơ sở dữ liệu nguồn (RDS MySQL)

1. Tạo RDS MySQL (db.t4g.micro).  
2. Bật **IAM Database Authentication**.  
3. Khởi chạy EC2 Windows để cài **MySQL Workbench**.  
4. Cấu hình Security Group:
   - EC2 → outbound 3306 → SG RDS
   - RDS → inbound 3306 → SG EC2
5. Cài MySQL Workbench và kết nối RDS bằng IAM.  
6. Bật CDC:
   - Tạo Parameter Group  
   - `binlog_format = ROW`  
   - `binlog_row_image = FULL`
7. Gán Parameter Group vào DB và **reboot**.  
8. Tạo schema `anycounty` và bảng dữ liệu demo.

---

## 5. Cấu hình Kinesis Data Streams

1. Tạo stream mới tên: **streamforrds**  
2. Chọn chế độ **On-demand** để tự động scale.

---

## 6. Cấu hình AWS DMS cho CDC

1. Tạo **subnet group** cho DMS.  
2. Tạo **Replication Instance** loại `dms.t3.micro`.  
3. Tạo **Secrets Manager** chứa user/password database.  
4. Tạo **endpoint nguồn** (RDS MySQL).  
5. Tạo **IAM Role** cho DMS đọc Secrets Manager.  
6. Tạo **endpoint đích** (Kinesis).  
7. Tạo và chạy **CDC replication task** cho schema `anycounty`.  
8. Kiểm tra dữ liệu đang stream vào Kinesis Viewer.

---

## 7. Cấu hình Amazon Redshift Serverless

1. Tạo IAM Role để Redshift đọc dữ liệu Kinesis.  
2. Tạo Redshift Serverless Namespace + Workgroup.  
3. Bật:
   - Private connectivity  
   - VPC endpoint đến Redshift  
4. Cho phép IP QuickSight (`52.23.63.224/27`) truy cập cổng 5439.

### Tạo schema và view trong Redshift

```sql
CREATE EXTERNAL SCHEMA kds
FROM KINESIS
IAM_ROLE '<role-arn>';
