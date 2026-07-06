# Runner Guidance

V1 is runner-agnostic. The framework defines what metadata must be captured, not a specific runner implementation.

## Preferred Reportable Modes

### Direct Provider API

Best for reproducibility when you can call the model provider directly.

Record:

- provider
- model ID
- model version, if available
- request parameters
- raw request
- raw response
- usage metadata
- timestamp

### OpenRouter

Useful for low-friction multi-model runs.

Reportable OpenRouter runs must disable fallbacks. If fallbacks are used, the run is exploratory and should not be presented as a clean benchmark.

Record:

- requested model
- selected provider
- selected model
- fallback setting
- router metadata, when available
- request parameters
- raw request
- raw response
- usage metadata
- timestamp

## Non-Reportable By Default

### Manual UI Copy/Paste

Manual UI runs are allowed for exploration only. They usually lack stable parameters, full request envelopes, exact model identifiers, provider metadata, and hidden system prompt visibility.

### Agent Harnesses

Agent harnesses are out of scope as benchmark targets in v1.

Agents may help run the workflow, but if the model response is produced through an agent harness, the report must label the result as agent-harness behavior rather than direct LLM behavior.

## Model Runner vs Agent Operator

Use this distinction in run manifests:

```yaml
agent_operator: cursor
model_runner: openrouter
runner_type: direct_model_api
```

or:

```yaml
agent_operator: cursor
model_runner: cursor-agent
runner_type: agent_harness
reportable: false
```
