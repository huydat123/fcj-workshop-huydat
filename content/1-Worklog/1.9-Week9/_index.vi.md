---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9: Phát triển phiên phỏng vấn AI và lưu câu trả lời

* Xây dựng luồng tạo phiên phỏng vấn AI dựa trên CV đã phân tích.
* Tạo API nhận câu trả lời, chấm điểm và lưu kết quả.
* Thiết kế dữ liệu lịch sử phỏng vấn để dùng cho trang History và Result.

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 1 | - Xây dựng Lambda analyze_cv đọc CV từ S3 và gọi Amazon Bedrock. | 15/06/2026 | 15/06/2026 | Amazon Bedrock Documentation |
| 2 | - Xây dựng Lambda create_interview sinh bộ câu hỏi phỏng vấn. | 16/06/2026 | 16/06/2026 | Project Backend Notes |
| 3 | - Thiết kế cấu trúc lưu questions, answers, attempts và score trong bảng Interviews.<br>- Chuẩn bị dữ liệu cho màn hình AI Interview. | 17/06/2026 | 18/06/2026 | DynamoDB Documentation |
| 4 | - Xây dựng Lambda submit_answer để chấm điểm câu trả lời và lưu feedback. | 19/06/2026 | 19/06/2026 | AWS Lambda Documentation |
| 5 | - Kiểm thử flow upload CV, analyze CV, create interview và submit answer. | 20/06/2026 | 20/06/2026 | Postman Collection |

### Kết quả đạt được tuần 9:

* Tạo được phiên phỏng vấn AI dựa trên dữ liệu CV.
* API chấm điểm câu trả lời đã lưu được answers, attempts và score.
* Hoàn thành nền tảng dữ liệu cho History và Result.
