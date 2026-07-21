---
title: "Tạo User Pool và App Client"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.3.1. </b> "
---

#### Tạo User Pool

1. Vào **Amazon Cognito** -> **User pools**.
2. Chọn **Create user pool**.
3. Ở phần sign-in options, chọn **Email**.
4. Bật các thuộc tính cần dùng:
   * `email`
   * `name`
   * `phone_number`
5. Chọn gửi mã xác nhận qua email.
6. Tạo User Pool.

#### Tạo App Client

1. Trong User Pool, mở **App clients**.
2. Chọn **Create app client**.
3. Chọn app type cho web application.
4. Không bật client secret nếu frontend là SPA React.
5. Copy lại **App client ID** để dùng cho biến:

```text
VITE_COGNITO_CLIENT_ID=<app-client-id>
```

#### Kiểm tra

* User Pool ID có dạng `ap-southeast-1_xxxxx`.
* App Client ID đã được lưu lại.
* Email verification hoạt động khi tạo user mới.
