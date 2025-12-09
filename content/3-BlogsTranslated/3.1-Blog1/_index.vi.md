---
title: "Blog 1"
date: 2025-09-30
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Navigating the Windows 10 to 11 Migration for Amazon WorkSpaces Personal

**Tác giả:** Dan Garibay  
**Ngày:** 05/03/2025  
**Danh mục:** Amazon WorkSpaces • Desktop Streaming • End-User Computing • Technical Guide  

---

## 1. Giới thiệu

Windows 10 Enterprise sẽ đạt **End-of-Support (EOS)** vào ngày **14/10/2025**, buộc các quản trị viên end-user computing phải chuyển sang Windows 11 để duy trì hệ điều hành được hỗ trợ. Bài viết hướng dẫn quy trình chuyển đổi sang Windows 11 theo mô hình **BYOL (Bring Your Own License)** cho Amazon WorkSpaces Personal.

Khách hàng dùng Windows 10 BYOL trên **WorkSpaces Pools** chỉ cần chuyển sang image mới vì môi trường không lưu trạng thái.

---

## 2. Phạm vi áp dụng

Hướng dẫn áp dụng cho khách hàng:

- Đang chạy hoặc dự định chạy workload Windows theo mô hình BYOL.
- Không áp dụng cho các gói WorkSpaces kèm bản quyền Windows.
- Không áp dụng cho **Windows 10 LTSC 2019/2021**.

---

## 3. Khi Windows 10 EOS – Điều gì thay đổi?

- WorkSpaces Windows 10 hiện tại **vẫn hoạt động**.
- Vẫn có thể tạo WorkSpaces từ **custom bundle** cũ.
- Không thể **import image Windows 10 mới**.
- Windows 11 yêu cầu **TPM + UEFI Secure Boot**, nên không thể nâng cấp trực tiếp — phải tạo WorkSpace mới.

---

## 4. Chuẩn bị trước khi Migration

- Sao lưu toàn bộ dữ liệu khỏi ổ **C:** (ổ này sẽ bị xoá).
- WorkSpace phải tồn tại **≥ 12 giờ** để đảm bảo snapshot đã được tạo.
- Dữ liệu sau snapshot cuối cùng **không được giữ lại**.
- Người dùng phải **log out hoàn toàn** khi migration đang diễn ra.
- WorkSpaces phải ở trạng thái: **AVAILABLE**, **STOPPED**, hoặc **ERROR**.
- Khuyến nghị dùng:
  - **Amazon FSx**
  - **ProfileUnity**
  - **Microsoft FSLogix**
- Đảm bảo có đủ **địa chỉ IP** cho các WorkSpaces mới.
- Nếu dùng script → migrate theo batch **≤ 25 WorkSpaces**.

---

## 5. Lựa chọn 1: WorkSpaces Migration API (Khuyến nghị)

### Ưu điểm
- Đơn giản và nhanh chóng.
- Không cần tạo thêm hạ tầng → **không tốn chi phí**.
- Người dùng giữ nguyên **Registration Code**.

### Nhược điểm
- **Không rollback** → quá trình **một chiều**.
- Không thể khôi phục dữ liệu thiếu trên ổ C:.

### Các bước thực hiện
1. Import image Windows 11 BYOL.
2. Tạo WorkSpace Windows 11 từ image.
3. Cài đặt management agent và security agents.
4. Tạo **custom image + bundle**.
5. Khởi chạy WorkSpace test để kiểm tra.
6. Migrate người dùng theo từng nhóm nhỏ.

---

## 6. Lựa chọn 2: Tạo mới hạ tầng Windows 11 BYOL

### Ưu điểm
- Cho phép chạy song song Windows 10 & 11 → **có rollback**.
- Linh hoạt, dễ kiểm soát và thử nghiệm.
- Người dùng có thời gian tự chuyển dữ liệu.

### Nhược điểm
- Phức tạp hơn và tốn nhiều tài nguyên.
- Có thể phát sinh chi phí do chạy song song hai môi trường.

### Các bước thực hiện
1. Import image Windows 11 BYOL.
2. Tạo WorkSpace Windows 11 trong **AD Connector** mới.
3. Áp dụng cấu hình cần thiết + cài agent bảo mật.
4. Tạo **custom image & bundle**.
5. Khởi chạy các WorkSpaces Windows 11 cho người dùng.
6. Cung cấp **registration code mới**, hướng dẫn người dùng tự chuyển dữ liệu.
7. Xóa WorkSpaces Windows 10 BYOL cũ.
8. Dọn dẹp:
   - Directory Services
   - VPC không dùng
   - AD computer objects

---

## 7. Kết luận

Bài viết trình bày hai phương pháp chuyển đổi từ Windows 10 sang Windows 11 trên Amazon WorkSpaces Personal:

- **Migration API** – nhanh, đơn giản, ít chi phí nhưng không rollback.  
- **Xây mới hạ tầng** – linh hoạt, an toàn, hỗ trợ rollback nhưng phức tạp và tốn kém hơn.

Dù chọn phương pháp nào, việc **lập kế hoạch kỹ lưỡng**, sao lưu dữ liệu, và quản lý hồ sơ người dùng đúng cách sẽ đảm bảo quá trình chuyển đổi sang Windows 11 diễn ra **suôn sẻ và an toàn**.

---

## 8. Về tác giả

**Dan Garibay**  
Senior Solutions Architect – AWS End User Compute  
Chuyên môn: EC2, Microsoft, Linux  
Gia nhập AWS từ 2016, từng là Senior Support Engineer và Technical Account Manager.


