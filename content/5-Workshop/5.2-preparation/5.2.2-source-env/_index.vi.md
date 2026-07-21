---
title: "Chuẩn bị source code và biến môi trường"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.2.2. </b> "
---

#### Cấu trúc source code

Project gồm hai phần chính:

```text
frontend/
backend/
```

Trong `backend/` có các Lambda:

```text
upload_cv
analyze_cv
profile_api
history_api
create_interview
submit_answer
polly_speech
transcribe_audio
admin_api
```

#### Biến môi trường frontend

File `frontend/.env` cần có các endpoint API và Cognito config:

```text
VITE_UPLOAD_CV_API_URL=https://<api-id>.execute-api.<region>.amazonaws.com/<stage>/upload_cv
VITE_ANALYZE_CV_API_URL=https://<api-id>.execute-api.<region>.amazonaws.com/<stage>/analyze_cv
VITE_PROFILE_API_URL=https://<api-id>.execute-api.<region>.amazonaws.com/<stage>/profile
VITE_HISTORY_API_URL=https://<api-id>.execute-api.<region>.amazonaws.com/<stage>/history
VITE_INTERVIEW_API_BASE_URL=https://<api-id>.execute-api.<region>.amazonaws.com/<stage>
VITE_VOICE_API_BASE_URL=https://<api-id>.execute-api.<region>.amazonaws.com/<stage>
VITE_ADMIN_API_BASE_URL=https://<api-id>.execute-api.<region>.amazonaws.com/<stage>
VITE_COGNITO_DOMAIN=https://<domain>.auth.<region>.amazoncognito.com
VITE_COGNITO_CLIENT_ID=<app-client-id>
VITE_COGNITO_REDIRECT_URI=http://localhost:5173
VITE_COGNITO_LOGOUT_URI=http://localhost:5173
VITE_COGNITO_SCOPES=openid email profile phone
```

#### Kiểm tra local

```bash
cd frontend
npm install
npm run dev
```

Mở `http://localhost:5173` để kiểm tra giao diện trước khi deploy lên Amplify.
