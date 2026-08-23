![Framework](https://img.shields.io/badge/framework-Swarm-orange)
![Status](https://img.shields.io/badge/status-experimental%20%E2%86%92%20replaced-red)
![Language](https://img.shields.io/badge/language-Python%203.10%2B-blue)
![Successor](https://img.shields.io/badge/successor-OpenAI%20Agents%20SDK-green)

# 🐝 Swarm — OpenAI's Lightweight Multi-Agent Framework

> A small, simple, educational framework for coordinating multiple AI agents. Swarm taught the ideas — the **OpenAI Agents SDK** turned them into a production-ready tool.

```mermaid
%%{init: {'theme':'base', 'themeVariables': {'primaryColor':'#fff7ed','primaryBorderColor':'#ea580c','lineColor':'#ea580c','fontSize':'15px'}}}%%
flowchart LR
    A(("🐝 Swarm<br/>Experimental")) -->|"evolved into"| B(("🚀 OpenAI Agents SDK<br/>Production-ready"))
    style A fill:#fed7aa,color:#7c2d12,stroke:#ea580c,stroke-width:2px
    style B fill:#ea580c,color:#fff,stroke:#9a3412,stroke-width:3px
```

---

## 📚 Table of Contents

1. [🐝 What Is Swarm?](#-what-is-swarm)
2. [🎯 Why Swarm Was Built](#-why-swarm-was-built)
3. [🧩 Core Ideas: Agents & Handoffs](#-core-ideas-agents--handoffs)
4. [🔄 How Swarm Runs a Conversation](#-how-swarm-runs-a-conversation)
5. [💻 Quick Example](#-quick-example)
6. [📜 From Swarm to the OpenAI Agents SDK](#-from-swarm-to-the-openai-agents-sdk)
7. [🏗️ Anthropic's Agent Patterns Inside the SDK](#️-anthropics-agent-patterns-inside-the-sdk)
8. [⚖️ Swarm vs OpenAI Agents SDK](#️-swarm-vs-openai-agents-sdk)
9. [📖 Resources](#-resources)

---

## 🐝 What Is Swarm?

Swarm is an **experimental, educational** framework from OpenAI for coordinating several AI agents at once. It's small on purpose — built to be lightweight, easy to test, and simple to understand, not to be a full production system.

📌 Swarm runs almost entirely on the client side and holds no memory between calls — just like the Chat Completions API it's built on.

---

## 🎯 Why Swarm Was Built

One agent with one giant prompt gets messy fast when it needs to handle many different jobs. Swarm exists to split that work across smaller, focused agents that can pass a conversation to each other.

```mermaid
%%{init: {'theme':'base', 'themeVariables': {'primaryColor':'#fefce8','primaryBorderColor':'#ca8a04'}}}%%
flowchart LR
    P["😵 One giant agent<br/>trying to do everything"] -->|"❓ hard to manage,<br/>hard to test"| S["🐝 Swarm<br/>small, focused agents<br/>that hand off work"]
    style S fill:#ca8a04,color:#fff,stroke:#854d0e,stroke-width:2px
```

---

## 🧩 Core Ideas: Agents & Handoffs

Swarm is built on just **two ideas** — that's the whole point.

| Concept | What It Means |
|---|---|
| 🤖 **Agent** | A focused unit with its own instructions and its own set of tools/functions. |
| 🔁 **Handoff** | A way for one agent to pass the conversation to another agent that's better suited for it. |

```mermaid
%%{init: {'theme':'base', 'themeVariables': {'primaryColor':'#eff6ff','primaryBorderColor':'#2563eb'}}}%%
flowchart LR
    U[🧑 User] --> A1["🤖 Agent A<br/>General Support"]
    A1 -->|"🔁 handoff:<br/>billing question detected"| A2["💳 Agent B<br/>Billing Specialist"]
    A2 --> R[✅ Resolved Answer]
    style A2 fill:#2563eb,color:#fff,stroke:#1e3a8a,stroke-width:2px
```

**Example:** A general support agent notices a billing question and hands the conversation to a billing agent — the user gets an answer from the right specialist, without starting over.

---

## 🔄 How Swarm Runs a Conversation

Every call to `client.run()` follows the same loop:

```mermaid
%%{init: {'theme':'base', 'themeVariables': {'primaryColor':'#f0fdf4','primaryBorderColor':'#16a34a'}}}%%
flowchart TD
    S1[1️⃣ Get a response from the current Agent] --> S2[2️⃣ Run any tool/function calls]
    S2 --> S3[3️⃣ Switch Agent if a handoff happened]
    S3 --> S4[4️⃣ Update context variables]
    S4 --> S5{🔁 New function calls?}
    S5 -- Yes --> S1
    S5 -- No --> S6[✅ Return final response]
    style S6 fill:#16a34a,color:#fff,stroke:#166534,stroke-width:2px
```

---

## 💻 Quick Example

```python
from swarm import Swarm, Agent

client = Swarm()

def transfer_to_agent_b():
    return agent_b

agent_a = Agent(
    name="Agent A",
    instructions="You are a helpful agent.",
    functions=[transfer_to_agent_b],
)

agent_b = Agent(
    name="Agent B",
    instructions="Only speak in Haikus.",
)

response = client.run(
    agent=agent_a,
    messages=[{"role": "user", "content": "I want to talk to agent B."}],
)

print(response.messages[-1]["content"])
```

**Install:**
```bash
pip install git+https://github.com/openai/swarm.git
```
📌 Requires Python 3.10+.

---

## 📜 From Swarm to the OpenAI Agents SDK

Swarm was always labeled **experimental** — a way for developers to learn multi-agent orchestration, not something to run in production. OpenAI later released the **Agents SDK**, built directly on Swarm's two core ideas (Agents and handoffs), but made **production-ready**: better tooling, active maintenance, and stronger support for real-world workloads.

```mermaid
%%{init: {'theme':'base'}}%%
timeline
    title 🕰️ Swarm's Short History
    Early Release : Swarm launches as an experimental, educational framework
    Community Use : Developers use Swarm to learn multi-agent patterns
    Evolution : OpenAI releases the Agents SDK, built on Swarm's core ideas
    Today : Swarm is retired for production use; Agents SDK is the recommended path
```

⚠️ OpenAI's own guidance: migrate to the Agents SDK for anything beyond learning and prototyping.

---

## 🏗️ Anthropic's Agent Patterns Inside the SDK

The Agents SDK maps closely onto the agent design patterns Anthropic described in [*Building Effective Agents*](https://www.anthropic.com/engineering/building-effective-agents):

| Pattern | What It Does | How the SDK Supports It |
|---|---|---|
| 🔗 **Prompt Chaining** | Breaks a task into ordered steps | Agents run in a defined sequence |
| 🚦 **Routing** | Sends a task to the right specialist | The handoff mechanism |
| ⚡ **Parallelization** | Runs subtasks at the same time | Agents can operate concurrently |
| 🧭 **Orchestrator-Workers** | One agent delegates to several others | An orchestrator agent assigns work to worker agents |
| 📊 **Evaluator-Optimizer** | Improves output through feedback loops | Guardrails that check and refine agent behavior |

---

## ⚖️ Swarm vs OpenAI Agents SDK

| | 🐝 Swarm | 🚀 Agents SDK |
|---|---|---|
| Status | Experimental, educational | Production-ready |
| Maintenance | Not actively maintained | Actively maintained by OpenAI |
| Memory between calls | None (stateless) | Improved state handling |
| Best for | Learning multi-agent concepts | Real applications |
| Core ideas | Agents + Handoffs | Same ideas, expanded and hardened |

---

## 📖 Resources

- [Swarm on GitHub](https://github.com/openai/swarm)
- [Anthropic — Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents)

<p align="center"><strong>🐝 Swarm taught the pattern. 🚀 The Agents SDK made it production-ready.</strong></p>


