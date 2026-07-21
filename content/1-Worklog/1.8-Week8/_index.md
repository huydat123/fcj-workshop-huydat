---
title: "Week 8 Worklog"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives: Building the cv upload feature

* Build the upload_cv Lambda to receive base64 CV files and store them in S3.
* Validate PDF, DOC, and DOCX formats and save metadata to DynamoDB.
* Create the Upload CV API and test it with Postman/frontend.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - Built the upload_cv Lambda to process base64 files from the frontend. | 08/06/2026 | 08/06/2026 | AWS Lambda Documentation |
| 2 | - Added validation for PDF, DOC, DOCX formats and file size. | 09/06/2026 | 09/06/2026 | Project Validation Notes |
| 3 | - Stored CV files in S3 using cv/{userId}/{cvId}.{extension}. | 10/06/2026 | 10/06/2026 | Amazon S3 Documentation |
| 4 | - Saved CV metadata to the CVs DynamoDB table.<br>- Added uploaded/analyzed statuses for CV records. | 11/06/2026 | 12/06/2026 | DynamoDB Documentation |
| 5 | - Created the API Gateway route and tested CV upload with Postman. | 13/06/2026 | 13/06/2026 | Postman Collection |

### Week 8 Achievements:

* Completed the CV upload API from frontend to AWS.
* CV files were stored in the correct S3 structure and metadata was saved to DynamoDB.
* Found and fixed several upload data issues during testing.
