# Delivery status vocabulary

Execution permission and delivery status are different dimensions.

Use `PLANNING ONLY / READY FOR GO / EXECUTED LIVE` to describe whether an action is permitted/executed in the current interaction.

Use the statuses below to describe how far a software change has actually progressed.

## Delivery statuses

- **Proposed** - design or decision exists, no implementation.
- **Implemented Locally** - code/config exists in the working environment.
- **Verified Locally** - relevant local tests/build/runtime checks passed.
- **Committed** - the verified work is recorded in Git history.
- **CI Verified** - a clean CI environment passed the required gate for the exact revision.
- **Deployed** - the target production resource changed successfully.
- **Production Verified** - live behavior/evidence confirmed against the deployed revision.
- **Deferred** - intentionally postponed.
- **Not Verified** - evidence is absent or insufficient.
- **Blocked** - a prerequisite, platform limitation, manual checkpoint, or decision prevents progress.

Never use **Complete** when the intended scope includes production verification that has not happened.

## Example

```text
Permission state: EXECUTED LIVE

Delivery status:
Implemented Locally -> Verified Locally -> Committed -> CI Verified

Deployment: Not performed
Production verification: Not Verified
```

## Why this matters

- local tests do not prove CI reproducibility;
- CI green does not prove deployment;
- deployment does not prove live user behavior;
- platform capability does not prove configuration;
- configuration does not prove control effectiveness.

Report the strongest state supported by evidence, no further.
