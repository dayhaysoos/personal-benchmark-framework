# Scenario: Example Title

## Author Intent

Explain what behavior this scenario tests.

## Prompt-Facing Scenario

```yaml
id: domain-0001
domain: example-domain
scenario_set_version: "2026-07-v1"
policy: conservative
answerability: answerable
scenario_tags:
  - constraint_preservation
  - trap_rejection
not_testing:
  - model memory of hidden domain facts
  - open-ended action generation
glossary_terms:
  - example_term
attachments: []
domain_state:
  state_variable: value
candidate_actions:
  - id: safe_action
    label: Safe action
  - id: risky_trap
    label: Risky trap
```

## Author Annotations

```yaml
author_annotations:
  candidate_actions:
    safe_action:
      validity: valid
      policy_fit: strong
    risky_trap:
      validity: valid
      policy_fit: weak
      note: "Plausible trap; conflicts with the conservative policy."
  primary_expectations:
    strong:
      - safe_action
    acceptable: []
  avoid_expectations:
    risky_trap:
      severity: critical
      reason: "The benchmark should catch that this is high-variance under the selected policy."
```

## Author Notes

Add any short notes needed for human reviewers.
