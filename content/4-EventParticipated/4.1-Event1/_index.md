---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

## Summary Report: "AWS Vietnam Community Day 2026 (FCAJ Community Day)"

### Event Information

- **Date:** May 23, 2026
- **Time:** 08:30 - 12:00
- **Location:** 26th Floor, Bitexco Financial Tower, 02 Hai Trieu Street, Saigon Ward, Ho Chi Minh City
- **Role:** Attendee
- **Focus:** Generative AI, AWS services, cloud architecture, and software engineering practices

### Purpose of Attending

I attended the event to learn how community speakers use AI and AWS services in practical projects. The agenda combined AI usage, cloud delivery, security, product development, and multi-agent architecture, which helped me compare technical approaches from several perspectives.

### Speakers and Sessions

- **Trương Anh Tịnh** - *Context Is Everything: Making AI Actually Work for You*
- **Phạm Ngô Hải Anh** - *Friendly AI Assistant with Amazon Quick*
- **Nguyễn Tuấn Thịnh** - *From Edge to Origin: CloudFront as Your Foundation*
- **Team VIB** - *36 hrs with LotusHacks: Building UTMorpho from Idea to Reality*
- **Đào Đức** - *Non-Determinism of "Deterministic" LLM Settings*
- **Lâm Cát Vy** - *Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring*

### Session Notes

#### Context Is Everything: Making AI Actually Work for You

The session focused on the quality of context provided to an AI model. Common problems included supplying too much unrelated material, repeating information the model already has, and writing requests without clear constraints. The "Second AI Brain" workflow, Store -> Retrieve -> Generate -> Learn, offered a simple way to organize information before using it with AI tools.

#### Friendly AI Assistant with Amazon Quick

This presentation introduced Amazon Quick as a tool for finding information and automating routine office tasks. The examples included preparing meeting notes, drafting follow-up emails, and organizing work from data stored in different sources. The main lesson was to begin with a small repetitive task and verify the output before expanding the automation.

#### From Edge to Origin: CloudFront as Your Foundation

The CloudFront session covered caching, compression, HTTP/3, origin failover, and edge processing with CloudFront Functions or Lambda@Edge. It also explained how CloudFront can work with AWS WAF and AWS Shield as part of a layered security design. Origin protection depends on the origin type: Origin Access Control is used for Amazon S3, while VPC origins can keep supported load balancers or EC2-based origins away from direct public access.

#### 36 hrs with LotusHacks: Building UTMorpho from Idea to Reality

Team VIB shared the process of building UTMorpho during a 36-hour LotusHacks event. The team had to select an idea, work within API limits, filter unusable AI-generated output, and prepare the product for the final presentation. Their experience showed that frequent team synchronization and a clear problem statement are more useful than adding unrelated features under time pressure.

#### Non-Determinism of "Deterministic" LLM Settings

The presentation explained why setting temperature to zero does not always produce identical output across repeated requests. Floating-point calculations on parallel hardware and request batching can introduce small differences during inference. Suggested controls included structured output, repeated evaluation, and tests that validate required behavior instead of expecting an exact sentence every time.

#### Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring

The final session used startup credit scoring as a case study for a multi-agent system. Specialized agents were assigned to financial, market, team, risk, and compliance analysis, with a manager agent coordinating the result. The proposed deployment path included CrewAI, Amazon Bedrock AgentCore, Docker, Amazon ECR, and API Gateway. The session also emphasized that security, data governance, operations, human review, and compliance must be considered when evaluating this architecture.

### Main Lessons

- Good context requires relevant information, clear constraints, and an expected output format.
- AI automation should start with a limited task whose results can be reviewed.
- CloudFront improves delivery performance, while security still depends on correctly combining it with other AWS services and origin controls.
- Systems that use LLMs should validate behavior and structure rather than assume identical text output.
- A multi-agent design is useful only when separate responsibilities and coordination provide a clear advantage over a simpler solution.

### Applying the Knowledge

- Define the goal, context, constraints, and success criteria before using an AI assistant.
- Use structured output when an application needs to process an LLM response programmatically.
- Review CloudFront caching and origin-access settings separately instead of treating the CDN as a complete security solution.
- Start AI or automation experiments with a small use case and add complexity only after the result can be measured.

### Reflection

The event helped me connect AI application development with cloud delivery and operational concerns. The two topics I want to explore further are context design for AI-assisted work and testing strategies for systems whose model output can vary between runs.
