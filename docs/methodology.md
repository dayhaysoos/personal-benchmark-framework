# Methodology

## Benchmark Shape

Each benchmark is built from self-contained scenarios. A scenario presents:

- a domain situation
- one selected policy
- candidate actions
- required JSON output fields
- author annotations used for scoring

The model must choose from candidate action IDs only. V1 does not test open-ended action generation.

## Scenario Layers

1. Prompt-facing data: what the model sees.
2. Author annotations: what the author uses to score the response.
3. Scoring sheet: how a specific model output performed.
4. HTML report: how a run is shared.

## Default Reportable Run Profile

```yaml
temperature: 0
top_p: 1
seed: if_supported
stream: false
web_access: false
fallbacks: false
max_tokens: report_defined
```

Reports may use other profiles, but they must say so explicitly.

## Authoring Rules

- Use supplied facts to test reasoning, not model memory.
- Use candidate actions only in v1.
- Include plausible traps, not gotchas.
- Keep scenarios independent and self-contained by default.
- Use author annotations, not a single golden output.
- Require short notes for traps, invalid actions, weak policy-fit judgments, and other non-obvious calls.
- Avoid universal-truth language. Use "author judgment", "author annotations", "judgment standard", and "benchmark lens".

## Scoring Layers

V1 uses pass, partial, and fail. It does not use numeric scores.

Suggested layers:

- format
- answerability
- primary action
- avoid reasons
- policy fit
- uncertainty
- unsupported claims

A scenario passes when:

- format is valid
- answerability is correct
- primary action is valid and at least acceptable
- all critical avoid expectations are handled
- no blocking unsupported claim is present

## Failure Modes

Core failure modes:

- `format_failure`
- `answerability_error`
- `invalid_action`
- `missed_critical_trap`
- `policy_mismatch`
- `uncertainty_error`
- `unsupported_claim`

Failure severity:

- `blocking`
- `minor`

Domains may add prefixed failure modes, such as `tek:frame_misread` or `repair:safety_hazard`.

## Scenario Count Guidance

- 1-5 scenarios: smoke test / demonstration
- 6-20 scenarios: exploratory report
- 21-50 scenarios: small benchmark
- 50+ scenarios: stronger personal benchmark

This is guidance, not a hard rule.
