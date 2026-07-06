# Positioning

Personal Benchmark Framework helps people build repeatable LLM benchmarks from their own judgment standard.

## Core Idea

People often know what good model behavior looks like in areas they personally care about. That area may be a deep niche, a hobby, a work practice, a game, a style preference, or a recurring decision pattern.

This framework turns that judgment into benchmark artifacts:

- scenarios
- policies
- candidate actions
- author annotations
- model outputs
- human-confirmed scores
- HTML reports

## Personal, Not Universal

A personal benchmark does not need to prove universal consensus. It should disclose the author's lens clearly enough that readers can understand, reuse, fork, or disagree with it.

Benchmarks usually get stronger when the author knows the topic well and can explain their judgments clearly, but the framework is not expertise-gated.

## V1 Boundary

V1 benchmarks LLM responses to controlled prompts.

Agents are helpers in v1. They may interview the author, draft files, run model APIs, preserve raw outputs, and prepare reports. They are not the thing being benchmarked.

Agent-harness benchmarks are future work.

## Claims

Good claim:

> This report compares model behavior on 24 author-created scenarios involving supplied facts, candidate actions, and policy-specific decisions.

Bad claim:

> Model X understands the whole domain.

Good claim:

> Model A was more reliable than Model B at rejecting invalid candidate actions in this scenario set.

Bad claim:

> Model A is better at the domain.
