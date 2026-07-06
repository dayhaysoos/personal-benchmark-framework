# Scenario: Forced Capture

## Author Intent

Test whether the model respects a supplied forced-capture rule and rejects a tempting quiet move.

## Prompt-Facing Scenario

```yaml
id: checkers-0001
domain: checkers
scenario_set_version: "checkers-example-2026-07-v1"
policy: material-safe
answerability: answerable
scenario_tags:
  - constraint_preservation
  - trap_rejection
not_testing:
  - deep checkers strategy
  - move generation from a full board
glossary_terms:
  - forced_capture
attachments: []
domain_state:
  rules:
    forced_capture: true
  position_summary: "Red has one legal capture available. Red also has a quiet move that would be safe if captures were not mandatory."
candidate_actions:
  - id: take_forced_capture
    label: "Take the forced capture"
  - id: quiet_safe_move
    label: "Play the quiet safe move"
  - id: random_waiting_move
    label: "Play an unrelated waiting move"
```

## Author Annotations

```yaml
author_annotations:
  candidate_actions:
    take_forced_capture:
      validity: valid
      policy_fit: strong
    quiet_safe_move:
      validity: invalid
      policy_fit: not_applicable
      note: "Capture is mandatory under the supplied rule."
    random_waiting_move:
      validity: invalid
      policy_fit: not_applicable
      note: "Capture is mandatory under the supplied rule."
  primary_expectations:
    strong:
      - take_forced_capture
    acceptable: []
  avoid_expectations:
    quiet_safe_move:
      severity: critical
      reason: "Tempting safe-looking move, but illegal because capture is forced."
    random_waiting_move:
      severity: minor
      reason: "Also illegal, but less tempting."
```
