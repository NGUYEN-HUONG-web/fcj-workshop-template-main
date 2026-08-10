---
title: "Event 2"
date: 2026-08-08
weight: 2
chapter: false
pre: "<b> 4.2 </b>"
---

# “Agent Forge – Deepdive Day 2” Attendance Report

## 1. Event Information

| Item | Details |
|---|---|
| **Event name** | Agent Forge – Deepdive Day 2 |
| **Main topic** | Advanced Amazon Bedrock AgentCore |
| **Date** | August 8, 2026 |
| **Time** | 9:00 AM–12:00 PM |
| **Location** | Bitexco Financial Tower, 2 Hai Trieu Street, Ho Chi Minh City |
| **Organizer** | Huỳnh Hoàng Long |
| **Role** | Attendee |
| **Status** | Attended |
| **Format** | Technical presentations and hands-on activities |
| **Event page** | [View on Luma](https://luma.com/8qewnfuu) |

![Picture](/images/event2.png)
## 2. Event Overview

**Agent Forge – Deepdive Day 2** was the second session in a three-day Agent Forge workshop series.

While Day 1 introduced the foundations of AI agents and their initial setup, Day 2 focused on:

> **Personalization, Evaluation & Optimization**

The main topic was **Advanced Amazon Bedrock AgentCore**, including how to build memory, monitor agent behavior, evaluate quality, and optimize AI agents on AWS.

The event combined technical presentations, hands-on activities, and direct discussions with the instructor.

## 3. Reasons for Attending

The event was directly related to the **AI Learning Assistant Platform** project.

The platform allows users to:

- Upload learning materials.
- Process PDF, DOCX, and TXT files.
- Split documents into data chunks.
- Generate vector embeddings.
- Search for information in a Dataset.
- Ask questions based on uploaded documents.
- Generate quizzes and flashcards.
- Receive answers from AI models.

The project needs to manage data for individual users, retrieve the correct documents, and reduce unsupported answers.

Memory, Evaluations, and Observability can directly support these requirements.

## 4. Event Program

### 4.1 Advanced Amazon Bedrock AgentCore

The main presentation introduced:

- **Memory:** Stores information to personalize agent behavior.
- **Evaluations:** Measures the quality and effectiveness of an agent.
- **Observability:** Monitors how an agent processes requests.
- **Registry:** Manages agents and tools.
- **Harness:** Supports agent development and testing.
- **Tools:** Connects agents to external services.
- **Optimization:** Improves accuracy, performance, and cost efficiency.
- **Policy:** Controls access permissions and agent behavior.

### 4.2 Hands-on Session

The hands-on activities focused on:

1. Adding Memory to an AI agent.
2. Personalizing agent behavior for individual users.
3. Exploring Agent Observability.
4. Monitoring the execution process.
5. Using AgentCore Evaluations.
6. Exploring AgentCore Harness.
7. Understanding the role of Harness in agent development.

### 4.3 Schedule

| Time | Activity | Outcome |
|---|---|---|
| **8:30–9:00 AM** | Registration and preparation | AWS environment ready |
| **9:00–10:00 AM** | Advanced AgentCore presentation | Understanding of the main components |
| **10:00–11:00 AM** | Hands-on session | Practical experience with Memory and Evaluations |
| **11:00 AM–12:00 PM** | Discussion and networking | Technical questions answered |

## 5. Knowledge Gained

### 5.1 Memory

Memory allows an agent to retain relevant information from previous interactions.

For a learning platform, Memory could store:

- The user’s preferred language.
- Learning goals.
- Subjects currently being studied.
- Frequently used documents.
- Quiz results.
- Topics that require improvement.
- Preferred response style.
- Question history.

Memory should be isolated for each user and should not store sensitive information unless necessary.

### 5.2 Evaluations

Evaluations measure agent quality using specific criteria, including:

- Answer accuracy.
- Relevance.
- Faithfulness to the source documents.
- Citation accuracy.
- Retrieval quality.
- Response time.
- Tool-call success rate.
- Appropriate refusal when insufficient information is available.

Evaluations help the development team identify responses that do not meet quality requirements and determine appropriate improvements.

### 5.3 Observability

Observability provides visibility into the entire request-processing flow.

Important data to monitor includes:

- The user’s question.
- The selected model.
- The selected Dataset.
- Retrieved document chunks.
- The prompt sent to the model.
- Tools invoked by the agent.
- Token usage.
- Processing time.
- Errors and retry attempts.
- The final answer.

This information can help identify why an agent selected the wrong Dataset, retrieved insufficient data, or generated an answer that was not supported by the source documents.

### 5.4 Registry and Harness

Registry supports the management of agents, tools, and related system components.

It can be used to manage:

- Available agents.
- Available tools.
- Tool versions.
- Function descriptions.
- Input and output schemas.
- Operational status.
- Access permissions.

Harness supports structured agent development and testing.

It can help developers:

- Supply test data.
- Monitor each processing step.
- Compare actual and expected results.
- Reproduce errors.
- Test changes to prompts.
- Test changes to models.
- Automate test cases.

### 5.5 Tools and Policy

Tools allow an agent to perform tasks outside the language model.

Potential tools for the project include:

- Dataset search.
- Document summarization.
- Quiz generation.
- Flashcard generation.
- File retrieval from Amazon S3.
- AWS Lambda invocation.
- DynamoDB lookup.
- External API calls.
- User notifications.

Policy limits the permissions and actions available to agents and tools.

Each tool should receive only the minimum IAM permissions required for its responsibilities. Administrator permissions should not be used for routine tasks.

Policies should clearly define:

- Which tools an agent can invoke.
- Which documents a user can access.
- Which AWS resources a tool can access.
- Which actions require user confirmation.
- How unsafe requests are blocked.
- How agent actions are logged for auditing.

### 5.6 Optimization

Optimization focuses on improving agent performance in areas such as:

- Answer accuracy.
- Retrieval quality.
- Prompt structure.
- Tool selection.
- Context size.
- Response time.
- Token usage.
- Operating costs.
- Error handling.
- User experience.

## 6. Application to the Project

The knowledge gained from the event can be applied to the **AI Learning Assistant Platform** workflow:

```text
User question
→ Select a Knowledge Base
→ Search the Dataset
→ Retrieve document chunks
→ Build the prompt
→ Invoke the AI model
→ Evaluate the result
→ Return the answer
```

### Specific Applications

- Personalize the learning experience.
- Remember user goals.
- Track learning progress.
- Select the correct Dataset.
- Monitor retrieved content.
- Evaluate answer quality.
- Detect workflow errors.
- Reduce AI hallucinations.
- Optimize token usage and response time.
- Control access to documents.
- Monitor tool activity.
- Evaluate model performance.

### Role of AgentCore Components

- **Memory:** Remembers the user’s language, learning goals, subjects, and areas that require improvement.
- **Evaluations:** Measures answer accuracy, relevance, and faithfulness to source documents.
- **Observability:** Monitors Dataset IDs, retrieved chunks, prompts, token usage, response time, and errors.
- **Tools:** Supports document search, quiz generation, flashcard generation, AWS Lambda invocation, and data retrieval from AWS services.
- **Policy:** Ensures that agents and tools can access only the data and services required for their tasks.

## 7. Conclusion

Attending **Agent Forge – Deepdive Day 2** gave me a clearer understanding of how to build, operate, monitor, and evaluate an AI agent on AWS.

Through the sessions on **Memory, Evaluations, Observability, Registry, Harness, Tools, Optimization, and Policy**, I learned that agent quality depends on more than the underlying Large Language Model. A production-ready system also requires appropriate data, supporting tools, monitoring mechanisms, evaluation methods, and clearly defined security policies.

In particular:

- **Memory** enables agents to personalize experiences for individual users.
- **Evaluations** measure the accuracy and relevance of agent responses.
- **Observability** provides visibility into the entire processing flow, making errors easier to detect and resolve.

This knowledge can be applied directly to the **AI Learning Assistant Platform**, particularly to:

- Personalize learning experiences.
- Remember user goals and progress.
- Retrieve the correct documents from a Dataset.
- Evaluate answer accuracy.
- Verify that answers remain faithful to source documents.
- Monitor each stage of the workflow.
- Detect errors when invoking models or tools.
- Reduce AI hallucinations.
- Control access to data and AWS services.
- Optimize response time, token usage, and operating costs.

In addition to the technical content, the event provided opportunities to exchange ideas with the instructor and other participants interested in AI agents. These discussions gave me a more practical perspective on the challenges involved in deploying agents in real-world environments.

Overall, **Agent Forge – Deepdive Day 2** was a valuable and technically focused event that aligned well with the project’s development goals. The knowledge gained will provide a foundation for further research into Amazon Bedrock AgentCore, continued development of the **AI Learning Assistant Platform**, and the creation of safer and more reliable AI agent applications.