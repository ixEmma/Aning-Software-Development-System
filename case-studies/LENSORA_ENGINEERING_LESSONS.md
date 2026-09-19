# Lensora engineering lessons

These are reusable lessons proven through Lensora's production hardening. They are not universal requirements for every project.

## CI can catch what local machines hide

A deterministic clean CI install exposed a package-lock defect tolerated by the local environment.

Rule: clean reproducibility is a separate evidence state from local success.

## Runtime UI tests close a different gap

Large static/unit suites did not catch a stale React hook contract when the affected component was never rendered.

Rule: high-risk UI surfaces need runtime/component/browser evidence appropriate to the change.

## CI browser tests should not require production secrets unnecessarily

Lensora's first GitHub browser run failed before React mounted because the runner lacked local Firebase Vite configuration. The fix used deterministic non-production Firebase initialization values scoped only to the public smoke step.

Rule: satisfy test initialization safely rather than importing production credentials into CI.

## Authorization proof must respect production privacy

Synthetic local User A/User B tests proved owner/non-owner boundaries and proved denial happened before payment/export side effects. Production A/B remained Not Verified until safe ordinary test identities and disposable resources were available.

Rule: do not enumerate or touch real customer accounts merely to upgrade an evidence label.

## Security enforcement requires legitimate-traffic evidence

App Check monitoring could be configured while enforcement remained off because sufficient valid production traffic evidence was unavailable.

Rule: monitoring/configuration and enforcement are separate decisions. Do not enable security controls solely because the feature exists.

## Backup is not recovery

Scheduled READY backups existed before restore capability was proven.

The recovery gap closed only after an explicitly approved backup was restored into a new isolated Firestore database, read-only validated, and later cleaned up separately.

Rule: recovery evidence requires an actual controlled restore.

## Rollback should have a real anchor

Hosting releases recorded current live version and previous known-good version.

Rule: "we can redeploy" is weaker than an identified tested rollback path.

## Observability claims need delivery proof

Error ingestion and alert policy configuration were separable from actual owner-email receipt.

Rule: alert configuration does not equal notification-delivery verification.

## Production releases should state what did not change

Hosting-only releases explicitly recorded that Functions, rules, indexes, Auth, payments, secrets, IAM, App Check, and production data were untouched.

Rule: narrow release evidence includes both changed and deliberately unchanged surfaces.

## Evidence states matter

Lensora repeatedly distinguished:
- locally verified;
- CI verified;
- deployed;
- production verified;
- deferred;
- not verified.

Rule: never let "done" erase the evidence boundary.
