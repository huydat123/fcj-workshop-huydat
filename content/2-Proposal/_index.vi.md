---
title: "Bản đề xuất"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Đề xuất đồ án Vertex-IntervAI / Talent Graph AI
## Nền tảng luyện phỏng vấn AI trên AWS Serverless

### 1. Tóm tắt tổng quan

Vertex-IntervAI là nền tảng luyện phỏng vấn ứng dụng trí tuệ nhân tạo nhằm giúp sinh viên và ứng viên chuẩn bị tốt hơn cho quá trình tuyển dụng. Thay vì chỉ luyện tập với danh sách câu hỏi chung, hệ thống bắt đầu từ CV thật của người dùng, phân tích kỹ năng và kinh nghiệm, tạo câu hỏi phỏng vấn theo vị trí mục tiêu, đánh giá câu trả lời và trả về điểm số kèm gợi ý cải thiện.

Giải pháp sử dụng frontend React + Vite và backend AWS Serverless. Các dịch vụ chính gồm Amazon Cognito để xác thực người dùng, Amazon S3 để lưu CV và audio, Amazon DynamoDB để lưu dữ liệu có cấu trúc, AWS Lambda và Amazon API Gateway để xây dựng API, Amazon Bedrock để phân tích CV và hỗ trợ AI phỏng vấn, Amazon Polly để tạo audio câu hỏi, Amazon Transcribe để chuyển giọng nói thành văn bản, Amazon CloudWatch để theo dõi log và AWS Amplify Hosting để triển khai frontend.

### 2. Vấn đề cần giải quyết

#### Thực trạng

Nhiều sinh viên và ứng viên mới đi làm luyện phỏng vấn nhưng thiếu phản hồi cá nhân hóa. Các bộ câu hỏi có sẵn trên mạng dễ tìm nhưng không phản ánh đúng CV, dự án, kỹ năng, kinh nghiệm và vị trí ứng tuyển của từng người. Việc phỏng vấn thử thủ công cũng cần mentor, thời gian và lịch hẹn, nên khó luyện tập thường xuyên.

#### Giải pháp đề xuất

Vertex-IntervAI cung cấp một quy trình luyện phỏng vấn tự phục vụ:

- Người dùng đăng ký và đăng nhập qua Amazon Cognito.
- Người dùng tải lên một hoặc nhiều file CV.
- Backend lưu file CV an toàn trong Amazon S3.
- Hệ thống phân tích CV để trích xuất kỹ năng, học vấn, dự án, kinh nghiệm và gợi ý vai trò phù hợp.
- Người dùng chọn vị trí mục tiêu và số lượng câu hỏi.
- Hệ thống tạo câu hỏi phỏng vấn dựa trên CV và vai trò đã chọn.
- Người dùng trả lời bằng văn bản hoặc microphone.
- Backend đánh giá câu trả lời, trả về điểm số, nhận xét, điểm mạnh, điểm yếu và lời khuyên.
- Người dùng có thể xem lại lịch sử phỏng vấn và kết quả.
- Admin có thể theo dõi người dùng, CV, phiên phỏng vấn, hàng đợi review, audit log và xuất dữ liệu CSV.

### 3. Mục tiêu đồ án

Đồ án hướng đến việc xây dựng một hệ thống luyện phỏng vấn AI có tính thực tế với các mục tiêu:

- Xây dựng ứng dụng web hoàn chỉnh cho upload CV, luyện phỏng vấn AI, xem kết quả, xem lịch sử và quản lý hồ sơ.
- Áp dụng kiến trúc AWS Serverless để giảm công việc quản trị hạ tầng và hỗ trợ mở rộng linh hoạt.
- Sử dụng Amazon Bedrock để phân tích CV, tạo câu hỏi phỏng vấn và đánh giá câu trả lời.
- Hỗ trợ luyện phỏng vấn bằng giọng nói với Amazon Polly và Amazon Transcribe.
- Lưu trữ thông tin người dùng, metadata CV, phiên phỏng vấn và kết quả theo cấu trúc rõ ràng.
- Cung cấp trang admin để theo dõi và quản lý dữ liệu vận hành.
- Xây dựng workshop triển khai từng bước trên AWS.

### 4. Kiến trúc giải pháp

Kiến trúc được chia thành các lớp chính: frontend, xác thực, API, lưu trữ, AI/voice và giám sát. Frontend gọi API Gateway và gửi Cognito JWT token cho các chức năng cần bảo vệ. API Gateway gọi các Lambda function, sau đó Lambda phối hợp với S3, DynamoDB, Bedrock, Polly và Transcribe để xử lý nghiệp vụ.

![Kiến trúc Vertex-IntervAI](/fcj-workshop-huydat/images/2-Proposal/vertex-intervai-architecture.svg)

### Dịch vụ AWS sử dụng

| Dịch vụ | Vai trò |
| --- | --- |
| Amazon Cognito | Đăng ký, đăng nhập, Hosted UI, xác thực JWT và phân quyền `user/admin`. |
| Amazon S3 | Lưu file CV, audio câu hỏi, audio câu trả lời và transcript. |
| Amazon DynamoDB | Lưu người dùng, metadata CV, phiên phỏng vấn, câu trả lời, điểm số và lịch sử. |
| AWS Lambda | Chạy backend cho upload CV, phân tích CV, profile, tạo phỏng vấn, chấm điểm, voice, history và admin. |
| Amazon API Gateway | Cung cấp REST API, cấu hình CORS và bảo vệ route bằng JWT authorizer. |
| Amazon Bedrock | Phân tích CV, tạo câu hỏi phỏng vấn, đánh giá câu trả lời và đưa ra gợi ý cải thiện. |
| Amazon Polly | Chuyển câu hỏi phỏng vấn thành audio. |
| Amazon Transcribe | Chuyển câu trả lời bằng giọng nói thành văn bản. |
| Amazon CloudWatch | Lưu log và hỗ trợ debug Lambda/API Gateway. |
| AWS Amplify Hosting | Build và triển khai frontend React + Vite. |

### 5. Thiết kế thành phần

| Thành phần | Trách nhiệm |
| --- | --- |
| Frontend | Cung cấp các trang login, dashboard, upload CV, interview, result, history, profile, settings và admin. |
| Xác thực | Dùng Cognito Hosted UI và App Client để quản lý phiên đăng nhập. |
| Luồng xử lý CV | Upload CV lên S3, lưu metadata vào DynamoDB và phân tích nội dung qua Lambda/Bedrock. |
| Bộ xử lý phỏng vấn | Tạo câu hỏi, nhận câu trả lời, chấm điểm và lưu kết quả. |
| Voice module | Dùng Polly để tạo audio câu hỏi và Transcribe để chuyển audio câu trả lời thành text. |
| Admin module | Cho phép admin xem người dùng, CV, phiên phỏng vấn, audit log và xuất dữ liệu. |
| Giám sát | Dùng CloudWatch Logs để theo dõi lỗi API và hành vi backend. |

### 6. Kế hoạch triển khai kỹ thuật

Workshop được chia theo từng giai đoạn triển khai dịch vụ:

1. Chuẩn bị AWS Region, cảnh báo ngân sách, source code và biến môi trường.
2. Tạo Cognito User Pool, App Client, Hosted UI domain, callback URL, logout URL và nhóm user/admin.
3. Tạo S3 bucket cho CV và audio, cấu hình CORS và IAM permission.
4. Tạo DynamoDB tables gồm `Users`, `CVs` và `Interviews`.
5. Deploy Lambda functions cho CV, profile, history, interview, voice và admin.
6. Tạo API Gateway routes, kết nối Lambda integration, cấu hình CORS và JWT authorization.
7. Bật quyền truy cập model Amazon Bedrock và kết nối vào các Lambda liên quan đến AI.
8. Cấu hình Amazon Polly và Amazon Transcribe cho tính năng voice.
9. Cấu hình biến môi trường frontend `.env` và deploy React + Vite bằng Amplify Hosting.
10. Kiểm thử luồng người dùng, luồng admin, voice, trang kết quả và lịch sử.
11. Dọn dẹp tài nguyên sau workshop để tránh phát sinh chi phí không cần thiết.

### 7. Lộ trình và mốc triển khai

| Giai đoạn | Thời gian | Kết quả |
| --- | --- | --- |
| Lập kế hoạch và nghiên cứu | Tuần 1-2 | Phân tích yêu cầu, chọn dịch vụ AWS, phác thảo kiến trúc. |
| Xác thực và lưu trữ | Tuần 3-4 | Cognito, S3, DynamoDB và cấu hình môi trường cơ bản. |
| Backend API | Tuần 5-6 | Lambda functions, API Gateway routes, CORS và JWT protection. |
| Tính năng phỏng vấn AI | Tuần 7-8 | Phân tích CV, tạo câu hỏi, chấm điểm bằng Bedrock. |
| Voice và admin | Tuần 9-10 | Polly, Transcribe, admin console, audit và export dữ liệu. |
| Deploy và kiểm thử | Tuần 11 | Amplify deployment, kiểm thử end-to-end, sửa lỗi. |
| Tài liệu và demo cuối | Tuần 12 | Nội dung workshop, trang báo cáo, demo cuối và hướng dẫn cleanup. |

### 8. Ước tính chi phí

Với quy mô workshop sinh viên và demo ít traffic, hệ thống được thiết kế theo hướng gọn nhẹ. Hầu hết dịch vụ có thể duy trì chi phí thấp nếu kiểm soát số lượng người dùng, file upload và số lần gọi AI.

| Hạng mục chi phí | Ghi chú |
| --- | --- |
| Lambda và API Gateway | Tính theo số request và thời gian chạy; thấp với traffic demo. |
| S3 | Tính theo dung lượng lưu trữ và request; nên xóa CV/audio test sau khi kiểm thử. |
| DynamoDB | Chế độ on-demand phù hợp với workload demo nhỏ. |
| Bedrock | Chi phí biến động chính; phụ thuộc số lần phân tích CV, tạo câu hỏi và chấm điểm. |
| Polly và Transcribe | Phụ thuộc thời lượng audio tạo ra và audio câu trả lời upload lên. |
| Amplify Hosting | Phụ thuộc build minutes, dung lượng lưu trữ và băng thông. |

Các biện pháp kiểm soát chi phí:

- Tạo AWS Budget alert trước khi triển khai.
- Sử dụng một AWS Region duy nhất.
- Giới hạn số lượng user test và kích thước file upload.
- Xóa CV, audio và tài nguyên test sau workshop.
- Dừng test Bedrock/Transcribe khi demo đã hoàn tất.

### 9. Đánh giá rủi ro

| Rủi ro | Ảnh hưởng | Cách giảm thiểu |
| --- | --- | --- |
| Sai callback/logout URL trong Cognito | Người dùng không đăng nhập hoặc không quay lại frontend được. | Kiểm tra URL local và URL Amplify trước khi test. |
| Cấu hình CORS hoặc JWT ở API Gateway sai | Frontend không gọi được backend API. | Test từng route bằng browser dev tools và CloudWatch Logs. |
| Chưa bật quyền model Bedrock | Chức năng AI không phân tích hoặc chấm điểm được. | Bật model access sớm và giữ fallback logic cho demo. |
| File CV/audio quá lớn | Tăng chi phí hoặc gây lỗi upload. | Giới hạn kích thước file và dọn dữ liệu test trong S3. |
| Trình duyệt chặn microphone | Luồng voice có thể lỗi khi demo. | Giữ luồng trả lời bằng text làm phương án dự phòng. |

### 10. Kết quả kỳ vọng

Sau khi hoàn thành, Vertex-IntervAI có thể cung cấp một quy trình luyện phỏng vấn AI hoàn chỉnh: người dùng đăng nhập, upload CV, nhận phân tích AI, luyện phỏng vấn, trả lời bằng văn bản hoặc giọng nói, xem điểm số và feedback, đồng thời xem lại lịch sử luyện tập. Workshop cũng tạo ra bộ tài liệu có thể tái sử dụng để triển khai hệ thống tương tự trên AWS Serverless.

