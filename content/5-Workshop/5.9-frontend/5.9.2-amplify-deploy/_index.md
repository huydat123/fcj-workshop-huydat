---
title: "Deploy with Amplify Hosting"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 5.9.2. </b> "
---

#### Deployment steps

1. Push code to GitHub.
2. Open **AWS Amplify** -> **Host web app**.
3. Select GitHub repository and branch.
4. Because the frontend is inside `frontend/`, use this build setting:

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

5. Add environment variables.
6. Click **Save and deploy**.
7. Copy the Amplify domain after deployment succeeds.

#### Update Cognito

Add the Amplify domain to:

* Allowed callback URLs
* Allowed sign-out URLs

Then redeploy frontend and test sign-in.
