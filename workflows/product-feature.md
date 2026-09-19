# Product feature workflow

Use for a feature with meaningful product behavior.

```text
Product decision
    ->
appropriate builder
    ->
Code Reviewer
    ->
Reality Checker
    ->
Emmanuel review
```

Use Product Manager before implementation only when the problem, evidence, scope, or acceptance criteria are genuinely unclear.

## Before build

Define:
- problem;
- affected user;
- evidence or reason;
- smallest useful solution;
- non-goals;
- acceptance criteria;
- data/auth/pricing impact;
- release impact.

## During build

- preserve existing architecture;
- keep scope bounded;
- avoid speculative abstractions;
- record major decisions only when they are actually major.

## Completion

A feature is not complete because code exists. It needs relevant verification and explicit reporting of anything unverified.
