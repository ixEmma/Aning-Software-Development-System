# Production readiness review

## Project identity

- Application:
- Version / commit:
- Owner:
- Review date:
- Target readiness level: Level 0 / 1 / 2 / 3 / 4
- Environment:
- Production URL:
- Repository:
- Primary platform:

## Architecture summary

- Frontend:
- Backend:
- Database:
- Storage:
- Authentication:
- Hosting:
- Regions:
- Payments:
- External dependencies:

## Critical flows and sources of truth

| Flow | Source of truth | Trust boundary | Failure concern |
|---|---|---|---|
| Authentication | | | |
| Authorization/ownership | | | |
| Payment/entitlement | | | |
| Upload/media | | | |
| Destructive actions | | | |

Add/remove flows as needed.

## Capability matrix

Use:
- architecture status: Implemented / Platform Managed / Partially Implemented / Planned / Not Required / Not Verified
- evidence maturity: Detected / Configured / Verified / Measured / Not Verified / Failed

| Capability | Architecture status | Evidence maturity | Provider/implementation | Evidence | Known gap / next action |
|---|---|---|---|---|---|
| CI clean install | | | | | |
| Authorization | | | | | |
| Backup | | | | | |
| Restore | | | | | |
| Rollback | | | | | |
| Logging | | | | | |
| Alert delivery | | | | | |

## Gate A - Architecture

- [ ] System overview current
- [ ] Critical flows documented
- [ ] Trust boundaries documented
- [ ] Platform-managed vs app-managed responsibilities clear
- [ ] Major ADRs current

Evidence / gaps:

## Gate B - Security

- [ ] Authentication verified
- [ ] Authorization/ownership verified at appropriate environment
- [ ] Server-side validation verified
- [ ] Secrets protected
- [ ] Abuse controls evaluated
- [ ] Threat model completed when required

Evidence / gaps:

## Gate C - Reliability

- [ ] Failure modes evaluated
- [ ] Backup strategy documented
- [ ] Recent backup evidence exists when required
- [ ] Restore tested safely when required
- [ ] RPO/RTO decisions documented
- [ ] Retry/timeout/idempotency behavior reviewed

Evidence / gaps:

## Gate D - Performance and scale

- [ ] Important latency/capacity measured when relevant
- [ ] Quotas/rate limits/concurrency evaluated
- [ ] Scaling/caching decisions documented
- [ ] Cost/capacity assumptions recorded

Evidence / gaps:

## Gate E - Operations

- [ ] CI/CD documented
- [ ] Clean CI gate verified
- [ ] Deployment environments documented
- [ ] Rollback path verified where required
- [ ] Logs/metrics appropriate to risk
- [ ] Alert delivery verified or clearly Not Verified
- [ ] Incident process documented
- [ ] Dependency failures considered

Evidence / gaps:

## Gate F - Product and governance

- [ ] Pricing/entitlement truth synchronized when applicable
- [ ] Privacy/retention/deletion documented
- [ ] Backward-compatibility/versioning decision recorded
- [ ] Known limitations recorded
- [ ] Deferred work recorded

Evidence / gaps:

## Readiness result

- Target level:
- Result:
- Blocking findings:
- Non-blocking gaps:
- Controls Not Verified:
- Evidence that may become stale:
- Next approved verification:
- Deployment recommendation:
