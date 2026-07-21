---
title: "Deploy bằng Amplify Hosting"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.9.2. </b> "
---

#### Các bước deploy

1. Push code lên GitHub.
2. Vào **AWS Amplify** -> **Host web app**.
3. Chọn GitHub repository và branch.
4. Vì frontend nằm trong `frontend/`, dùng build setting:

```yaml
version: 1
applications:
  - appRoot: frontend
    frontend:
      phases:
        preBuild:
          commands:
            - npm ci
        build:
          commands:
            - npm run build
      artifacts:
        baseDirectory: dist
        files:
          - '**/*'
      cache:
        paths:
          - node_modules/**/*
```

5. Thêm environment variables.
6. Bấm **Save and deploy**.
7. Copy domain Amplify sau khi deploy thành công.

#### Cập nhật Cognito

Thêm domain Amplify vào:

* Allowed callback URLs
* Allowed sign-out URLs

Sau đó redeploy frontend và test đăng nhập.
