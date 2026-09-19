---
name: firebase-release
description: Use for Firebase production deployment planning or execution involving Hosting, Functions, Firestore indexes/rules, Storage rules, or related project resources.
---

# Firebase release procedure

Derived from Emmanuel's Aning Software Development System and Lensora production releases.

Deployment requires explicit approval.

## Preflight

Before any write:

1. Confirm repository, branch, and exact committed SHA.
2. Confirm Firebase project identity and target environment.
3. Confirm CI/local verification state.
4. Inspect intended deployment diff.
5. Identify affected Firebase resources.
6. Check current production inventory where a deploy command could delete or replace resources.
7. Record rollback anchor/version where the platform supports it.

Do not read or print secret values merely to prove they exist.

## Index safety

When Firestore index configuration changed:
- compare repository index definitions with live production inventory;
- identify drift intentionally;
- do not let a scoped feature deployment accidentally delete unrelated live indexes;
- create required new indexes before code that depends on them;
- wait until required indexes are READY before dependent production behavior is relied on.

## Dependency-aware order

The exact order is project-specific. A common safe pattern is:

1. preflight Git/CI/project identity;
2. required indexes;
3. wait for index readiness;
4. deploy only affected Functions/background jobs;
5. deploy changed Rules after verification;
6. fresh production build from the exact committed SHA;
7. deploy Hosting;
8. verify released Hosting/version identity;
9. perform bounded smoke tests.

Do not use a broad "deploy everything" command when resource dependencies or unintended changes make scoped deployment safer.

## Scoped deployment

If the release is Hosting-only, deploy Hosting only.

If one Function changed, prefer the narrowest supported Function deployment unless shared dependencies require broader scope.

Document explicitly what did **not** change, especially:
- Functions;
- Firestore rules/indexes/data;
- Storage rules/objects;
- Auth;
- secrets;
- payment configuration;
- App Check;
- IAM;
- production data.

## Production verification

After deployment:
- record Hosting/Function version or revision;
- verify production domain(s);
- confirm the expected bundle/release is live when possible;
- run only bounded smoke tests;
- check logs/errors when relevant;
- preserve previous known-good rollback anchor.

Use disposable/synthetic data where state-changing proof is required.

## Status

Keep separate:
- CI Verified;
- Deployed;
- Production Verified.

A successful Firebase CLI command proves deployment, not product behavior.
