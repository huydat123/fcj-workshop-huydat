---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10: API hồ sơ người dùng và lịch sử hoạt động

* Xây dựng API hồ sơ người dùng để lưu thông tin cá nhân.
* Hoàn thiện luồng lưu câu trả lời và kết quả đánh giá phỏng vấn.
* Sửa lỗi tích hợp giữa frontend và backend trong các luồng chính.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | - Xây dựng Lambda profile_api với GET/POST profile vào bảng Users. | 22/06/2026 | 22/06/2026 | DynamoDB Documentation |
| 2 | - Bổ sung dữ liệu activity/history phục vụ dashboard và history. | 23/06/2026 | 23/06/2026 | Project Data Notes |
| 3 | - Kiểm tra việc lưu answers, feedback, score và final result.<br>- Sửa lỗi dữ liệu thiếu trong bản ghi Interviews. | 24/06/2026 | 24/06/2026 | Project Backend Notes |
| 4 | - Kết nối frontend service profileApi, interviewApi với endpoint thật. | 25/06/2026 | 26/06/2026 | Frontend Source Code |
| 5 | - Kiểm thử lại flow người dùng từ upload CV đến xem kết quả. | 27/06/2026 | 27/06/2026 | Manual Test Checklist |

### Kết quả đạt được tuần 10:

* Hoàn thành API hồ sơ người dùng cơ bản.
* Dữ liệu câu trả lời và đánh giá được lưu đầy đủ hơn trong Interviews.
* Frontend bắt đầu sử dụng dữ liệu backend cho dashboard, history và result.
