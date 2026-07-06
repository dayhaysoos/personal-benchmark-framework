# Benchmark Name

Short description of the personal benchmark.

## Read First

- [eval-card.md](eval-card.md): what this benchmark tests and does not test.
- [policies.md](policies.md): behavior policies used in scenarios.
- [rubric.md](rubric.md): scoring rules.
- [scenarios/](scenarios): scenario files.
- [reports/](reports): HTML reports.

## Reproduce A Run

1. Read the run manifest under `runs/<run-id>/manifest.yaml`.
2. Use the same scenario set version, model IDs, runner settings, and prompt template.
3. Preserve raw sanitized request/response envelopes under `runs/<run-id>/raw-outputs/`.
4. Record scores under `runs/<run-id>/scores.yaml`.
5. Publish an HTML report under `reports/`.

## Claim Boundary

This benchmark reflects the benchmark author's judgment standard. It should not be read as universal consensus unless the benchmark explicitly says otherwise.
