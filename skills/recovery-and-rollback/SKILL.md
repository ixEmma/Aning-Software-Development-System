---
name: recovery-and-rollback
description: Use when designing, verifying, or documenting backups, restore drills, RPO/RTO, deployment rollback, or disaster recovery.
---

# Recovery and rollback

Derived from Emmanuel's production-readiness standard and the Lensora Firestore recovery drill.

## Core rules

- Backup configuration is not restore proof.
- A READY backup artifact is not restore proof.
- Rollback documentation is not rollback proof.
- Recovery is verified only after a controlled recovery action and bounded validation.

## Recovery plan

For each critical dataset define:
- backup mechanism;
- frequency;
- location;
- retention;
- encryption/protection;
- RPO;
- RTO;
- restore procedure;
- verification;
- cleanup.

Do not invent RPO/RTO values. Derive them from product/business requirements.

## Safe restore drill

For a production backup, prefer an isolated destination.

Before execution require explicit approval that names:
- exact source backup/recovery point;
- exact destination;
- region/location;
- expected cost scope;
- verification plan;
- affected systems;
- cleanup/retention decision.

### Isolation rules

Where platform semantics allow:
- never restore over the production/default database during a drill;
- create a new isolated recovery target;
- keep it default-closed to client traffic;
- avoid IAM/rules/Hosting/Functions/Auth/payment/App Check changes unless the drill explicitly requires them;
- keep unrelated storage/auth systems out of scope unless they are part of the recovery objective.

## Validation

Use read-only checks to confirm representative:
- core entities;
- critical financial/business records where safe;
- relationships/counts;
- indexes;
- retention/TTL configuration;
- schema compatibility.

Record:
- operation ID;
- start/end time;
- recovery point age;
- validation completion;
- RPO comparison;
- technical recovery duration.

A database restore duration does not automatically prove the full-incident RTO.

## Cleanup

Deleting the isolated recovery target is a separate destructive action and should have separate approval when required.

After cleanup verify:
- production remained untouched;
- recovery target is gone;
- source backups remain intact.

## Deployment rollback

Before production release record:
- current live version;
- candidate version/commit;
- last known-good rollback anchor;
- rollback command/path;
- what rollback does and does not revert.

Prefer granular rollback when possible.

A successful release should record the new live version and retain the previous known-good anchor until confidence is sufficient.
