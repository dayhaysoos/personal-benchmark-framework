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

## Stage Gates

Follow the stages in order. Do not skip ahead just because the next artifact is easy to draft.

### Stage 1: Benchmark Lens

Produce an accept/edit draft for:

- what the benchmark tests
- what it does not test
- the initial claim boundary

Do not move on until the author accepts or edits this lens.

### Stage 2: Domain Pack

Before authoring scenario files, draft and get acceptance on:

- `eval-card.md` benchmark lens and `not_testing`
- `policies.md` initial policies
- `glossary.md` initial terms
- `scenario_set_version`
- core and domain-specific scenario tags

Do not write scenario files in Stage 2 unless the author explicitly asks.

### Stage 3: Smoke Scenarios

Only after Stage 2 is accepted, create 3-5 smoke scenarios using the existing scenario template.

### Stage 4: Runs And Reports

Only after scenarios are accepted, run models, capture raw outputs, score results, and draft reports.

## Required Agent Behaviors

- Interview one question at a time.
- Provide a recommended answer when making design decisions.
- Prefer accept/edit prompts over blank-form prompts when enough context exists.
- Respect the stage gates; do not introduce undefined policy IDs, glossary terms, scenario tags, or scenario set versions inside scenarios.
- Keep scenarios candidate-action only for v1.
- Keep model output JSON-only.
- Separate prompt-facing scenario data from author annotations.
- Preserve raw outputs.
- Label draft reports visibly.
- Avoid broad claims.

## Stop Conditions

Stop and ask the author when:

- a policy is undefined
- a scenario depends on a policy, glossary term, tag, or scenario set version that has not been accepted
- a candidate action's validity is unclear
- a trap or weak option lacks a reason
- scoring requires subjective judgment
- the report claim sounds broader than the scenario set supports
