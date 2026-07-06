# Policies

```yaml
policies:
  - id: material-safe
    label: Material-safe
    type: general
    definition: Prefer legal moves that preserve material and avoid immediate tactical loss.
    prefer:
      - legal captures when capture is forced
      - moves that avoid immediate recapture
    avoid:
      - illegal non-captures when capture is available
      - greedy moves that lose material immediately

  - id: promotion-race
    label: Promotion-race
    type: general
    definition: Prefer moves that advance toward kinging when material risk is acceptable.
    prefer:
      - legal moves that improve promotion chances
      - calculated material concessions if promotion pressure improves
    avoid:
      - passive moves that abandon a clear promotion race
```
