---
title: "Blog 3"
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# AgentCore Harness: From an idea to a working AI agent with only two APIs

When building an AI agent, calling a language model is only one part of the challenge. Developers must also handle the agent loop, tool connections, memory, session state, identity, observability, and a secure execution environment.

**Amazon Bedrock AgentCore Harness** packages these components into a managed service, allowing developers to focus on business logic and agent capabilities instead of building the supporting infrastructure.

---

## 1. Two main APIs

An agent can be put into operation through two APIs:

* **CreateHarness:** Defines the model, system prompt, tools, skills, memory, and execution limits.
* **InvokeHarness:** Sends a request for the agent to analyze, select tools, execute actions, and return a result.

For example, an AWS Support Agent could read CloudWatch logs, search AWS documentation, analyze errors, recommend solutions, and create a support case when necessary.

---

## 2. What Harness manages

Each agent session can run in an isolated environment with its own filesystem and shell. Harness can also connect to **AgentCore Gateway**, **MCP servers**, **AgentCore Browser**, **Code Interpreter**, and **Inline Functions**.

The model is separated from the agent logic, so developers can configure a default model or select a different model for individual requests without redesigning the entire system.

---

## 3. Harness and Runtime

* **AgentCore Harness** is suitable for the common agent flow of receiving a request, reasoning, calling tools, and returning a result. It prioritizes development speed and simplicity.
* **AgentCore Runtime** is more suitable when a custom framework, specialized workflow, custom orchestration, or deeper execution control is required.

Harness does not make agent development completely code-free. Developers still need to design prompts, tools, data, IAM roles, access permissions, and action controls.

---

## Conclusion

With **CreateHarness** for defining an agent and **InvokeHarness** for running it, AgentCore Harness reduces much of the supporting structure normally required for an AI agent. This helps development teams focus on real use cases and move more quickly from an idea to production.

---

## References

Read the official AWS article:
[Amazon Bedrock AgentCore harness is now generally available: Go from idea to production-grade agent in minutes](https://aws.amazon.com/blogs/machine-learning/amazon-bedrock-agentcore-harness-is-now-generally-available-go-from-idea-to-production-grade-agent-in-minutes/)

#AWS #AmazonBedrock #AgentCore #AgenticAI #GenerativeAI
