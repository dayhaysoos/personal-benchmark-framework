# Create Scenario Playbook

Use this playbook to create one scenario in a downstream benchmark repo.

## Interview

Ask one question at a time.

1. What behavior should this scenario test?
2. What exact situation should the model reason about?
3. Which policy applies?
4. Is the scenario answerable or intentionally underspecified?
5. What candidate actions should the model choose from?
6. Which candidates are valid, invalid, or depend on missing information?
7. Which valid candidates fit the policy strongly, acceptably, or weakly?
8. Which traps are critical to catch?
9. What should the scenario explicitly not test?
10. What glossary terms are relevant to the prompt?

## Scenario Requirements

- Markdown file named `0001-short-slug.md`.
- Prompt-facing data in a YAML block.
- Author annotations in a separate YAML block.
- One policy per test case.
- Candidate actions use stable IDs and human labels.
- Model-facing prompt must include selected policy definition and only relevant glossary terms.

## Anti-Patterns

Avoid scenarios that:

- ask for general advice instead of a constrained decision
- rely on hidden facts not supplied to the model
- have only one obviously correct option
- use cheap wording gotchas
- test model memory while claiming to test reasoning
- use undefined policies
- mark an option bad without a reason when the call is non-obvious
