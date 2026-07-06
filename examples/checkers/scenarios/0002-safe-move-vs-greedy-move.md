# Scenario: Safe Move vs Greedy Move

## Author Intent

Test whether the model can choose a material-safe move over a greedy move that allows immediate recapture.

## Prompt-Facing Scenario

```yaml
id: checkers-0002
domain: checkers
scenario_set_version: "checkers-example-2026-07-v1"
policy: material-safe
answerability: answerable
scenario_tags:
  - policy_fit
  - trap_rejection
not_testing:
  - deep checkers strategy
  - long tactical search
glossary_terms:
  - recapture
attachments: []
domain_state:
  position_summary: "Red may either make a safe developing move or take a loose piece. The loose-piece capture allows Black to immediately recapture and win back more material."
  immediate_recapture_available_after_greedy_capture: true
candidate_actions:
  - id: safe_developing_move
    label: "Safe developing move"
  - id: greedy_capture
    label: "Greedy capture"
  - id: passive_back_move
    label: "Passive backward move"
```

## Author Annotations

```yaml
author_annotations:
  candidate_actions:
    safe_developing_move:
      validity: valid
      policy_fit: strong
    greedy_capture:
      validity: valid
      policy_fit: weak
      note: "Wins material immediately but allows a worse immediate recapture."
    passive_back_move:
      validity: valid
      policy_fit: acceptable
      note: "Legal and safe, but less useful than developing."
  primary_expectations:
    strong:
      - safe_developing_move
    acceptable:
      - passive_back_move
  avoid_expectations:
    greedy_capture:
      severity: critical
      reason: "Plausible greedy trap that violates the material-safe policy."
```
