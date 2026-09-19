---
name: evidence-driven-testing
description: Choose and capture evidence that proves a change works. Scale evidence depth to task risk instead of recording every change.
---

# Evidence-driven testing

## Principle

A claim of completion should be backed by evidence appropriate to the behavior.

Do not create evidence artifacts merely for ceremony.

## Evidence levels

### Level 1: focused proof
Use for small logic or configuration fixes:
- test output;
- before/after value;
- log or payload;
- focused runtime reproduction.

### Level 2: runtime proof
Use for normal features:
- relevant automated checks;
- actual user-flow verification;
- screenshots for important visual states when useful.

### Level 3: release proof
Use for high-risk flows, large UI changes, client sign-off, or release candidates:
- exact revision/environment;
- named test targets;
- runtime walkthrough;
- screenshots or video where visual/interactivity matters;
- supporting logs/payloads/results;
- clear PASS/FAIL/UNVERIFIED assertions.

## Capture rules

- Record the exact revision or deployment being tested.
- Show the actual state, not a staged simulation.
- Do not expose secrets, customer data, payment details, or unnecessary personal data.
- For a bug fix, preserve evidence of the old failure when practical.
- If a test cannot be performed safely, mark it UNVERIFIED rather than pretending.

## UI video

Screen recording is optional. Use it when a multi-step visual interaction is hard to prove concisely with tests/screenshots or when a client/reviewer benefits from seeing the full journey.

Do not record every tiny change.

## Result

Every test target should end as:
- PASS;
- FAIL;
- UNVERIFIED.

Evidence should make the status independently understandable.
