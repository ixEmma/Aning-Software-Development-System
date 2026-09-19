# Production readiness audit

Use for serious applications before a production-readiness claim, major commercial launch, or high-risk release.

Reference:
- `../core/PRODUCTION_READINESS_STANDARD.md`
- `../core/EVIDENCE_MATURITY.md`
- `../templates/PRODUCTION_READINESS_REVIEW.md`

## 1. Establish context

Record:
- application/revision;
- target readiness level;
- production or pre-production state;
- architecture;
- critical workflows;
- sensitive data/payments/multi-user/webhooks/background jobs;
- available environments.

The target level determines applicable controls.

## 2. Passive evidence first

Inspect without mutation:
- repository/config;
- CI;
- tests;
- deployment configuration;
- cloud/resource inventory where read-only access is safe;
- monitoring;
- backup records;
- documentation.

Do not promote self-reported or detected evidence to Verified.

## 3. Capability matrix

For each relevant control record:
- capability;
- architecture status;
- evidence maturity;
- implementation/provider;
- evidence reference;
- known gap;
- next verification action.

## 4. Evidence-gap plan

Before active tests, identify:
- current state;
- next possible state;
- missing proof;
- risk;
- recommended environment;
- exact approval needed.

## 5. Active verification

Only after explicit approval.

Prefer staging, emulators, synthetic identities/data, and isolated recovery targets.

Production active tests must be bounded and define halt/cleanup conditions.

## 6. Six gates

Review:
A. Architecture
B. Security
C. Reliability
D. Performance/Scale
E. Operations
F. Product/Governance

Do not pass a gate because the platform "probably handles it."

## 7. Findings order

Report:
1. release/launch blockers;
2. failed controls;
3. high-risk Not Verified controls;
4. evidence-confidence gaps;
5. recommended verification;
6. remediation;
7. verified/measured controls;
8. stale evidence.

## 8. Reassessment

Readiness is not permanent.

Reuse still-valid evidence, invalidate stale evidence, rerun changed controls, and record regression/improvement.
