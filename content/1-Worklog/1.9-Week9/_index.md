---
title: "Week 9 Worklog"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives: Developing ai interview sessions and answer storage

* Build the AI interview session flow based on analyzed CV data.
* Create an API to receive answers, score them, and store results.
* Design interview history data for the History and Result pages.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 1 | - Built analyze_cv Lambda to read CV files from S3 and invoke Amazon Bedrock. | 15/06/2026 | 15/06/2026 | Amazon Bedrock Documentation |
| 2 | - Built create_interview Lambda to generate interview question sets. | 16/06/2026 | 16/06/2026 | Project Backend Notes |
| 3 | - Designed storage for questions, answers, attempts, and score in the Interviews table.<br>- Prepared data for the AI Interview screen. | 17/06/2026 | 18/06/2026 | DynamoDB Documentation |
| 4 | - Built submit_answer Lambda to score answers and save feedback. | 19/06/2026 | 19/06/2026 | AWS Lambda Documentation |
| 5 | - Tested the upload CV, analyze CV, create interview, and submit answer flow. | 20/06/2026 | 20/06/2026 | Postman Collection |

### Week 9 Achievements:

* Created AI interview sessions based on CV data.
* The answer scoring API saved answers, attempts, and scores.
* Completed the data foundation for History and Result pages.
