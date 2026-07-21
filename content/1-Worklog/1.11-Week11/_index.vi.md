---
title: "Worklog Tuần 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu tuần 11: Hoàn thiện hồ sơ, lịch sử CV và tối ưu web

* Hoàn thiện API cập nhật thông tin cá nhân và đọc lịch sử CV/phỏng vấn.
* Tối ưu tốc độ và trải nghiệm frontend khi có nhiều dữ liệu.
* Sửa lỗi đồng bộ dữ liệu giữa localStorage fallback và dữ liệu AWS.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | - Hoàn thiện POST profile để cập nhật fullname, email, phone và avatar. | 29/06/2026 | 29/06/2026 | Profile API Notes |
| 2 | - Xây dựng luồng lấy danh sách CV và phỏng vấn từ DynamoDB. | 30/06/2026 | 30/06/2026 | DynamoDB Query Documentation |
| 3 | - Sửa dashboard để hiển thị nhiều CV, chọn CV và xem chi tiết tương ứng. | 01/07/2026 | 01/07/2026 | Frontend Source Code |
| 4 | - Tối ưu các service frontend và xử lý fallback localStorage.<br>- Kiểm tra dữ liệu đồng bộ giữa nhiều trang. | 02/07/2026 | 03/07/2026 | React/Vite Documentation |
| 5 | - Kiểm tra hiệu năng và xử lý lỗi giao diện trên các kích thước màn hình. | 04/07/2026 | 04/07/2026 | Manual Test Checklist |

### Kết quả đạt được tuần 11:

* Hồ sơ người dùng có thể cập nhật và hiển thị dữ liệu phù hợp hơn.
* Dashboard, Upload CV, History và Result dùng dữ liệu nhất quán hơn.
* Cải thiện tốc độ và giao diện khi hệ thống có nhiều CV/phỏng vấn.
