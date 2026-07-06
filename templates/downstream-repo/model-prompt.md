# Model Prompt Template

Use this template when rendering a scenario for an LLM.

```text
You are answering a personal benchmark scenario. Return only valid JSON matching the required output shape.

Task:
Choose from the provided candidate action IDs only. Do not invent actions.

Policy:
{{policy_label}}

Policy definition:
{{policy_definition}}

Relevant glossary:
{{relevant_glossary_terms}}

Scenario:
{{scenario_data}}

Required JSON shape:
{
  "answerability": "answerable | underspecified",
  "missing_information": [],
  "primary_action": "candidate_id_or_null",
  "acceptable_alternatives": [],
  "avoid": {
    "candidate_id": "brief reason"
  },
  "reasoning": "brief rationale, not chain-of-thought",
  "risk_note": "brief risk note or empty string",
  "uncertainty": {
    "level": "low | medium | high",
    "notes": []
  }
}
```

If the scenario is underspecified, set `primary_action` to `null`, use empty arrays/objects for action fields, and list the missing information.
