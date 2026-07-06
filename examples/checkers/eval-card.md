# Eval Card: Toy Checkers Example

## Benchmark

- Name: Toy Checkers Example
- Scenario set version: `checkers-example-2026-07-v1`
- Benchmark author: framework example
- License: MIT

## Author Context

```yaml
author_context:
  relationship_to_domain: "Framework example author"
  perspective: "Simple rule-following and conservative move choice"
  limitations: "This is illustrative only and not a serious checkers benchmark"
```

## What This Tests

This example tests whether an LLM can choose from candidate checkers moves while respecting supplied rules and a simple policy.

## What This Does Not Test

- deep checkers strategy
- opening theory
- tournament-level play
- move generation from a full board
- model memory of checkers rules beyond supplied facts

## Scenario Coverage

- Scenario count: 2
- Policies: `material-safe`, `promotion-race`
- Core tags: `constraint_preservation`, `trap_rejection`, `policy_fit`

## Scoring Method

- Scoring values: `pass | partial | fail`
- Review requirement: reportable scores require `human_confirmed`
- Failure severity: `blocking | minor`

## Known Limitations

This example uses fabricated model outputs and exists only to show the framework's shape.
