---
title: "When to Choose LangChain Over Direct API Calls"
description: "The decision between abstraction and control isn't always obvious. Here's when LangChain actually helps."
date: 2024-01-20
draft: false
---

Most developers hit this question early: should I use LangChain or just call the OpenAI API directly? The answer isn't about which is "better" — it's about what problem you're actually solving.

If you're building a simple chatbot or a one-off script, LangChain adds complexity you don't need. But when you're orchestrating multiple LLM calls, managing context across conversations, or building something that needs to work with multiple providers, the abstraction starts paying off.

## So when does LangChain actually help?

LangChain shines when you're doing more than a single request-response cycle. If you're chaining prompts, managing memory, or switching between different models, the framework handles the plumbing that would otherwise clutter your code.

Consider a scenario where you need to summarize a document, then ask questions about that summary, then generate a follow-up action. With direct API calls, you're manually managing context, tracking conversation state, and handling errors at each step. LangChain's chains and memory components abstract this away.

The trade-off is control. When something breaks, you're debugging through layers of abstraction instead of seeing exactly what's being sent to the API.

## What's the real cost of choosing wrong?

Pick LangChain for a simple use case, and you'll spend time learning a framework for a problem that needs 20 lines of code. Pick direct API calls for a complex workflow, and you'll end up building your own mini-framework to handle what LangChain already solves.

The hidden cost is maintenance. A direct API call is easy to understand six months later. A LangChain chain with custom components requires context about the framework's patterns and abstractions.

## Is this about avoiding vendor lock-in?

Not really. LangChain doesn't eliminate lock-in — it just shifts it to the framework itself. You're still dependent on LangChain's abstractions, update cycles, and design decisions.

The real question is: do you need the flexibility to switch providers, or do you need the flexibility to change your approach? If you're committed to OpenAI's API, the direct approach gives you more control. If you might switch providers or need multi-provider support, LangChain's abstractions make that easier.

In practice, most teams overestimate how often they'll switch providers. The abstraction is useful, but it's not the primary reason to choose LangChain.

The decision comes down to complexity. Simple problems need simple solutions. Complex workflows benefit from frameworks that handle the orchestration. The mistake is assuming one approach fits all scenarios.

If this helped you think more clearly about the topic, consider following — I share more thoughts like this.

The real question isn't LangChain vs. direct calls — it's whether you're solving a problem that needs orchestration, or one that just needs an API request.

