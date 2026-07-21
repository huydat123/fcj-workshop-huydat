---
title: "Proposal"
date: 2026-07-21
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Vertex-IntervAI / Talent Graph AI Proposal
## AWS Serverless AI Interview Training Platform

### 1. Executive Summary

Vertex-IntervAI is an AI-powered interview training platform that helps students and job seekers prepare for recruitment more effectively. Instead of using generic question lists, the system starts from the user's own CV, analyzes their skills and experience, generates interview questions for a selected role, evaluates answers, and returns feedback with scores and improvement suggestions.

The proposed solution uses a React + Vite frontend and an AWS Serverless backend. Core services include Amazon Cognito for authentication, Amazon S3 for CV and audio storage, Amazon DynamoDB for structured data, AWS Lambda and Amazon API Gateway for backend APIs, Amazon Bedrock for CV analysis and interview intelligence, Amazon Polly for question audio, Amazon Transcribe for speech-to-text, Amazon CloudWatch for logs, and AWS Amplify Hosting for frontend deployment.

### 2. Problem Statement

#### Current Problem

Many students and early-career candidates prepare for interviews without personalized feedback. Public question banks are easy to find, but they do not adapt to the candidate's real CV, project experience, skill level, or target job role. Manual mock interviews also require mentors, time, and repeated scheduling, which makes frequent practice difficult.

#### Proposed Solution

Vertex-IntervAI provides a self-service interview preparation workflow:

- Users sign up and sign in through Amazon Cognito.
- Users upload one or more CV files.
- The backend stores CV files securely in Amazon S3.
- The system analyzes CV content and extracts skills, education, projects, experience, and role suggestions.
- Users choose a target role and number of questions.
- The system generates interview questions based on the CV and selected role.
- Users answer by text or microphone.
- The backend evaluates answers and returns score, feedback, strengths, weaknesses, and advice.
- Users can review their interview history and results later.
- Admin users can monitor users, CVs, interviews, review queues, audit logs, and CSV exports.

### 3. Project Objectives

The project aims to deliver a practical AI interview training system with the following goals:

- Build a complete web application for CV upload, AI interview practice, result review, and profile management.
- Apply AWS Serverless architecture to reduce infrastructure management and keep the system scalable.
- Use Amazon Bedrock to support CV analysis, question generation, and answer evaluation.
- Support voice-based interview practice with Amazon Polly and Amazon Transcribe.
- Store user data, CV metadata, interview sessions, and results in a structured and reusable way.
- Provide an admin console for monitoring and operational management.
- Prepare a deployment workshop that can be followed step by step on AWS.

### 4. Solution Architecture

The architecture separates the frontend, authentication layer, API layer, storage layer, AI services, and monitoring layer. The frontend communicates with API Gateway endpoints and passes Cognito JWT tokens for protected operations. API Gateway invokes Lambda functions, which coordinate with S3, DynamoDB, Bedrock, Polly, and Transcribe.

![Vertex-IntervAI architecture](/fcj-workshop-huydat/images/2-Proposal/vertex-intervai-architecture.png)

### AWS Services Used

| Service | Purpose |
| --- | --- |
| Amazon Cognito | Sign-up, sign-in, Hosted UI, JWT authentication, and `user/admin` authorization. |
| Amazon S3 | Store uploaded CV files, generated audio, answer recordings, and transcript artifacts. |
| Amazon DynamoDB | Store users, CV metadata, interview sessions, answers, scores, and history. |
| AWS Lambda | Run backend functions for upload, CV analysis, profile, interview creation, answer scoring, voice, history, and admin operations. |
| Amazon API Gateway | Expose REST API endpoints and protect routes with JWT authorizers and CORS configuration. |
| Amazon Bedrock | Analyze CVs, generate interview questions, evaluate answers, and create improvement advice. |
| Amazon Polly | Convert interview questions into audio. |
| Amazon Transcribe | Convert candidate voice answers into text for evaluation. |
| Amazon CloudWatch | Store logs and support debugging for Lambda and API Gateway. |
| AWS Amplify Hosting | Build and deploy the React + Vite frontend. |

### 5. Component Design

| Component | Responsibility |
| --- | --- |
| Frontend | Provides login, dashboard, CV upload, interview, result, history, profile, settings, and admin pages. |
| Authentication | Uses Cognito Hosted UI and app client configuration to manage user sessions. |
| CV pipeline | Uploads CV files to S3, stores metadata in DynamoDB, and analyzes content through Lambda and Bedrock. |
| Interview engine | Generates questions, receives answers, scores responses, and stores results. |
| Voice module | Uses Polly for question audio and Transcribe for answer transcription. |
| Admin module | Allows administrators to review users, CVs, interviews, audit logs, and exported data. |
| Monitoring | Uses CloudWatch logs to trace API errors and backend behavior. |

### 6. Technical Implementation Plan

The workshop implementation is divided into service-based stages:

1. Prepare AWS Region, budget alert, source code, and environment variables.
2. Create Cognito User Pool, App Client, Hosted UI domain, callback URLs, logout URLs, and user/admin groups.
3. Create S3 buckets for CV and audio storage with CORS and IAM permissions.
4. Create DynamoDB tables for `Users`, `CVs`, and `Interviews`.
5. Deploy Lambda functions for CV, profile, history, interview, voice, and admin features.
6. Create API Gateway routes, connect Lambda integrations, configure CORS, and add JWT authorization.
7. Enable Amazon Bedrock model access and connect Bedrock to the AI-related Lambda functions.
8. Configure Amazon Polly and Amazon Transcribe for voice support.
9. Configure frontend `.env` variables and deploy the React + Vite app with Amplify Hosting.
10. Test the user flow, admin flow, voice flow, result page, and history page.
11. Clean up resources after the workshop to avoid unnecessary cost.

### 7. Timeline and Milestones

The implementation worklog covers 6 working weeks. In the overall project timeline, Worklog Week 1 starts at Project Week 7, after the initial research and proposal preparation phase.

| Project week | Worklog week | Main focus | Milestones |
| --- | --- | --- | --- |
| Week 7 |  Project initialization and architecture design | Analyze requirements, create the React project, build basic routing and page layout, design DynamoDB schemas, prepare S3 storage, define the AI workflow, and draft the AWS architecture checklist. |
| Week 8 |  Authentication, CV upload, and storage | Complete Login UI, integrate Cognito Hosted UI, build drag-and-drop CV upload, create `upload_cv` Lambda, store files in S3, save CV metadata in DynamoDB, and configure callback/logout URLs. |
| Week 9 |  CV analysis and dashboard | Build Dashboard data views, create `analyze_cv` Lambda, read CV files from S3, analyze CV content with Bedrock/Nova Lite, store extracted skills/projects/experience, and protect APIs with Cognito JWT authorizer. |
| Week 10 |  AI interview and answer scoring | Build the AI Interview page, create interview sessions, generate questions from CV and role, save answers, score responses, return feedback and suggested answers, and calculate the final interview score. |
| Week 11 |  Voice, history, profile, settings, and admin | Add History, Profile, and Settings pages, implement `history_api` and `profile_api`, integrate Polly and Transcribe for voice, build Admin Console, export CSV data, and prepare feedback email workflow. |
| Week 12 |  Testing, deployment, documentation, and demo | Polish UI, test responsive layout, verify API Gateway/Lambda/DynamoDB/IAM/CORS, improve AI prompts and scoring, prepare deployment guide, capture screenshots, finalize worklog, and complete the demo checklist. |

### 8. Budget Estimation

For a student workshop and low-traffic demo, the system is designed to stay lightweight. Most services can remain low cost when the number of users, uploaded files, and AI calls are controlled.

| Cost Area | Notes |
| --- | --- |
| Lambda and API Gateway | Charged by request count and execution time; expected to be low for demo traffic. |
| S3 | Charged by storage size and requests; CV and audio files should be cleaned up after testing. |
| DynamoDB | On-demand usage is suitable for small demo workloads. |
| Bedrock | Main variable cost; depends on number of CV analyses, generated questions, and answer evaluations. |
| Polly and Transcribe | Depends on amount of generated audio and uploaded answer recordings. |
| Amplify Hosting | Depends on build minutes, storage, and bandwidth. |

Cost control actions:

- Set an AWS Budget alert before deployment.
- Use a single AWS Region.
- Limit test users and uploaded file sizes.
- Delete test CVs, audio files, and unused resources after the workshop.
- Stop using Bedrock/Transcribe tests once the demo is complete.

### 9. Risk Assessment

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Incorrect Cognito callback/logout URL | Users cannot sign in or return to the frontend. | Verify local and Amplify URLs before testing. |
| API Gateway CORS or JWT misconfiguration | Frontend cannot call backend APIs. | Test each route with browser dev tools and CloudWatch logs. |
| Bedrock model access unavailable | AI analysis or scoring cannot run. | Enable model access early and keep fallback logic for demo mode. |
| Large CV/audio files increase cost or fail upload | Higher cost and unstable demo behavior. | Add file size limits and clean up S3 test data. |
| Voice permissions blocked by browser | Microphone flow may fail during demo. | Keep text-answer flow as a reliable backup. |

### 10. Expected Outcomes

After completion, Vertex-IntervAI should provide a working AI interview preparation workflow where users can sign in, upload CVs, receive AI analysis, practice interviews, answer by text or voice, view scores and feedback, and review history. The workshop also produces reusable documentation for deploying the same system on AWS Serverless infrastructure.

