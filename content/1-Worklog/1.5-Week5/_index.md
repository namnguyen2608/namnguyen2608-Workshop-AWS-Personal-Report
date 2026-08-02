---
title: "Worklog Week 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Research **Amazon Bedrock AgentCore Runtime** environment and program Coordinator Agent for AI task orchestration.
* Study **Cedar** authorization language and build security policies within the **AgentCore Policy Engine**.
* Configure **Bedrock Gateway** and safety **Guardrails** to control operational risks and prevent Prompt Injection attacks.

### Tasks Completed This Week:

| Day | Task Description | Start Date | Completion Date | Reference Resource |
| --- | --- | --- | --- | --- |
| Mon | - Study **Amazon Bedrock AgentCore Runtime** architecture — an execution environment managing AI Agent lifecycles <br> - **Hands-on:** Program **Coordinator Agent** handling user queries, intent analysis, and automated tool selection | 07/20/2026 | 07/20/2026 | [AWS AI/ML Services](https://cloudjourney.awsstudygroup.com/vi/7-aimlservice/) |
| Tue | - Research decoupling security boundaries completely from application code within AgentCore <br> - Learn **Cedar** authorization language syntax and structure (distinguishing `permit` allow vs `forbid` deny rules) | 07/21/2026 | 07/21/2026 | [IAM Policies & Governance](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |
| Wed | - Author Cedar security policy files inside **Policy Engine** controlling Agent tool invocation rights <br> - Practice policy evaluation in log-only mode (`log-only`) to assess behavior before enforcing active blocking | 07/22/2026 | 07/22/2026 | [IAM Permission Boundaries](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |
| Thu | - Configure **Bedrock Gateway** as a central interceptor monitoring all incoming Agent traffic <br> - Integrate **Guardrails** safety layers filtering toxic phrasing, blocking Prompt Injection attacks, and protecting sensitive data | 07/23/2026 | 07/23/2026 | [App Protection with AWS WAF](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |
| Fri | - **Integrated Practice:** Conduct security integration testing across AgentCore Runtime -> Policy Engine -> Bedrock Gateway <br> - Simulate unauthorized query attempts and confirm accurate active blocking per defined Cedar policies | 07/24/2026 | 07/24/2026 | [AWS Security Hub & Security](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |

### Week 5 Outcomes & Achievements:

* Gained deep understanding of Amazon Bedrock AgentCore Runtime and successfully programmed Coordinator Agent for intelligent task orchestration.
* Mastered Cedar policy authoring in Policy Engine, completely decoupling security governance from application logic.
* Successfully established Bedrock Gateway and Guardrails, guaranteeing enterprise-grade security for AI Agent operations.
