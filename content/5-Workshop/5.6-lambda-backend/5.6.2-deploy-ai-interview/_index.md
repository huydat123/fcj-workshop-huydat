---
title: "Deploy analyze_cv, create_interview, submit_answer"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.6.2. </b> "
---

#### Deploy `analyze_cv`

1. Create Lambda `analyze_cv`.
2. Copy code from:

```text
backend/analyze_cv/lambda_function.py
```

3. Add environment variables:

```text
CVS_TABLE=CVs
BEDROCK_MODEL_ID=apac.amazon.nova-lite-v1:0
BEDROCK_REGION=ap-southeast-1
```

4. Add PDF extraction layer if needed:

```text
backend/analyze_cv/analyze_cv_pypdf_layer.zip
```

#### Deploy `create_interview`

```text
backend/create_interview/lambda_function.py
```

Environment variables:

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

Environment variables:

```text
INTERVIEWS_TABLE=Interviews
BEDROCK_MODEL_ID=apac.amazon.nova-lite-v1:0
BEDROCK_REGION=ap-southeast-1
```

These Lambdas need `bedrock:InvokeModel` and matching DynamoDB read/write permissions.
