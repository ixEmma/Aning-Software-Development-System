# Operating system

The system has two modes: a lightweight task loop for ordinary work and a deeper lifecycle for serious software or release work.

## Lightweight task loop

```text
Understand -> Scope -> Build -> Review -> Verify -> Emmanuel approval
```

Do not create ceremony that costs more than the risk it controls.

## Serious software lifecycle

1. Product validation and scope
2. Documentation foundation
3. Architecture and trust boundaries
4. UI/reference research when relevant
5. Repository and environment setup
6. Functional implementation in bounded phases
7. Testing at the correct layer
8. CI/reproducibility gate
9. Security and reliability hardening
10. Product/pricing/public-surface synchronization when relevant
11. Production-readiness gates
12. Controlled deployment
13. Production smoke QA
14. Observability and recovery
15. Functional UI QA
16. Visual refinement only after function is sound
17. Final regression and release closure
18. User acquisition, feedback, and iteration

## Production-readiness gates

For serious releases, review:

- **Architecture** - boundaries, critical flows, source of truth, major decisions.
- **Security** - auth, authorization, validation, secrets, abuse controls.
- **Reliability** - failure behavior, recovery, backups where relevant.
- **Performance** - real bottlenecks, quotas, concurrency, cost.
- **Operations** - CI, logs, alerts, deployment, rollback.
- **Product and governance** - pricing/entitlements, privacy, retention, known limitations.

A gate passes on evidence, not assumption.

## Product/pricing synchronization

Whenever a release changes pricing, plan limits, entitlements, feature names, or availability, compare implementation against backend enforcement, checkout/payment mapping, pricing and upgrade UI, plan labels, marketing pages, FAQ/help/docs, and tests.

## Visual refinement boundary

Functional QA comes before visual polish. Refinement may improve hierarchy, spacing, typography, responsiveness, accessibility, and coherence, but must not silently redesign product behavior.

## Post-release rule

Once core production gates pass, real user evidence should influence the next build queue more than speculative feature accumulation.
