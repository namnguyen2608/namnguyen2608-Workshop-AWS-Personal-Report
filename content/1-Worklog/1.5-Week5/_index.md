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
| Mon | - Study **Amazon Bedrock AgentCore Runtime** architecture — an execution environment managing AI Agent lifecycles <br> - **Hands-on:** Program **Coordinator Agent** handling user queries, intent analysis, and automated tool selection | 07/20/2026 | 07/20/2026 | [Amazon Bedrock Agents Developer Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html) |
| Tue | - Research decoupling security boundaries completely from application code within AgentCore <br> - Learn **Cedar** authorization language syntax and structure (distinguishing `permit` allow vs `forbid` deny rules) | 07/21/2026 | 07/21/2026 | [Cedar Authorization Language Specification](https://www.cedarpolicy.com/en/docs) |
| Wed | - Author Cedar security policy files inside **Policy Engine** controlling Agent tool invocation rights <br> - Practice policy evaluation in log-only mode (`log-only`) to assess behavior before enforcing active blocking | 07/22/2026 | 07/22/2026 | [Cedar Security Policy Management Guide](https://docs.aws.amazon.com/verifiedpermissions/latest/userguide/policies.html) |
| Thu | - Configure **Bedrock Gateway** as a central interceptor monitoring all incoming Agent traffic <br> - Integrate **Guardrails** safety layers filtering toxic phrasing, blocking Prompt Injection attacks, and protecting sensitive data | 07/23/2026 | 07/23/2026 | [Configuring Amazon Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html) |
| Fri | - **Integrated Practice & Team Meeting (07/25/2026):** Security integration testing across AgentCore Runtime -> Policy Engine -> Bedrock Gateway. Simulate unauthorized queries and verify active Cedar policy enforcement. <br> - **Team Meeting:** Comprehensive system evaluation, full codebase review, and report error audit among team members. <br> - **Detailed Meeting Agenda:** <br>&emsp; + In-depth review of all compiled report sections (5.1.5, 5.4.1, 5.4.2, 5.4.3, 5.3.2). <br>&emsp; + Feedback on technical terminology, Markdown formatting, and image URL pathing. <br>&emsp; + Finalize rollout plan for technical testing and end-to-end system validation in Week 6 | 07/24/2026 | 07/25/2026 | [AWS Security Hub Documentation](https://docs.aws.amazon.com/securityhub/latest/userguide/what-is-securityhub.html) |

### Week 5 Outcomes & Achievements:

* Gained deep understanding of Amazon Bedrock AgentCore Runtime and successfully programmed Coordinator Agent for intelligent task orchestration.
* Mastered Cedar policy authoring in Policy Engine, completely decoupling security governance from application logic.
* Successfully established Bedrock Gateway and Guardrails, guaranteeing enterprise-grade security for AI Agent operations.
* Completed team meeting auditing all report sections (5.1.5, 5.4.1, 5.4.2, 5.4.3, 5.3.2), unifying Markdown formatting and Week 6 testing schedule.

