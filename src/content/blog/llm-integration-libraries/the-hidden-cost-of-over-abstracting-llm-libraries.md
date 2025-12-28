---
title: "The Hidden Cost of Over-Abstracting LLM Libraries"
description: "Abstraction layers promise simplicity, but they come with hidden costs that compound over time."
date: 2024-01-20
draft: false
---

Every abstraction layer promises to make your life easier. With LLM libraries, that promise often comes true in the short term. You write less code, things work faster, and you don't have to think about the underlying APIs.

But abstractions have a cost that shows up later: debugging becomes harder, performance issues are harder to diagnose, and you're locked into the framework's way of doing things. When you need to do something the framework doesn't support well, you're stuck.

This isn't about avoiding abstractions entirely. It's about understanding what you're trading away.

## What are you actually giving up?

The most obvious cost is visibility. When something goes wrong with a direct API call, you can see exactly what was sent and what was received. With an abstraction layer, you're debugging through multiple levels of code you didn't write.

Error messages become less helpful. Instead of "rate limit exceeded" from the API, you get "chain execution failed" from the framework. You spend time figuring out what the framework did before you can address the actual problem.

Performance becomes harder to optimize. The framework might be making multiple API calls you don't know about, caching in ways you didn't expect, or adding overhead that doesn't matter at small scale but becomes significant later.

## When does the cost compound?

The real problem shows up when you need to do something the framework doesn't handle well. Maybe you need fine-grained control over retries, or you want to implement a custom caching strategy, or you need to optimize costs in a way the framework doesn't support.

Now you're fighting the abstraction. You're working around the framework's design instead of solving your actual problem. The time you saved initially gets spent later, often with interest.

Team knowledge becomes a dependency. New developers need to learn the framework, not just the underlying APIs. When the framework changes or deprecates features, your entire team needs to adapt. With direct API calls, the API documentation is your only dependency.

## Is there a middle ground?

Yes: use abstractions for the common cases, but keep the escape hatch. If your framework allows direct API access when needed, you can use the abstraction for 80% of your code and drop down when necessary.

Another approach is to abstract at your application layer, not at the library level. Build your own thin wrapper around direct API calls. You get the benefits of abstraction without the framework lock-in.

The key is knowing when to use each approach. Simple, repetitive tasks benefit from abstraction. Complex, performance-critical, or unusual requirements often need direct control.

The hidden cost isn't the abstraction itself — it's using it when you need control, or avoiding it when you need simplicity. The right choice depends on what you're building and how it might change.

I write about similar ideas regularly. Follow if this kind of breakdown is useful to you.

Abstractions are tools, not solutions. Use them where they help, avoid them where they hinder.

