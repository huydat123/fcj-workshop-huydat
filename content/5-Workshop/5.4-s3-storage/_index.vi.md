---
title: "Triển khai Amazon S3"
date: 2026-07-21
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

#### Mục tiêu

Amazon S3 lưu các file không phù hợp để lưu trực tiếp trong database: CV, audio câu hỏi, audio câu trả lời và transcript.

![Storage model](/images/5-Workshop/vertex-intervai/storage-model.svg)

#### Cấu trúc object

```text
cv/{userId}/{cvId}.{extension}
voice/questions/{userId}/{interviewId}/{questionIndex}.mp3
voice/answers/{userId}/{interviewId}/{questionIndex}.webm
voice/transcripts/{jobName}.json
```

S3 bucket được dùng bởi `upload_cv`, `analyze_cv`, `polly_speech`, `transcribe_audio` và một số chức năng admin.
