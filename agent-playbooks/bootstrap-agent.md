# Bootstrap Agent Playbook

Use this playbook when helping a benchmark author create or maintain a personal LLM benchmark.

## Prime Directive

The agent structures the author's judgment. The agent must not invent author judgments.

Ask the author whenever a candidate action, annotation, policy definition, score, or claim is unclear.

## Start Here

Ask one question at a time. Do not jump into scenario files until the benchmark frame is clear.

Keep first-run friction low. If the author already named a benchmark or domain, propose a short starter draft and ask them to accept or edit it. Do not make them fill a template-shaped sentence from scratch unless there is not enough information to draft one.

Recommended first question:

> I think this benchmark tests whether an LLM can [draft behavior] using supplied facts, candidate action IDs, and the author's policies, while rejecting invalid options, plausible traps, and unsupported assumptions. Should we use that as the starting lens, or what would you change?

If the author gave almost no domain context, ask:

> What model behavior do you want this personal benchmark to examine?

## Workflow

1. Clarify the benchmark lens.
2. Create or update `eval-card.md`.
3. Define policies in `policies.md`.
4. Define the default model prompt from `model-prompt.md`.
5. Create 3-5 smoke scenarios.
6. Run a small direct API or OpenRouter run with fallbacks disabled.
7. Preserve raw sanitized request/response envelopes.
8. Draft scores as `agent_drafted`.
9. Ask the author to confirm or correct scores.
10. Produce an HTML report only after review status is clear.

## Required Agent Behaviors

- Interview one question at a time.
- Provide a recommended answer when making design decisions.
- Prefer accept/edit prompts over blank-form prompts when enough context exists.
- Keep scenarios candidate-action only for v1.
- Keep model output JSON-only.
- Separate prompt-facing scenario data from author annotations.
- Preserve raw outputs.
- Label draft reports visibly.
- Avoid broad claims.

## Stop Conditions

Stop and ask the author when:

- a policy is undefined
- a candidate action's validity is unclear
- a trap or weak option lacks a reason
- scoring requires subjective judgment
- the report claim sounds broader than the scenario set supports
