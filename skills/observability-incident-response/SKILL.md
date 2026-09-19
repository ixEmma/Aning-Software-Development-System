---
name: observability-incident-response
description: Use when designing or verifying logs, metrics, alerts, uptime checks, incident procedures, or operational notification delivery.
---

# Observability and incident response

Derived from Emmanuel's production-readiness standard and Lensora operational hardening.

## Observability questions

A production system should be able to answer, where relevant:

- **Logs** - what happened?
- **Metrics** - how often/how much?
- **Traces** - where did time or failure occur?
- **Alerts** - who is notified, for what condition, and when?

Do not add every observability mechanism to every app. Match depth to risk and readiness level.

## Alert maturity

Keep these states separate:

```text
error ingestion verified
alert signal configured
notification channel configured
alert policy configured
test condition generated
notification delivery verified
operator acknowledgement verified
```

Do not claim alerting is verified merely because logs exist or a policy is enabled.

## Signal quality

Use signals that actually represent the operational condition.

Do not invent highly specific alerts when the available metric cannot distinguish failure from normal product outcomes.

Prefer conservative thresholds over notification floods.

Document:
- signal;
- threshold/window;
- severity;
- owner;
- notification destination;
- autoclose/recovery behavior;
- known blind spots.

## Controlled notification test

When safe and approved:
1. generate the smallest non-destructive synthetic signal;
2. verify monitoring receives it;
3. verify the policy evaluates it;
4. verify the intended notification arrives;
5. remove temporary test policy/event scaffolding when it is no longer needed.

If owner receipt cannot be confirmed:

```text
Policy: Configured
Signal ingestion: Verified
Notification delivery: Not Verified
```

## Incident severity

Use a project-appropriate model. A useful default:

- **SEV-1** - critical outage, data loss, financial/security incident.
- **SEV-2** - major functionality degraded.
- **SEV-3** - limited-impact issue.
- **SEV-4** - minor operational issue.

## Incident flow

```text
Detect
-> Assess
-> Contain
-> Recover
-> Verify
-> Communicate
-> Postmortem
```

During an incident:
- freeze unrelated changes;
- establish scope before fixing;
- protect evidence/logs;
- prefer reversible containment;
- avoid speculative config changes;
- verify recovery before declaring closure;
- record the root cause and prevention work separately.

## Privacy

Logs and alerts should not expose secrets, raw sensitive content, authorization headers, private customer data, or full provider payloads unless explicitly required and safely governed.
