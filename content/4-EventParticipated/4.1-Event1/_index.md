---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Summary Report: "AWS Vietnam Community Day 2026 (FCAJ Community Day)"

### Event Objectives

- Bring the FCAJ community together and share practical insights about Generative AI and Cloud Computing tailored for First Cloud AI Journey members.
- Understand Context Engineering in depth to use AI tools effectively in daily studies and workflows.
- Update knowledge on newer AWS services, including the Amazon Quick Suite, and CloudFront's cost optimization and security capabilities.
- Analyze the root causes of non-determinism in LLMs and explore production-ready architectures for multi-agent systems.

### Speakers

- **Tinh Truong** - Platform Engineer, GoTyme Bank
- **Pham Ng Hai Anh** - AWS Community Builder, G-AsiaPacific Vietnam
- **Nguyen Tuan Thinh** - DevOps Engineer, First Cloud AI Journey
- **Team VIB** - Software Developers/Hackathon Winners
- **Duc Dao** - Solution Architect, Cloud Kinetics
- **Vy Lam** - Senior Business Systems Analyst, VPBank

### Key Highlights

#### Context Is Everything: Making AI Actually Work for You

- Explained that AI models are already powerful, and the biggest bottleneck is how users feed context to them.
- Highlighted three common mistakes: dumping raw data (which dilutes signals and wastes tokens), stating the obvious to the model, and writing vague prompts without constraints.
- Introduced the "Second AI Brain" framework: Store -> Retrieve -> Generate -> Learn.
- Provided guidance for program members to build small, practical AI tools like Study Assistants, PDF Chat Apps, or Code Reviewers.

#### Friendly AI Assistant with Amazon Quick

- Addressed office workflow struggles: spending excessive time gathering data from different sources and doing repetitive tasks.
- Introduced the Amazon Quick Suite for natural-language data analysis: Quick Chat (deep analysis), Quick Flows (no-code automation), Quick Spaces (shared team knowledge), and Quick Sight (voice-to-dashboard).
- Demoed automation of administrative tasks: generating Minutes of Meetings (MoM), emailing stakeholders, and scheduling follow-ups without writing code.

#### From Edge to Origin: CloudFront as Your Foundation

- Solved cost and security concerns for small websites/startups: preventing AWS bill spikes due to unexpected traffic or DDoS attacks.
- Discussed cost optimization strategies like free data transfer out from AWS origins to CloudFront, flat-price tiers, and the Security Savings Bundle.
- Explained built-in security features: AWS WAF, Route 53, Shield, Mutual TLS (mTLS), and origin cloaking (securing S3/ALB origins via VPC Origin and OAC).
- Covered performance and reliability improvements: multi-layer caching, HTTP/3 (QUIC/UDP), HTTP compression, automatic origin failover, and edge logic (CloudFront Functions, Lambda@Edge).

#### 36 hrs with LotusHacks – Building UTMorpho from Idea to Reality

- Shared a real-world story of surviving 36 hours of continuous coding at Vietnam's largest hackathon.
- Walked through the practical challenges of developing UTMorpho: starting with zero ideas at hour zero, filtering out AI-generated garbage output, hitting API token limits, and facing burnout near the pitch.
- Outlined key learnings: real frustration leads to the best ideas; team sync matters more than individual skill; and hackathons test endurance in the face of failure.

#### Non-Determinism of "Deterministic" LLM Settings

- Debunked the assumption that setting Temperature = 0 guarantees fully reproducible (deterministic) outputs.
- Explained technical root causes: non-associative floating-point arithmetic on parallel GPU kernels and inference batching by API providers.
- Proposed mitigation strategies: running prompts multiple times with majority voting, enforcing structured outputs (JSON mode/function calling), and using `temperature = 0.1` to avoid greedy-decoding loops.

#### Enterprise-Grade Multi-Agent System: The Case of Startup Credit Scoring

- Analyzed why traditional credit scoring systems reject startups (requiring 3+ years of financials and physical collateral).
- Proposed a Multi-Agent "Virtual Credit Committee" architecture: specialized agents (Financial, Market, Team, Risk, Compliance) collaborating under a Manager.
- Demonstrated business ROI: 95% faster processing (from weeks to 2-4 hours), 95% cost reduction per application, and doubled approval rates.
- Outlined the deployment pipeline on AWS: CrewAI -> Bedrock AgentCore -> Docker -> ECR -> API Gateway, emphasizing the need to design the six enterprise pillars (security, data, network, operations, human, compliance) from day one.

### Key Takeaways

#### Working with AI

- Context engineering is the most underrated GenAI skill. Feeding the model targeted, high-quality context is far more effective than trying to write a complex prompt.
- LLM outputs are always probabilistic, even at temperature = 0. Systems must be designed and tested to handle variance and output disagreements.

#### Technical Architecture

- CloudFront is not just a CDN to speed up assets; it acts as a cost-control, security, and origin isolation layer when configured properly.
- Multi-agent architectures with specialized agents and peer checks outperform single-agent systems on complex, high-stakes decisions.

#### Product Design & Career

- The best product ideas come from real-world frustration and difficulties, not from theoretical brainstorming sessions.
- Start small by building tools that solve your own problems (like PDF chat or learning assistants) before scaling to complex enterprise systems.

### Applying to Work

- Outline Goal, Context, Constraints, and Success Criteria before opening a chat with AI to minimize trial-and-error.
- Experiment with Amazon Quick Sight to automate work report generation from raw datasets using natural language.
- Review current project CloudFront distributions to activate auto-compression and enforce origin security using OAC.
- Stop writing test assertions that assume deterministic LLM outputs; integrate JSON schema validation and majority voting instead.

### Event Experience

Attending the AWS Vietnam Community Day 2026 (FCAJ Community Day) was an actually useful experience. It gave me a clear picture of putting AI applications into production and building secure, cost-effective cloud foundations. Here are the main highlights:

#### Learning from experienced speakers
- Listened to insightful analyses from seasoned professionals at GoTyme Bank, VPBank, and Cloud Kinetics. The speakers shared actual production challenges and system errors rather than just marketing products.
- Understood that moving a prototype from local development to production requires robust architectures and addressing much higher security risks.

#### Practical technical insights
- The sessions dived directly into concrete configurations, such as setting up mTLS, configuring VPC Origin to keep backend ALB/EC2 instances completely off the public internet, and resolving LLM non-determinism at the GPU hardware level.
- Gained a clear understanding of measuring resource utilization (e.g., reducing EC2 origin CPU loads from 5% to 1% by leveraging optimal caching).

#### Exploring modern tools
- Witnessed live demos of Amazon Quick Suite and Amazon Bedrock AgentCore. These tools indicate a clear shift in GenAI application development from standalone chatbots to agentic automation workflows.
- Explored ways to handle model variance, such as majority voting and structured output formats to mitigate GenAI's technical limitations.

#### Networking & discussions
- The event brought together about 400 attendees, mostly First Cloud AI Journey members and the AWS FCAJ community. The discussions were very open, ranging from asking seniors for career advice to detailed questions about RAG algorithms.
- Observed the energy of the young AWS community, where student developers and junior engineers actively share and search for practical solutions rather than commercial debates.

#### Lessons learned
- AI collaboration skills will soon define a developer's core capability. Developing a solid understanding of context engineering and AI risk mitigation is essential, especially for program members.
- Team sync and targeting real problems are far more valuable than stacking cool but disjointed features.

#### Some event photos
*Add your event photos here*

> Overall, the event gave me solid technical knowledge and reshaped my thinking about system architecture, helping me understand how to integrate AI securely, efficiently, and cost-effectively into real-world projects.
