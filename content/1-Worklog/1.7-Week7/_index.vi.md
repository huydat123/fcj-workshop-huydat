---
title: "Worklog Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7: Khởi tạo Backend và thiết kế Database

* Bắt đầu triển khai phần Backend và Database cho đồ án.
* Phân tích nhu cầu lưu trữ CV, hồ sơ người dùng và phiên phỏng vấn.
* Tạo S3 bucket lưu CV và kiểm tra kết nối từ Lambda.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | - Khởi tạo cấu trúc backend với các thư mục Lambda riêng. | 01/06/2026 | 01/06/2026 | Project Repository |
| 2 | - Thiết kế dữ liệu cho Users, CVs, Interviews và Profiles. | 02/06/2026 | 02/06/2026 | DynamoDB Data Modeling |
| 3 | - Tạo bảng DynamoDB với khóa userId, cvId và interviewId. | 03/06/2026 | 03/06/2026 | DynamoDB Documentation |
| 4 | - Tạo S3 bucket lưu CV theo đường dẫn cv/{userId}/{cvId}.<br>- Kiểm tra quyền truy cập S3 từ Lambda. | 04/06/2026 | 05/06/2026 | Amazon S3 Documentation |
| 5 | - Ghi chú biến môi trường và IAM permissions cần dùng cho backend. | 06/06/2026 | 06/06/2026 | IAM Documentation |

### Kết quả đạt được tuần 7:

* Hoàn thành cấu trúc backend ban đầu.
* Tạo được mô hình dữ liệu phục vụ CV, user profile và interview.
* Kết nối được Lambda với S3 để chuẩn bị chức năng upload CV.
