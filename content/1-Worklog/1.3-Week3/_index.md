---
title: "Worklog Week 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Research container image registry service **Amazon ECR (Elastic Container Registry)**.
* Package FastAPI Backend application into an optimized Docker Container Image for AWS Lambda.
* Initialize AWS Lambda Function using Docker Container Image from ECR and link with API Gateway.

### Tasks Completed This Week:

| Day | Task Description | Start Date | Completion Date | Reference Resource |
| --- | --- | --- | --- | --- |
| Mon | - Overview of container registry service **Amazon ECR (Elastic Container Registry)** <br> - **Hands-on:** Provision a Private ECR Repository on AWS Console <br> - Learn Docker CLI authentication command with Amazon ECR via AWS CLI: `aws ecr get-login-password --region <region>| 07/06/2026 | 07/06/2026 | [Amazon ECR User Guide](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html) |
| Tue | - Design and author an optimized `Dockerfile` for FastAPI Backend application <br> - Utilize base image (`public.ecr.aws/lambda/python:3.12`), append dependencies into `requirements.txt`, and configure Lambda Handler entrypoint | 07/07/2026 | 07/07/2026 | [Deploying AWS Lambda with Container Images](https://docs.aws.amazon.com/lambda/latest/dg/images-create.html) |
| Wed | - Build Docker Image locally (`docker build -t smartdoc-backend .`) <br> - Tag image targeting ECR URI (`docker tag ...`) and push image to Private ECR Repository <br> - Manage Image Tags, audit layer sizes, and enable Vulnerability Scanning settings on ECR | 07/08/2026 | 07/08/2026 | [Amazon ECR Image Vulnerability Scanning](https://docs.aws.amazon.com/AmazonECR/latest/userguide/image-scanning.html) |
| Thu | - Provision a new Lambda Function specifying **Container Image** source from the pushed ECR Repository <br> - Configure Memory Allocation (1024MB), Execution Timeout (30 seconds), and attach appropriate IAM Execution Role for Lambda Container | 07/09/2026 | 07/09/2026 | [Configuring AWS Lambda Container Functions](https://docs.aws.amazon.com/lambda/latest/dg/configuration-images.html) |
| Fri | - **Integrated Practice:** Link API Gateway trigger to newly deployed Lambda Container Image <br> - Execute API endpoint testing from Postman, evaluate Cold Start latency, and measure overall Serverless Container performance | 07/10/2026 | 07/10/2026 | [API Gateway & Lambda Container Integration](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-develop-integrations-lambda.html) |

### Week 3 Outcomes & Achievements:

* Mastered Docker Container Image management with Amazon ECR (authentication, push, tag, vulnerability scanning).
* Successfully packaged FastAPI Backend into a lightweight Docker Image optimized for serverless environments.
* Successfully deployed AWS Lambda Function running from ECR Container Image, fully integrated with API Gateway.
