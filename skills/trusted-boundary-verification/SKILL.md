---
name: trusted-boundary-verification
description: Use when verifying authorization, ownership, tenant isolation, privileged operations, webhooks, payment boundaries, or other controls where unsafe production testing could touch real users or side effects.
---

# Trusted-boundary verification

Derived from Emmanuel's production-readiness evidence workflow and Lensora authorization hardening.

## Principle

Start with the least-privileged evidence. Escalate only when stronger proof is useful, safe, and explicitly approved.

Do not convert repository evidence or AI reasoning into a production-verified claim.

## Evidence progression

A control may move through:

```text
Detected -> Configured -> Verified -> Measured
```

Local verification is not automatically production verification.

State the environment:

- verified locally;
- verified in emulator/test;
- verified in staging;
- production verified;
- not verified.

## Before active verification

For any active test, define:

- exact target;
- control being tested;
- identities/resources used;
- maximum requests/actions;
- whether data may be created;
- possible side effects;
- halt condition;
- rollback/cleanup;
- expected evidence.

Obtain explicit approval for production active tests.

## Authorization and ownership tests

Prefer:
- synthetic users;
- designated ordinary User A/User B accounts;
- disposable resources/events;
- test-only data.

Verify both allowed and denied paths.

For sensitive side effects, prove the authorization check occurs **before** payment, archive, delete, export, webhook, or other irreversible/provider action.

## Production safety

Do not:
- enumerate real production users merely to find a test subject;
- read another customer's private resource;
- create a real charge;
- trigger uncontrolled webhook/provider traffic;
- alter customer-owned data;
- attempt privilege escalation;
- enable a stronger security control before legitimate traffic has been observed and rollback is known.

If safe production identities/resources do not exist, report:

```text
Configured / locally verified
Production verification: NOT VERIFIED
```

That is stronger than inventing proof.

## App attestation / abuse controls

Treat monitoring, enforcement, and replay protection as separate states.

Do not enable enforcement solely because the feature exists. First gather legitimate traffic evidence, identify affected clients, define exact targets, and plan rollback.

Provider webhooks should use their correct trust mechanism, such as signature/HMAC verification and idempotency, rather than client attestation designed for browser/app traffic.

## Halt rule

If a denial test unexpectedly succeeds, or a test affects a real user/provider action, stop immediately and report the observed state before continuing.
