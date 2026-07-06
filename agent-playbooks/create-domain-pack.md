# Create Domain Pack Playbook

Use this playbook to create the first domain files in a downstream personal benchmark repo.

## Interview

Ask these one at a time. When the author already gave enough context, draft a likely answer and ask for accept/edit instead of asking a blank question.

1. What behavior should the benchmark examine?
2. What domain or recurring task does this benchmark cover?
3. What does the benchmark intentionally not test?
4. What policies or behavior styles should the model follow?
5. What kinds of candidate actions will scenarios use?
6. What common mistakes should scenarios expose?
7. What claims should reports be allowed to make?

For the first question, prefer this shape:

> Recommended starting lens: this benchmark tests whether an LLM can [draft behavior] using supplied facts, candidate action IDs, and the author's policies, while rejecting invalid options, plausible traps, and unsupported assumptions. Use this, or what should change?

## Files To Create

- `README.md`
- `eval-card.md`
- `glossary.md`
- `policies.md`
- `rubric.md`
- `scenarios/`
- `runs/`
- `reports/`

## Quality Bar

Do not ask the author for credentials. Ask for their benchmark lens.

The benchmark is ready for smoke scenarios when:

- the benchmark behavior is clear
- at least one policy is defined
- candidate-action format is understood
- the author can explain at least one plausible trap
- the report claim boundary is clear
