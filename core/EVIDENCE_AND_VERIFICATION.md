# Evidence and verification

## Principle

Use enough evidence to prove the task, but no more process than the risk justifies.

## Evidence hierarchy

Prefer, when applicable:

1. Reproducible runtime behavior
2. Focused automated tests
3. Build/type/lint checks relevant to the change
4. Logs, payloads, database state, provider receipts
5. Screenshots/video for visual behavior
6. Code inspection
7. Agent claims

A screenshot does not prove backend behavior. A passing test does not prove a flow it never exercises.

## Proportional verification

### Tiny fix
- focused check;
- nearby regression sanity check.

### Normal feature
- relevant automated checks;
- runtime verification of the changed path.

### UI/layout change
- runtime interaction;
- affected responsive breakpoints;
- screenshot evidence when useful.

### Auth/data/backend change
- authorized and unauthorized cases;
- read/write behavior;
- error path;
- rule/server enforcement.

### Tracking change
- event fires once;
- expected payload;
- platform debug receipt;
- CRM/downstream record when in scope;
- duplicate-event check.

### Release candidate
- project-specific release checklist;
- CI/build;
- critical-flow smoke test;
- product/pricing synchronization if applicable;
- production verification after deployment.

## Final result vocabulary

- **PASS** - acceptance criteria are proven and no blocker remains.
- **FAIL** - an acceptance criterion fails or a blocking regression is confirmed.
- **UNVERIFIED** - available evidence is insufficient.

Do not invent grades or percentages.
