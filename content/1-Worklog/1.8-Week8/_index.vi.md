---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8: Xây dựng chức năng Upload CV

* Xây dựng Lambda upload_cv nhận CV dạng base64 và lưu vào S3.
* Kiểm tra định dạng PDF, DOC, DOCX và lưu metadata vào DynamoDB.
* Tạo API Upload CV và kiểm thử bằng Postman/frontend.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | - Xây dựng Lambda upload_cv xử lý file base64 từ frontend. | 08/06/2026 | 08/06/2026 | AWS Lambda Documentation |
| 2 | - Thêm kiểm tra định dạng PDF, DOC, DOCX và kích thước file. | 09/06/2026 | 09/06/2026 | Project Validation Notes |
| 3 | - Lưu CV lên S3 theo cấu trúc cv/{userId}/{cvId}.{extension}. | 10/06/2026 | 10/06/2026 | Amazon S3 Documentation |
| 4 | - Lưu metadata CV vào DynamoDB bảng CVs.<br>- Bổ sung trạng thái uploaded/analyzed cho CV. | 11/06/2026 | 12/06/2026 | DynamoDB Documentation |
| 5 | - Tạo route API Gateway và kiểm thử upload CV bằng Postman. | 13/06/2026 | 13/06/2026 | Postman Collection |

### Kết quả đạt được tuần 8:

* Hoàn thành API upload CV từ frontend lên AWS.
* CV được lưu đúng cấu trúc trong S3 và metadata được ghi vào DynamoDB.
* Phát hiện và xử lý một số lỗi về dữ liệu upload trong quá trình kiểm thử.
