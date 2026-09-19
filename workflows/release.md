# Release workflow

Use for production-bound, high-risk, or product-truth-changing work.

References:
- `../core/DELIVERY_STATUS.md`
- `../core/EVIDENCE_MATURITY.md`
- `../core/PRODUCTION_READINESS_STANDARD.md`
- `../skills/ci-cd-release-gates/SKILL.md`
- `../skills/trusted-boundary-verification/SKILL.md`
- `../skills/recovery-and-rollback/SKILL.md`

For Firebase releases also use `../skills/firebase-release/SKILL.md`.

## Pre-release

1. Confirm approved scope and target readiness level.
2. Confirm branch, committed SHA, worktree safety, and intended deployment target.
3. Run relevant local tests, runtime checks, and production build.
4. Require the clean CI/reproducibility gate when the project has CI.
5. Review security, authorization/ownership, trusted boundaries, and destructive behavior.
6. Review recovery/rollback evidence appropriate to the release risk.
7. Run product/pricing synchronization if pricing, limits, entitlements, names, or availability changed.
8. Run functional UI/runtime QA.
9. Perform visual refinement only if the product is functionally sound.
10. Record known limitations, Deferred items, and Not Verified controls.

Use:

```text
Verified Locally
-> Committed
-> CI Verified
-> eligible for deployment review
```

Do not skip from local success to production claims.

## Deployment approval

Deployment is a separate owner-approved action.

Before approval record:
- exact target project/environment;
- exact committed revision;
- affected resources;
- dependency order;
- rollback anchor/path;
- possible production-data or provider side effects;
- smoke-test plan.

## Deployment

Prefer:
- dependency-aware order;
- the narrowest supported deployment;
- stop on failed prerequisites;
- no secret printing;
- explicit recording of both changed and intentionally unchanged production surfaces.

If a deployment tool can delete or replace live resources, compare intended configuration with current production inventory before writing.

## Production verification

After deployment:
- record deployed revision/version;
- verify the production domain/resource is serving the expected release;
- exercise the smallest safe set of critical flows;
- use synthetic/disposable identities/data for active proof where possible;
- check logs/errors/monitoring when relevant;
- verify alert delivery separately from alert configuration when that is part of the release;
- retain the last known-good rollback anchor until confidence is sufficient.

Report exact states:

```text
Deployed: yes/no
Production Verified: yes/no/partial
Not Verified: [...]
Deferred: [...]
```

Do not use customer data when synthetic/disposable data can prove the path.

A successful deploy command means **Deployed**, not automatically **Production Verified**.
