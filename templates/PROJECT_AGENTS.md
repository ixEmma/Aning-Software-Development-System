# Project agent rules

Copy and adapt this file into a product repository as `AGENTS.md`.

## Project source of truth

List the documents agents must read before editing:

- README:
- Product/PRD:
- Architecture:
- Current implementation plan:
- Release checklist:
- Pricing/entitlement source:
- Design system:
- Other:

Project-specific rules override the general Aning Software Development System.

## Stack

- Frontend:
- Backend:
- Database:
- Auth:
- Storage:
- Hosting:
- Payments:
- Analytics/tracking:

## Commands

- Install:
- Dev:
- Typecheck:
- Lint:
- Unit tests:
- Integration tests:
- Build:
- Other verification:

Do not invent commands. Inspect the repository first.

## Hard invariants

Record rules that must not be broken, for example:
- ownership/security boundaries;
- pricing/entitlement behavior;
- data retention/deletion rules;
- critical backward compatibility;
- protected production resources;
- required accessibility behavior.

## Workflow

Use:
- `PLANNING ONLY`
- `READY FOR GO`
- `EXECUTED LIVE`

Prefer the smallest appropriate workflow.

Do not merge or deploy without explicit approval.

## Project-specific release gates

List required gates such as:
- product/pricing synchronization;
- functional QA;
- visual refinement;
- production smoke tests;
- client approval;
- documentation update.

## Copy and design

Persuasive copy uses the Aning copywriting router.

Major design direction uses the Aning design-architecture and proven-reference workflow when relevant.

## Production safety

Record:
- production project/account identifiers without secrets;
- staging/test environment;
- rollback approach;
- actions requiring human/manual approval.

Never paste or print secret values merely to prove they exist.
