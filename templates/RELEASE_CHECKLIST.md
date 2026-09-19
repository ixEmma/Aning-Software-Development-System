# Release checklist

Adapt this to the project. Delete irrelevant items instead of pretending every project needs every gate.

## Scope and state

- [ ] Approved release scope is clear
- [ ] Target readiness level is appropriate
- [ ] Exact branch/commit is known
- [ ] Unrelated work is excluded
- [ ] Known limitations/Deferred items are recorded
- [ ] Current delivery status is stated precisely

## Local and CI verification

- [ ] Relevant local tests pass
- [ ] Runtime/component/browser checks cover high-risk UI when applicable
- [ ] Type/lint checks pass where applicable
- [ ] Production build succeeds
- [ ] Clean deterministic dependency install is proven in CI where applicable
- [ ] CI is green for the exact revision
- [ ] CI does not depend on uncommitted local files
- [ ] Any CI limitation or unenforced branch gate is documented

## Product truth

- [ ] Pricing is correct
- [ ] Plan limits/entitlements are correct
- [ ] Checkout/payment mapping is correct
- [ ] Upgrade/paywall messaging is correct
- [ ] Public marketing/docs match actual behavior
- [ ] Feature names are synchronized

Mark this section not applicable when the release does not affect product truth.

## Security and trusted boundaries

- [ ] Authentication paths are verified
- [ ] Authorization/ownership is verified at the strongest safe environment
- [ ] Privileged side effects happen only after trusted checks
- [ ] No secrets leaked
- [ ] Destructive/data-migration risk is understood
- [ ] Production active tests use approved synthetic/disposable identities/resources where possible
- [ ] Any production authorization gap is labeled Not Verified rather than guessed

## Reliability and recovery

- [ ] Backup state is known where data is critical
- [ ] Restore evidence is distinguished from backup configuration
- [ ] RPO/RTO decisions exist where relevant
- [ ] Rollback anchor/path is known
- [ ] Recovery/rollback has been verified to the level required by release risk

## Functional QA

- [ ] Critical flows work
- [ ] Loading/empty/error states are acceptable
- [ ] Responsive behavior is checked where UI changed
- [ ] Accessibility basics are preserved
- [ ] Tracking/conversions work where relevant

## Observability and operations

- [ ] Relevant logs/metrics exist
- [ ] Alert policy/configuration state is known
- [ ] Notification delivery is separately Verified or Not Verified
- [ ] Incident owner/process is known for material releases

## Visual refinement

Only after functional QA:
- [ ] critique
- [ ] distill
- [ ] polish
- [ ] audit
- [ ] human aesthetic review

Mark not applicable when no visual surface changed.

## Deployment

Deployment requires explicit approval.

- [ ] Target project/environment confirmed
- [ ] Exact committed SHA confirmed
- [ ] Affected resources listed
- [ ] Dependency order understood
- [ ] Scoped deployment planned
- [ ] Live configuration/inventory drift checked where deletion/replacement risk exists
- [ ] Rollback anchor/path recorded
- [ ] Possible production-data/provider side effects understood

## Production smoke QA

After deployment:
- [ ] Deployed revision/version recorded
- [ ] Expected release is confirmed live
- [ ] Critical production routes/flows verified safely
- [ ] Production logs/errors checked where accessible
- [ ] Changed and intentionally unchanged resources are recorded
- [ ] Anything not tested is labeled Not Verified

## Closure

- [ ] Task result PASS / FAIL / UNVERIFIED recorded
- [ ] Delivery status recorded
- [ ] Control maturity updated where relevant
- [ ] Docs reflect current truth
- [ ] Next follow-up is evidence-driven
