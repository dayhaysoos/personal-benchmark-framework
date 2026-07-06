# Run Benchmark Playbook

Use this playbook when running a downstream personal benchmark.

## Before Running

1. Confirm scenario set version.
2. Confirm models.
3. Confirm runner.
4. Confirm run profile.
5. Confirm fallbacks are disabled for reportable direct API or OpenRouter runs.

## Default Profile

```yaml
temperature: 0
top_p: 1
seed: if_supported
stream: false
web_access: false
fallbacks: false
```

## During Run

For each model and scenario:

1. Render prompt-facing data with selected policy definition and relevant glossary terms.
2. Request JSON output.
3. Preserve full sanitized request/response envelope.
4. Mark malformed JSON as a format failure.
5. Do not repair malformed JSON for scoring.

## After Run

1. Draft scores as `agent_drafted`.
2. Ask the benchmark author to confirm or correct scores.
3. Change review status to `human_confirmed` only after author approval.
4. Generate a draft or final HTML report depending on review status.
