# Review Scenario Playbook

Use this playbook before adding a scenario to a reportable scenario set.

## Checklist

- The file name follows `0001-short-slug.md`.
- The scenario ID is repo-local and domain-prefixed.
- Prompt-facing data and author annotations are separated.
- The scenario binds one policy.
- The selected policy is defined in `policies.md`.
- Candidate actions have stable IDs and labels.
- The model is required to choose candidate IDs only.
- The scenario is independent and self-contained by default.
- Traps are plausible, not gotchas.
- Invalid actions and weak policy-fit judgments have notes.
- Critical avoid expectations are marked.
- `not_testing` keeps claims narrow.
- Relevant glossary terms are listed.

## Ask The Author

If any annotation is unclear, ask:

> What should a reader understand about why this candidate is valid, invalid, strong, weak, or a trap?

Do not infer the answer from the agent's own domain knowledge.
