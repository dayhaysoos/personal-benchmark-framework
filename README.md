# Personal Benchmark Framework

A framework for turning your own judgment standard into repeatable benchmarks of LLM behavior.

The project is for personal benchmarks: benchmark authors define the situations, policies, candidate actions, annotations, and claims that matter to them. Agents can help structure the work, but the author owns the judgment.

## Quick Start

Create a new benchmark repo from the starter:

```bash
gh repo create my-benchmark --template dayhaysoos/personal-benchmark-starter --public --clone
```

Then copy this prompt into your preferred agent from inside the new benchmark repo:

```text
Use this repository as a downstream personal LLM benchmark repo.

Use https://github.com/dayhaysoos/personal-benchmark-framework as the methodology source. Interview me one question at a time. I am the benchmark author. Do not invent my benchmark lens, policies, scenario judgments, candidate annotations, scores, or report claims.

Start by helping me define what model behavior this personal benchmark should examine, what it does not test, the first 1-3 policies, and the first 3-5 smoke scenarios.
```

The starter repo is here: [dayhaysoos/personal-benchmark-starter](https://github.com/dayhaysoos/personal-benchmark-starter).

## Framework-Only Start

Copy this prompt into your preferred agent:

```text
Use this repository as a framework for creating a personal LLM benchmark. Interview me one question at a time. Treat me as the benchmark author. Do not invent author judgments, candidate annotations, policy definitions, or scoring decisions. Help me create a downstream benchmark repo using the templates and playbooks here.
```

Then follow:

1. Read [docs/positioning.md](docs/positioning.md).
2. Use [agent-playbooks/bootstrap-agent.md](agent-playbooks/bootstrap-agent.md).
3. Create a downstream repo using [templates/downstream-repo/README.md](templates/downstream-repo/README.md), or use the starter repo above.
4. Start with 3-5 smoke scenarios before running a larger benchmark.

## What This Is

This framework helps you create personal benchmarks that test how LLMs behave under your stated judgment standard.

It is useful when you want to ask:

- Does this model preserve the constraints I care about?
- Does it choose from candidate actions in a way that matches my policy?
- Does it reject plausible traps?
- Does it admit uncertainty when the scenario is underspecified?
- Does it make unsupported claims?

## What This Is Not

This is not an official consensus benchmark format, a leaderboard system, or a claim that your personal benchmark is universal truth. It is a way to make your benchmark lens explicit, repeatable, and inspectable.

## V1 Scope

V1 benchmarks LLM responses only. Agents may help author scenarios, run APIs, organize outputs, draft scores, and fill reports, but agents are not benchmark targets in v1.

Default reportable runs use direct provider APIs or OpenRouter-style direct model APIs with fallbacks disabled. Manual UI copy/paste runs are exploration only.

## Core Artifacts

- [templates/downstream-repo/eval-card.md](templates/downstream-repo/eval-card.md): benchmark identity and limitations.
- [templates/downstream-repo/policies.md](templates/downstream-repo/policies.md): policies the model should follow.
- [templates/downstream-repo/scenarios/0001-example-scenario.md](templates/downstream-repo/scenarios/0001-example-scenario.md): Markdown scenario with prompt-facing data and author annotations.
- [templates/downstream-repo/rubric.md](templates/downstream-repo/rubric.md): scoring rules.
- [templates/downstream-repo/runs/example-run/manifest.yaml](templates/downstream-repo/runs/example-run/manifest.yaml): run metadata.
- [templates/downstream-repo/runs/example-run/scores.yaml](templates/downstream-repo/runs/example-run/scores.yaml): human-confirmed or draft scoring.
- [templates/downstream-repo/reports/example-report.html](templates/downstream-repo/reports/example-report.html): agent-filled static HTML report template.

## Example

The [examples/checkers](examples/checkers) folder contains a tiny illustrative checkers benchmark. Its outputs are fabricated and exist only to show the framework structure.

## License

This framework is MIT licensed. Downstream benchmark authors should choose their own license for their benchmark content.
