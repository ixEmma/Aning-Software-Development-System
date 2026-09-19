# Architecture

## Product context

- Product:
- Primary users:
- Core outcome:
- Critical flows:

## System overview

Describe the frontend, trusted backend, data stores, storage, integrations, and hosting.

## Source of truth

For every critical domain, identify the authoritative source.

Examples:
- identity:
- plan/entitlement:
- payment:
- event ownership:
- uploaded media:
- analytics conversion:
- pricing:

## Trust boundaries

Document:
- public/client-controlled input;
- authenticated user boundary;
- privileged/admin boundary;
- trusted server execution;
- external providers.

Sensitive client input must not automatically become trusted server state.

## Data model

Describe important entities, ownership, relationships, and deletion behavior.

## Auth and authorization

Authentication proves identity. Authorization controls access.

Document owner/admin/member rules and server or security-rule enforcement.

## External integrations

For each integration:
- purpose;
- credentials/secrets location;
- request direction;
- retry/duplicate behavior;
- failure mode;
- source of truth.

## Failure and recovery

List meaningful failure modes and expected behavior.

## Deployment

Document environment(s), dependency order, rollback, and any manual checkpoints.

## Observability

Document the smallest useful logs, metrics, alerts, and error capture for this product.

## Decisions

Link major ADRs. Do not use ADRs for trivial implementation details.
