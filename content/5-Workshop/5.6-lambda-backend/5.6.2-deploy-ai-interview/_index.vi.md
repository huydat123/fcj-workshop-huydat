---
title: "Deploy analyze_cv, create_interview, submit_answer"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.6.2. </b> "
---

#### Deploy `analyze_cv`

1. Tạo Lambda `analyze_cv`.
2. Copy code từ:

```text
backend/analyze_cv/lambda_function.py
```

3. Thêm biến môi trường:

```text
CVS_TABLE=CVs
BEDROCK_MODEL_ID=apac.amazon.nova-lite-v1:0
BEDROCK_REGION=ap-southeast-1
```

4. Thêm layer đọc PDF nếu cần:

```text
backend/analyze_cv/analyze_cv_pypdf_layer.zip
```

#### Deploy `create_interview`

```text
backend/create_interview/lambda_function.py
```

Biến môi trường:

```text
INTERVIEWS_TABLE=Interviews
CVS_TABLE=CVs
BEDROCK_MODEL_ID=apac.amazon.nova-lite-v1:0
BEDROCK_REGION=ap-southeast-1
```

#### Deploy `submit_answer`

```text
backend/submit_answer/lambda_function.py
```

Biến môi trường:

```text
INTERVIEWS_TABLE=Interviews
BEDROCK_MODEL_ID=apac.amazon.nova-lite-v1:0
BEDROCK_REGION=ap-southeast-1
```

IAM của các Lambda này cần `bedrock:InvokeModel` và quyền đọc/ghi DynamoDB tương ứng.
