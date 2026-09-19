# Evidence maturity

Task verification and architecture-control maturity are related, but they are not the same thing.

## Control maturity states

Use these when evaluating production controls, infrastructure, security, reliability, recovery, or operational capabilities.

- **Detected** - evidence suggests the control or capability exists.
- **Configured** - evidence shows it was intentionally set up.
- **Verified** - a direct observation or controlled test proves the expected behavior.
- **Measured** - runtime or load evidence quantifies how it behaves over time or under defined conditions.
- **Not Verified** - stronger proof is absent.
- **Failed** - direct evidence shows the required behavior is not satisfied.

Never promote a control above the strongest state supported by traceable evidence.

Examples:

```text
backup schedule exists
= Configured

READY backup artifact exists
= Configured with stronger evidence

isolated restore completes and data is validated
= Verified

repeated restore drills with measured RPO/RTO
= Measured
```

Absence of stronger evidence is **Not Verified**, not automatically **Failed**.

## Architecture capability status

Use these when documenting whether a capability belongs to the application/platform:

- **Implemented** - explicitly built and verified by us.
- **Platform Managed** - provided by the platform and relevant behavior is understood.
- **Partially Implemented** - some controls exist but the full capability is incomplete.
- **Planned** - required but not implemented.
- **Not Required** - evaluated and intentionally excluded.
- **Not Verified** - implementation/configuration evidence is insufficient.

Do not label something Implemented merely because the platform probably provides it.

## Task result

Use the simpler task-level result vocabulary:

- **PASS**
- **FAIL**
- **UNVERIFIED**

A task may PASS while a broader production control remains only Configured or Not Verified.

Example:

```text
Task: add Firestore backup schedule
Result: PASS

Backup control maturity: Configured
Restore capability: Not Verified
```

## Evidence record

For important verification, record when practical:

- control/task;
- evidence source;
- supported maturity state;
- environment;
- revision/version;
- time collected;
- test parameters;
- evidence artifact/reference;
- cleanup status;
- human approval when active testing was required;
- freshness/expiry when relevant.

Evidence is allowed to expire. Reassess when the system, configuration, or environment changes.
