# Release checklist

Adapt this to the project. Delete irrelevant items instead of pretending every project needs every gate.

## Scope and state

- [ ] Approved release scope is clear
- [ ] Branch/revision is known
- [ ] Unrelated work is excluded
- [ ] Known limitations/deferred items are recorded

## Automated verification

- [ ] Relevant tests pass
- [ ] Type/lint checks pass where applicable
- [ ] Production build succeeds
- [ ] CI is green when CI exists

## Product truth

- [ ] Pricing is correct
- [ ] Plan limits/entitlements are correct
- [ ] Checkout/payment mapping is correct
- [ ] Upgrade/paywall messaging is correct
- [ ] Public marketing/docs match actual behavior
- [ ] Feature names are synchronized

Mark this section not applicable when the release does not affect product truth.

## Security and data

- [ ] Auth/authorization paths are verified
- [ ] No secrets leaked
- [ ] Destructive/data-migration risk is understood
- [ ] Rollback/recovery is known

## Functional QA

- [ ] Critical flows work
- [ ] Loading/empty/error states are acceptable
- [ ] Responsive behavior is checked where UI changed
- [ ] Accessibility basics are preserved
- [ ] Tracking/conversions work where relevant

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

- [ ] Target environment confirmed
- [ ] Dependency order understood
- [ ] Scoped deployment planned
- [ ] Rollback path known

## Production smoke QA

After deployment:
- [ ] Exact deployed revision recorded
- [ ] Critical production routes/flows verified
- [ ] Production logs/errors checked where accessible
- [ ] Anything not tested is labeled UNVERIFIED

## Closure

- [ ] PASS / FAIL / UNVERIFIED recorded
- [ ] Docs reflect current truth
- [ ] Next follow-up is evidence-driven
