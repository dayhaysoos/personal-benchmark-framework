# Rubric

V1 scoring uses `pass | partial | fail`.

## Default Scenario Pass Condition

A scenario passes when:

- format is valid
- answerability is correct
- primary action is valid and at least acceptable
- all critical avoid expectations are handled
- no blocking unsupported claim is present

## Score Fields

- `format`
- `answerability`
- `primary_action`
- `avoid_reasons`
- `policy_fit`
- `uncertainty`
- `unsupported_claims`

## Failure Modes

- `format_failure`
- `answerability_error`
- `invalid_action`
- `missed_critical_trap`
- `policy_mismatch`
- `uncertainty_error`
- `unsupported_claim`

## Failure Severity

- `blocking`
- `minor`

## Review Status

- `agent_drafted`: agent prepared the score; not reportable as final.
- `human_confirmed`: benchmark author confirmed the score; reportable.
