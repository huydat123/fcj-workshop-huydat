---
title: "Deploy upload_cv, profile_api, history_api"
date: 2026-07-21
weight: 1
chapter: false
pre: " <b> 5.6.1. </b> "
---

#### Deploy `upload_cv`

1. Create Lambda `upload_cv`.
2. Runtime: Python 3.12.
3. Copy code from:

```text
backend/upload_cv/lambda_function.py
```

4. Add environment variables:

```text
CVS_TABLE=CVs
STORAGE_BUCKET=talent-graph-ai-storage-huydat
```

5. IAM needs `s3:PutObject`, `dynamodb:PutItem`.

#### Deploy `profile_api`

```text
backend/profile_api/lambda_function.py
```

Environment variable:

```text
USERS_TABLE=Users
```

IAM needs `dynamodb:GetItem`, `dynamodb:PutItem`, `dynamodb:UpdateItem`.

#### Deploy `history_api`

```text
backend/history_api/lambda_function.py
```

Environment variables:

```text
CVS_TABLE=CVs
INTERVIEWS_TABLE=Interviews
```

IAM needs `dynamodb:Query` on `CVs` and `Interviews`.
