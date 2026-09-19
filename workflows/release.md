# Release workflow

Use for production-bound, high-risk, or product-truth-changing work.

## Pre-release

1. Confirm approved scope.
2. Confirm branch/commit/CI state.
3. Run relevant tests and production build.
4. Review security, auth/data boundaries, and destructive behavior.
5. Run product/pricing synchronization if pricing, limits, entitlements, names, or availability changed.
6. Run functional UI/runtime QA.
7. Perform visual refinement only if the product is functionally sound.
8. Record known limitations and deferred work.

## Deployment

Deployment is a separate approval.

Prefer:
- dependency-aware order;
- scoped deployment;
- stop on failed gates;
- no secret printing;
- rollback path known before risky writes.

## Production verification

After deployment, verify the smallest safe set of critical flows and record:
- deployed revision;
- what was verified;
- what was not verified;
- observed production errors;
- rollback status if needed.

Do not use customer data when synthetic/disposable data can prove the path.
