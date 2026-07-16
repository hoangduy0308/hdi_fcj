---
title: "Event 2"
date: 2026-06-06
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

## Summary Report: "Technical Meetup - June 6, 2026"

### Event Information

- **Date:** June 6, 2026
- **Role:** Attendee
- **Format:** Technical knowledge-sharing meetup

### Purpose of Attending

I attended the meetup to learn how engineers apply cloud services and software practices to real problems. The six sessions covered infrastructure, security, real-time applications, AI-based retrieval, teamwork, and career development, so the event also provided a useful view of how these areas connect.

### Speakers and Sessions

- **Bảo Huỳnh** - *Docker: A Containerization Technology*
- **Lê Hoàng Gia Đại** - *Combining AWS WAF with Machine Learning for Cyber Attack Detection on AWS*
- **Nguyễn Quốc Bảo** - *Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets*
- **Trương Huy Phước** - *The Art of Effective Teamwork*
- **Việt Phát** - *GraphRAG: Build GraphRAG Applications Using Amazon Bedrock and Amazon Neptune*
- **Trần Trung Vinh** - *From IT Helpdesk to Senior Sysadmin*

### Session Notes

#### Docker: A Containerization Technology

Bảo Huỳnh compared virtual machines with containers and explained how containers share the host operating system instead of running a complete guest operating system. The session covered Docker images, containers, Dockerfiles, and image layers, with examples from CI/CD, microservices, testing, cloud-native applications, and legacy modernization. The practical value of Docker is the ability to build an application once and run it consistently in different environments.

#### Combining AWS WAF with Machine Learning for Cyber Attack Detection

Lê Hoàng Gia Đại presented AWS WAF as the first layer for filtering attacks such as SQL injection, cross-site scripting, bot traffic, and brute-force attempts. Rule-based protection is effective for known patterns but has limitations when traffic contains zero-day, hybrid, or unusual behavior.

The proposed Network Intrusion Detection System adds behavioral detection instead of replacing AWS WAF. The presentation covered the CSE-CIC-IDS2018 dataset, data cleaning and class balancing, a LightGBM model, and an AWS architecture that collects and processes security data through services including Amazon S3, Kinesis Data Firehose, AWS Lambda, and Amazon CloudWatch.

#### Multiplayer in the Cloud with Godot and AWS WebSockets

Nguyễn Quốc Bảo demonstrated a turn-based Rock-Paper-Scissors game built with Godot clients, Amazon API Gateway WebSocket APIs, AWS Lambda, and Amazon DynamoDB. The `$connect`, `$disconnect`, and application routes handled connections, matchmaking, player choices, and results.

The session also discussed the limits of this serverless design. Stale connections, table scans, and stateless Lambda functions need careful handling, while games with frequent real-time updates may require a service such as AWS GameLift.

#### The Art of Effective Teamwork

Trương Huy Phước focused on the basics that teams often overlook: agreeing on a shared goal, assigning suitable roles, communicating openly, listening, and taking responsibility for assigned work. Tools such as Trello, ClickUp, Google Workspace, Slack, and Discord can support collaboration, but they do not replace clear responsibilities and regular communication.

#### GraphRAG with Amazon Bedrock and Amazon Neptune

Việt Phát explained why traditional Retrieval-Augmented Generation can struggle with questions that require following relationships across several entities or documents. GraphRAG represents those relationships as nodes and edges, allowing the retrieval process to follow more than semantic similarity.

Two implementation paths were introduced. The managed path uses Amazon Bedrock Knowledge Bases and Amazon Neptune Analytics for data processing and graph construction. The custom path uses LlamaIndex to build the knowledge graph and Cypher queries with Amazon Neptune for storage and multi-step traversal.

#### From IT Helpdesk to Senior Sysadmin

Trần Trung Vinh shared a career path from IT Helpdesk to System Administrator and then toward Cloud and DevOps. Troubleshooting, communication, Linux, networking, and hands-on labs form the foundation. The later stages require automation, runbooks, monitoring, Infrastructure as Code, CI/CD, version control, and safe testing practices. The session also stressed that practical projects and a clear portfolio are important evidence of capability.

### Main Lessons

- Containers solve environment consistency problems, but they do not remove the need to understand the underlying infrastructure.
- AWS WAF and machine-learning-based detection serve different purposes and work better as complementary security layers.
- API Gateway WebSocket APIs, Lambda, and DynamoDB fit lightweight or turn-based real-time features, not every multiplayer workload.
- GraphRAG is worth considering when questions depend on explicit relationships and multi-step reasoning.
- Technical skills alone are not enough; documentation, communication, accountability, and safe operational habits affect the reliability of a system.

### Applying the Knowledge

- Use Docker to create repeatable development and testing environments for small project components.
- Combine preventive controls with logging, monitoring, and behavioral detection when designing security solutions.
- Test a small WebSocket feature with API Gateway, Lambda, and DynamoDB before considering a larger real-time architecture.
- Evaluate GraphRAG only when the data and questions genuinely require relationship-based retrieval.
- Define a shared goal, clear responsibilities, and one task-tracking process before starting team implementation.

### Reflection

The meetup showed that selecting a technology is only one part of engineering. A solution also needs suitable security controls, operating practices, and teamwork. The topics I plan to study further are Docker, WebSocket APIs, monitoring, Infrastructure as Code, and the conditions under which GraphRAG provides a real advantage over traditional RAG.
