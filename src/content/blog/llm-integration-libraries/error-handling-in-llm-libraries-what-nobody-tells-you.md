---
title: "Error Handling in LLM Libraries: What Nobody Tells You"
description: "LLM APIs fail in ways that HTTP libraries don't handle well. Here's what you need to know."
date: 2024-01-20
draft: false
---

Error handling in LLM libraries looks straightforward. The API returns an error, the library throws an exception, you catch it and handle it. Standard HTTP error patterns.

But LLM APIs fail in ways that don't fit standard error handling patterns. Rate limits are soft, not hard. Timeouts are common and often recoverable. Partial failures happen mid-stream. Token limits are hit unexpectedly.

Most libraries handle the obvious errors but miss the edge cases that matter in production.

## What errors are actually recoverable?

Rate limits are the most common issue, and they're usually recoverable. The API tells you when you can retry, but most libraries don't implement exponential backoff or respect retry-after headers automatically.

You end up implementing your own retry logic, which means you're handling the same error in multiple places, using different strategies, and creating inconsistent behavior across your application.

Token limit errors are often recoverable too. If a request exceeds the context window, you can truncate the input, summarize it, or split it into multiple requests. But most libraries just throw an error and let you figure it out.

Timeout errors are ambiguous. Did the request actually fail, or is the API just slow? Some libraries retry timeouts automatically, others don't. Some distinguish between network timeouts and API timeouts, others don't.

## Why do libraries handle errors poorly?

Library authors focus on the happy path. They test with successful requests and obvious failures, but they don't test the gray areas: slow responses, partial failures, recoverable errors.

The abstraction also hides useful information. When an error occurs, you often need details about what was sent, what failed, and what you can do about it. But the library's error object might not expose that information.

Error types are inconsistent. Some libraries use custom exception types, others use standard HTTP exceptions. Some provide detailed error messages, others give generic failures. You can't write consistent error handling code.

## What should proper error handling include?

Retry logic with exponential backoff is essential. Rate limits, temporary failures, and network issues are common and usually recoverable. The library should handle these automatically with sensible defaults.

Error classification helps. Distinguish between recoverable errors (rate limits, timeouts) and non-recoverable errors (invalid API keys, malformed requests). This lets you handle each type appropriately.

Context preservation is crucial. When an error occurs, you need to know what request failed, what the response was (if any), and what you can do about it. The error object should include this information.

Partial failure handling matters for streaming and long-running requests. If a request fails partway through, you need to know what succeeded, what failed, and whether you can recover or need to start over.

## How do you work around library limitations?

The best approach is to wrap the library with your own error handling layer. Implement retry logic, error classification, and context preservation that the library doesn't provide.

Use circuit breakers for persistent failures. If an API is consistently failing, stop sending requests temporarily to avoid wasting resources and degrading user experience.

Implement fallback strategies. If the primary LLM provider fails, can you use a backup? If a specific model fails, can you use a different one? Plan for failure, not just success.

Log everything. When errors occur, log the full context: request details, response (if any), error type, and what you did about it. This information is invaluable for debugging and improving error handling.

The library provides the API interface. You provide the production reliability.

Error handling is where the difference between demo code and production code shows up. Plan for it from the start, not as an afterthought.

If this helped you think more clearly about the topic, consider following — I share more thoughts like this.

Good error handling anticipates failure modes. Most libraries don't. You need to fill that gap.

