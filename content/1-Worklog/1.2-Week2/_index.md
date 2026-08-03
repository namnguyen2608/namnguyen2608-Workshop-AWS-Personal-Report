---
title: "Worklog Week 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* In-depth study of serverless compute service **AWS Lambda**: Handler functions, Triggers, Execution Roles, Environment Variables.
* Research **Amazon API Gateway** (HTTP API & REST API) and Proxy Routing (`/{proxy+}`).
* Deploy an initial Serverless Backend integration combining API Gateway and AWS Lambda Function.

### Tasks Completed This Week:

| Day | Task Description | Start Date | Completion Date | Reference Resource |
| --- | --- | --- | --- | --- |
| Mon | - Deep dive into **AWS Lambda** architecture, Stateless Execution mechanics, Pay-as-you-go pricing model, Memory Allocation configuration (128MB to 10GB), and Ephemeral Storage (`/tmp`) <br> - **Hands-on:** Write a basic Python 3.12 Lambda Function via AWS Console, analyzing `event` and `context` object syntax in Handler functions | 06/29/2026 | 06/29/2026 | [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) |
| Tue | - Research Lambda access permissions management via **IAM Execution Roles** and configure `AWSLambdaBasicExecutionRole` policy <br> - Learn to configure **Environment Variables** to manage static application parameters without hardcoding in source code <br> - Write JSON event processing logic inside Handler functions and test with sample AWS Console Event payloads | 06/30/2026 | 06/30/2026 | [AWS Lambda Execution Role & IAM Policies](https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html) |
| Wed | - Study **Amazon API Gateway**, comparing feature sets and cost trade-offs between HTTP APIs and REST APIs <br> - Research **Proxy Integration (`/{proxy+}`)**: Enabling API Gateway to forward raw HTTP Requests (headers, query params, body) directly to AWS Lambda for execution | 07/01/2026 | 07/01/2026 | [Amazon API Gateway Developer Guide](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html) |
| Thu | - Provision an Amazon API Gateway (HTTP API) and configure it as a direct Trigger for the AWS Lambda Function <br> - Configure **CORS (Cross-Origin Resource Sharing)** rules on API Gateway to allow secure browser connections from Frontend clients | 07/02/2026 | 07/02/2026 | [Configuring CORS & Triggers on API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-cors.html) |
| Fri | - **Integrated Practice:** Send HTTP requests (GET, POST) via Postman to the API Gateway endpoint URL <br> - Verify request routing -> Lambda execution -> successful JSON response payload delivery while monitoring logs in Amazon CloudWatch Logs | 07/03/2026 | 07/03/2026 | [Amazon CloudWatch Logs Documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html) |

### Week 2 Outcomes & Achievements:

* Deeply understood AWS Lambda execution mechanisms and serverless resource management.
* Mastered Amazon API Gateway and Proxy Routing `/{proxy+}` to receive and forward client HTTP traffic.
* Successfully built an end-to-end Serverless API Backend (API Gateway -> AWS Lambda).
