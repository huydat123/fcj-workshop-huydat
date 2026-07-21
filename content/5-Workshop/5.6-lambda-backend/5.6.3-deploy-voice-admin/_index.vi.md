---
title: "Deploy voice và admin Lambda"
date: 2026-07-21
weight: 3
chapter: false
pre: " <b> 5.6.3. </b> "
---

#### Deploy `polly_speech`

```text
backend/polly_speech/lambda_function.py
```

Biến môi trường:

```text
VOICE_BUCKET=talent-graph-ai-storage-huydat
POLLY_VOICE_ID=Joanna
POLLY_ENGINE=standard
PRESIGNED_URL_EXPIRES_SECONDS=900
```

IAM cần `polly:SynthesizeSpeech`, `s3:PutObject`.

#### Deploy `transcribe_audio`

```text
backend/transcribe_audio/lambda_function.py
```

Biến môi trường:

```text
VOICE_BUCKET=talent-graph-ai-storage-huydat
TRANSCRIBE_LANGUAGE_CODE=en-US
TRANSCRIBE_OUTPUT_PREFIX=voice/transcripts
```

IAM cần `transcribe:StartTranscriptionJob`, `transcribe:GetTranscriptionJob`, `s3:PutObject`, `s3:GetObject`.

#### Deploy `admin_api`

```text
backend/admin_api/lambda_function.py
```

Admin API cần quyền đọc/ghi phù hợp trên `Users`, `CVs`, `Interviews`. Nếu có chức năng khóa user bằng Cognito, Lambda role cần thêm quyền Cognito như `cognito-idp:AdminDisableUser` và `cognito-idp:AdminEnableUser`.
