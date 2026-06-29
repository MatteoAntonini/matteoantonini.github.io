---
title: "LLM vs Agent vs Multi-Agent [0]"
date: 2026-06-29
excerpt: The AI vocabulary that dominated 2025 — and why the distinction between LLM, Agent, and Multi-Agent actually matters if you're building with any of them.
image: /images/0.jpg
tags: [multi-agent, LLM, agentic-ai, fundamentals]
---

In 2025, one term started appearing everywhere: **Agentic AI**. You'll find it in startup pitch decks, in Gartner reports (which named it the top tech trend of the year), in job postings, and in conversations across the industry. But even among AI practitioners, the distinction between *LLM*, *Agent*, and *Multi-Agent* generates confusion more often than not. This post is the starting point: a reasoned glossary, not a list of definitions.

---

## Starting point: what is an LLM?

LLM stands for *Large Language Model*. But what does that actually mean in practice?

An LLM is, at its core, a **neural network** — a mathematical system made of billions of parameters (called weights) trained on massive amounts of text. Neural networks aren't inherently about generating text: they can be used to forecast revenue, classify images, detect fraud. But one of their applications is generating text output from text input. That's exactly what an LLM does: take a prompt, produce a response.

GPT, Claude, Gemini, Llama — all LLMs. All remarkably capable at answering questions, summarizing documents, translating text. But with one fundamental constraint: **they're stateless**. Every conversation starts from scratch. They don't remember, don't act, don't take initiative. They receive an input and return an output. That's it.

---

## The agent: when AI stops answering and starts acting

An **AI agent** is structurally different from an LLM. It's not a bigger or smarter model — it's a **layer on top** of the LLM that turns it into something autonomous.

An agent is built from three components:

- **LLM** — the brain: it reasons, interprets requests, decides what to do
- **Tools** — the hands: external APIs, databases, search engines, MCP servers, business systems
- **Context (memory)** — short-term state: maintains what happened in the conversation and what actions have been taken

The key difference from a bare LLM: the agent **acts**, it doesn't just respond. It can open a ticket, query a database, send an email, search the web. It can do this autonomously, step by step, until it completes an objective.

### How many times does the LLM get called?

This is a technical nuance worth understanding. In an agent, the LLM is typically invoked multiple times in sequence:

1. **First call**: receives the user's request and decides which tool to use (or whether one is needed at all)
2. **After tool execution**: receives the tool's output and processes it to formulate a coherent response

The number of calls depends on task complexity. For a simple task two calls are enough; for more complex work, the agent can reason, act, observe the result, and repeat — a pattern known as *ReAct* (Reason + Act).

---

## Multi-Agent: divide and conquer

If a single agent is like a good specialist, a **multi-agent system** is a well-coordinated team.

The problem with single agents is well-known: they're effective on well-defined, bounded tasks, but struggle when the problem is too broad or requires different areas of expertise. The natural solution is to **decompose the complex task into subtasks** and assign each one to a dedicated agent.

This isn't just good engineering practice — it's a paradigm shift. Gartner recorded a 1,445% increase in inquiries about multi-agent systems between Q1 2024 and Q2 2025. The Agentic AI market, currently at $7.8 billion, is projected to exceed $52 billion by 2030.

### A concrete example: customer support

Imagine a customer support system for a telecom company. A single general-purpose agent would struggle to handle everything. A multi-agent system, instead, could be structured like this:

- **Orchestrator** — receives the user's request and routes it to the right agents
- **Claims agent** — handles ticket creation, escalations, refunds
- **Account agent** — retrieves user information, active contracts, history
- **Sales agent** — proposes new offers, activates promotions, manages upgrades

Each agent is specialized. Each does one thing well. The orchestrator coordinates the flow. The result is a system that's far more robust, scalable, and controllable than a single catch-all agent.

---

## The full picture in three rows

| | LLM | Agent | Multi-Agent |
|---|---|---|---|
| **What it does** | Generates text | Acts toward an objective | Coordinates teams of agents |
| **Memory** | None (stateless) | Session context | Shared across agents |
| **Autonomy** | Low | Medium | High |
| **Typical use case** | Q&A, summaries, translation | Automating a specific task | Complex multi-domain tasks |

---

## Conclusion

If you want to simplify: the LLM is the engine, the agent is the car, the multi-agent system is the fleet.

In the next posts I'll go deeper: how the neural networks behind LLMs actually work, how to design an agent from scratch, and which frameworks exist today for building multi-agent systems — LangGraph, Google ADK, and others. There will be concrete examples from real projects.

If you have questions or want to suggest a topic, reach out.
