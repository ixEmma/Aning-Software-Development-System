---
name: ci-cd-release-gates
description: Use when creating or auditing CI/CD, preparing a release, or deciding whether local work is reproducible and eligible for deployment review.
---

# CI/CD and release gates

Derived from Emmanuel's Aning Software Development System and proven Lensora CI workflow.

## Purpose

CI proves the repository can reproduce the claimed quality from a clean environment. It does not replace manual/runtime QA and it does not automatically authorize deployment.

## When to establish CI

Set up CI once a repository has a working scaffold and code worth protecting. Do not wait until launch.

## Baseline clean-environment gate

Use project-relevant checks such as:

1. deterministic clean dependency install, for example `npm ci`;
2. separate package installs for Functions/background jobs when applicable;
3. lint;
4. unit/domain/contract tests;
5. component/runtime tests when present;
6. backend/function tests;
7. database/security-rule emulator tests when present;
8. production build;
9. diff/whitespace integrity such as `git diff --check`;
10. real-browser smoke tests when high-value UI flows justify them.

Do not invent commands. Inspect the project first.

## Proven Lensora lessons

- Local package-manager state can hide lockfile defects. Clean CI caught an incomplete lockfile that local npm tolerated.
- Static/unit coverage can miss real React runtime failures. High-risk UI surfaces benefit from actual component/browser execution.
- CI browser tests should not require production secrets just to mount public UI. Where safe, use deterministic non-production initialization values scoped to the CI test step.
- Failure artifacts such as screenshots/traces can make browser-test failures diagnosable.
- A CI quality workflow should not quietly contain deployment credentials or production deploy commands unless the repository explicitly uses reviewed continuous deployment.

## Release eligibility

Use this rule:

```text
relevant local verification
+ clean CI green
+ clean/safe Git state
= eligible for deployment review
```

Eligible for review is not deployed.

## Branch protection

Where the repository/platform plan supports it, required status checks can enforce quality before merge.

If branch protection is unavailable, document that limitation and keep the manual gate. Do not claim enforcement that the platform does not provide.

## Preview and human review

For visible product changes, a safe release flow may include:

```text
branch implementation
-> CI verification
-> preview/runtime verification
-> human review
-> merge
-> separately approved production deployment
```

Use only the steps relevant to the project.

## CI safety

CI should not:
- make real payments;
- mutate customer production data;
- expose live secret values;
- deploy merely because tests passed unless that behavior is explicitly designed and approved;
- rely on a developer's local uncommitted files.

## Evidence

Record:
- workflow/run;
- commit SHA;
- checks executed;
- failures and corrections;
- artifacts where useful;
- whether the gate is informational or enforced.
