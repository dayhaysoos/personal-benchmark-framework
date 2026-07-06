# Policies

Policies define the behavior style the model should follow.

Each scenario references exactly one policy ID. The model prompt should inline the selected policy definition.

## Policy Template

```yaml
- id:
  label:
  type: general # general | author_style
  definition:
  prefer:
    - 
  avoid:
    - 
```

## Policies

```yaml
policies:
  - id: conservative
    label: Conservative
    type: general
    definition: Prefer low-risk options with high certainty.
    prefer:
      - valid options with fewer downside risks
      - robust choices over fragile reads
    avoid:
      - high-variance actions unless clearly justified
```
