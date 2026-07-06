# Claims And Limitations

Reports should make claims that match the scenario set, run profile, and review status.

## Good Claims

- This model passed 18 of 24 scenarios in this personal benchmark.
- The most common failure mode was `missed_critical_trap`.
- Model A was more reliable than Model B at rejecting invalid candidate actions in this scenario set.
- This benchmark reflects the author's stated judgment standard.

## Bad Claims

- This model understands the whole domain.
- This model is objectively better at the domain.
- This benchmark proves universal expert consensus.
- These results generalize beyond the tested scenarios.

## Public Benchmarks

Fully public benchmarks are transparent, teachable, reproducible, and easy to fork. They are weaker as permanent leaderboards because future models may be trained on them.

That is acceptable for this framework. Reports should simply say the benchmark is public and avoid overclaiming.

## Maintenance

- Version scenario sets with simple date/version labels.
- Do not silently edit old scenarios after reports are published.
- If scenarios or policies change, create a new scenario-set version.
- Reports must state which scenario-set version they used.

Example:

```yaml
scenario_set_version: "2026-07-v1"
```
