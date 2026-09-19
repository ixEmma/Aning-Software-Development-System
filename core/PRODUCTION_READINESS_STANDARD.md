# Production readiness standard

A working application is not automatically production-ready.

For serious applications, document **what we built, what the platform manages, what we configured, what we verified, what we measured, what we deferred, and what happens when something fails**.

Apply only the controls relevant to the target readiness level and product risk.

## Readiness levels

- **Level 0 - Prototype**: concept validation. No production-readiness claim.
- **Level 1 - Internal / Limited Beta**: core security and data integrity established for controlled use.
- **Level 2 - Production**: applicable production-readiness gates satisfied and verified.
- **Level 3 - Commercial SaaS**: Production plus mature observability, recovery, billing integrity, supportability, versioning, and capacity evidence.
- **Level 4 - High Criticality**: stricter reliability, security, redundancy, incident, recovery, and compliance controls based on risk.

Do not force a Level 4 checklist onto a prototype.

## Architecture and trust

Document:
- application purpose and users;
- frontend/backend/data/storage/auth/hosting;
- regions/domains;
- payments and critical providers;
- public, authenticated, admin, and trusted-server boundaries;
- authoritative source of truth for each critical flow.

For sensitive operations, client input must never automatically become trusted server state.

Document breaking-change and backward-compatibility consequences when clients/data contracts can outlive one deployment.

## Critical flows

Review separately where applicable:
- authentication;
- authorization and ownership;
- payments and entitlements;
- uploads/media;
- destructive actions;
- webhooks;
- background jobs;
- notifications;
- external APIs/model providers.

For each flow consider validation, timeout, retries, idempotency, duplicate delivery, error behavior, and source of truth.

## Reliability

Ask what happens when important dependencies fail.

Evaluate:
- compute;
- database;
- storage;
- auth;
- payments;
- DNS/CDN;
- external APIs/models;
- queues/background work.

Define SLIs/SLOs only where useful and based on product requirements or measured baselines. Do not invent numeric targets to make documentation look mature.

## Performance and capacity

Measure only what matters to the product.

Potential evidence:
- latency percentiles;
- throughput;
- concurrency;
- storage growth;
- database reads/writes;
- peak traffic;
- dependency degradation;
- cost.

A measured performance envelope is stronger than a theoretical scaling claim.

Keep distinct:
- quota: how much may be consumed/retained;
- validation: what is allowed;
- rate limit: how frequently;
- concurrency limit: how many at once.

## Data and storage

Document:
- data model and ownership;
- indexes/query patterns;
- transactions/consistency;
- retention/deletion;
- migrations;
- object-storage constraints;
- lifecycle/encryption;
- backward compatibility.

Do not trust stale cache for permissions, payment, or entitlement state.

## Security

Review:
- authentication;
- authorization;
- server-side enforcement;
- secrets;
- encryption;
- abuse controls;
- App Check/attestation/CAPTCHA where justified;
- WAF/rate limiting where justified;
- account recovery;
- threat model for high-impact systems.

Authentication and abuse prevention are separate concerns.

## Recovery

For critical datasets document:
- what is backed up;
- frequency;
- location;
- retention;
- encryption;
- restore procedure;
- restore evidence;
- RPO;
- RTO.

A configured backup is not a proven recovery capability. Restoration must be tested safely.

## Observability

A production system should eventually answer:

- **Logs** - what happened?
- **Metrics** - how often/how much?
- **Traces** - where did time/failure occur, when tracing is justified?
- **Alerts** - who is notified and under what threshold?

Logging is not alerting. Alert configuration is not alert-delivery verification.

Document threshold, severity, owner, notification destination, escalation, and autoclose/recovery behavior where applicable.

## Incident process

Use an appropriate severity model.

A useful default flow:

```text
Detect -> Assess -> Contain -> Recover -> Verify -> Communicate -> Postmortem
```

Do not make changes during an incident merely because something looks suspicious. Freeze unrelated work, establish the incident boundary, then act.

## CI/CD and rollback

Document:
- repository;
- CI provider;
- clean install;
- automated checks;
- build;
- environments;
- deployment provider;
- approvals;
- deployment verification;
- rollback.

Every production deployment path must answer:

**How do we return to the last known-good state?**

Prefer granular rollback when technically practical.

## Dependency and cost risk

For important providers record:
- purpose;
- failure impact;
- timeout/retry/fallback;
- provider limitations;
- exit/migration risk where significant;
- cost/capacity assumptions.

## Privacy and governance

Record:
- personal data collected;
- purpose;
- retention/deletion;
- third-party processing;
- user controls;
- known limitations;
- deferred technical debt;
- legal/geographic considerations where relevant.

## Six gates

### Gate A - Architecture
- system overview;
- critical flows;
- trust boundaries;
- platform vs application responsibilities;
- major ADRs.

### Gate B - Security
- auth/authz;
- validation;
- secrets;
- encryption;
- abuse controls;
- threat model where required.

### Gate C - Reliability
- failure modes;
- recovery;
- backup/restore;
- RPO/RTO where relevant;
- SLI/SLO decisions where useful.

### Gate D - Performance and scale
- measured latency/throughput where relevant;
- quotas/rate/concurrency;
- scaling/caching/CDN decisions;
- cost implications.

### Gate E - Operations
- logs/metrics/alerts;
- incident process;
- CI/CD;
- environments;
- rollback;
- dependency failure handling.

### Gate F - Product and governance
- privacy/retention;
- pricing/entitlement truth where relevant;
- versioning/backward compatibility;
- cost/capacity;
- known limitations/deferred work.

No gate passes on assumption alone.

## Sale-readiness boundary

Technical production readiness can improve due-diligence quality and transferability. It does not prove product-market fit, revenue quality, customer retention, IP ownership, or commercial value.
