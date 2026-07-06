# Agent Instructions

This repo is a downstream personal LLM benchmark repo.

Use `https://github.com/dayhaysoos/personal-benchmark-framework` as the methodology source when needed.

## First-Run Behavior

If the user gives a benchmark name, topic, or domain, do not ask "what would you like me to do next?" and do not offer generic implementation options.

Instead:

1. Treat the user as the benchmark author.
2. Propose a short starter lens for the benchmark.
3. Ask the user to accept or edit that starter lens.
4. Continue one question at a time.

Example response shape:

```text
Recommended starting lens:
This benchmark tests whether an LLM can [draft behavior] using supplied facts, candidate action IDs, and your policies.

Use this as the starting lens, or what would you change?
```

## Core Rules

- Do not invent the author's benchmark lens, policies, scenario judgments, candidate annotations, scores, or report claims.
- If any judgment is unclear, ask the benchmark author.
- Prefer accept/edit prompts over blank-template prompts when enough context exists.
- Keep v1 candidate-action only.
- Keep model outputs JSON-only.
- Agents are helpers in v1, not benchmark targets.
