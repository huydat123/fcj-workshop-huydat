---
title: "Week 7 Worklog"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives: Backend initialization and database design

* Start implementing the Backend and Database parts of the project.
* Analyze storage needs for CVs, user profiles, and interview sessions.
* Create an S3 bucket for CV storage and test Lambda connectivity.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - Initialized the backend structure with separate Lambda folders. | 01/06/2026 | 01/06/2026 | Project Repository |
| 2 | - Designed data for Users, CVs, Interviews, and Profiles. | 02/06/2026 | 02/06/2026 | DynamoDB Data Modeling |
| 3 | - Created DynamoDB tables using userId, cvId, and interviewId keys. | 03/06/2026 | 03/06/2026 | DynamoDB Documentation |
| 4 | - Created an S3 bucket to store CVs under cv/{userId}/{cvId}.<br>- Tested S3 access permissions from Lambda. | 04/06/2026 | 05/06/2026 | Amazon S3 Documentation |
| 5 | - Documented required environment variables and IAM permissions for the backend. | 06/06/2026 | 06/06/2026 | IAM Documentation |

### Week 7 Achievements:

* Completed the initial backend structure.
* Created a data model for CVs, user profiles, and interviews.
* Connected Lambda with S3 to prepare for the CV upload feature.
