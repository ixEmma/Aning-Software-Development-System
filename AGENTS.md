# Aning Software Development System - master agent rules

## Authority order

When instructions conflict:

1. Emmanuel's direct instruction for the current task.
2. Current project-specific documentation and approved decisions.
3. This repository's core operating rules and selected workflow.
4. Specialist agent defaults.
5. Generic framework conventions.

Do not reopen settled decisions without new evidence.

## Execution states

- **PLANNING ONLY** - inspect, research, reason, and propose. No repository, infrastructure, data, billing, or deployment writes.
- **READY FOR GO** - the scope is approved but execution has not happened.
- **EXECUTED LIVE** - the approved change was actually written and the relevant behavior was verified.

Discussion is not permission to execute.

## Delivery and evidence state

Execution permission is not delivery status.

Use `core/DELIVERY_STATUS.md` to distinguish Proposed, Implemented Locally, Verified Locally, Committed, CI Verified, Deployed, Production Verified, Deferred, Not Verified, and Blocked.

Use `core/EVIDENCE_MATURITY.md` for architecture/control maturity: Detected, Configured, Verified, Measured, Not Verified, Failed.

Never collapse local success, CI success, deployment, and production verification into "done."

## Default operating loop

1. Read the relevant README, project docs, task context, and nearby implementation.
2. Identify the exact problem and approved scope.
3. Choose the smallest workflow that fits.
4. Explain the intended change before code when useful.
5. Make the smallest coherent change.
6. Run proportionate verification.
7. Use Code Reviewer for independent review when implementation is non-trivial.
8. Use Reality Checker before claiming completion.
9. Do not merge or deploy without explicit approval.

## Task routing

- Product uncertainty or scope -> `agents/product-manager.md`
- Small bounded fix -> `agents/minimal-change-engineer.md`
- React/UI implementation -> `agents/frontend-developer.md`
- Firebase/data/auth/backend -> `agents/backend-architect.md`
- Independent review -> `agents/code-reviewer.md`
- Final evidence gate -> `agents/reality-checker.md`
- Organic search -> `agents/seo-specialist.md`
- Analytics/conversion tracking -> `agents/tracking-specialist.md`
- Persuasive copy -> `skills/copywriting/SKILL.md`
- Production-readiness review -> `workflows/production-readiness-audit.md`
- CI/CD or release-gate work -> `skills/ci-cd-release-gates/SKILL.md`
- Authorization/ownership/trusted-boundary proof -> `skills/trusted-boundary-verification/SKILL.md`
- Backup/restore/rollback -> `skills/recovery-and-rollback/SKILL.md`
- Firebase production release -> `skills/firebase-release/SKILL.md`
- Observability/alerts/incidents -> `skills/observability-incident-response/SKILL.md`

Use the smallest set that materially helps.


## Mandatory frontend design routing

For any task touching visible UI, classify the change **before implementation** and state the level, scope, applicable skills, evidence, and approval gate. Product-specific approved design decisions take precedence. Apply the smallest sufficient level; when uncertain, stop and clarify rather than silently widening scope.

- **Level 1 — Bounded visual fix:** spacing, overflow, alignment, or narrow UI bug without new design direction. Use the small-fix workflow and frontend agent as applicable; inspect existing design, preserve behavior, and run focused functional/viewport checks. Do not require reference research or the complete Impeccable sequence.
- **Level 2 — Component or section change:** significant change to navigation, forms, components, or existing screen composition without a new product-wide direction. Read the project's design system and relevant existing patterns; inspect affected states, capture before/after evidence when meaningful, and run functional, responsive, and accessibility checks. Use targeted critique/distill/polish/audit only when applicable.
- **Level 3 — New or major interface direction:** new landing page, substantial dashboard/page redesign, new visual language, or major UX flow. Route through `skills/design-architecture/SKILL.md` and `skills/proven-reference-design/SKILL.md`; research and qualify references, present a reference stack, and obtain approval **before** implementation. After functional QA, perform critique → distill → polish → audit (with Impeccable if installed and available; otherwise use the documented methodology and disclose the limitation). Obtain human visual approval for affected desktop/mobile states before claiming design acceptance.

A task's visible scope, risk, and change to approved design—not merely the number of edited files—determine its level. A functionality-only fix does not authorize a redesign. Do not claim that a routing statement, checklist, or successful build proves visual approval or GitHub merge enforcement. Merge/deploy still require separate permission.


## Scope discipline

- Preserve working behavior outside the requested change.
- Do not silently add adjacent features.
- Do not redesign while fixing functionality unless design work is in scope.
- Do not add packages, abstractions, infrastructure, or frameworks without demonstrated need.
- Report unrelated technical debt separately.
- Prefer reversible, bounded changes.

## Stack defaults

Preserve the current project's stack first.

For a new project with no established stack:
- React is the default frontend.
- Firebase is the default backend/data platform.

These are defaults, not migration mandates.

Where no local JavaScript/TypeScript style exists:
- use parentheses around arrow-function parameters;
- avoid unnecessary spaces inside object braces.

## Product truth and copy

Project documentation is authoritative for product behavior, pricing, limits, entitlements, and approved positioning.

Do not rewrite persuasive copy as an engineering side effect. Route marketing/sales copy through the copywriting skill.

## Verification

Evidence beats confidence. Use the smallest evidence set that can prove the requested behavior. If something cannot be proven, mark it **UNVERIFIED**.

## Git and release safety

- Prefer a focused branch for meaningful work.
- Use worktrees when parallel agents/sessions or risky isolation justify them, not automatically.
- Never force-push accepted production history.
- Never merge, deploy, publish rules/functions, change pricing, mutate production data, or perform destructive actions without explicit approval.
- Preserve unrelated/untracked work.
- Keep commits focused.

## Human checkpoints

Stop for human action when required for secrets, live credentials, real-money payment configuration, destructive production changes, DNS/domain changes, privileged ownership changes, or other irreversible actions.

## Model-agnostic core

Core files must not depend on one named model. Tool-specific behavior belongs in `adapters/`.


## Reusable skill routing

- New/major UI direction -> `skills/design-architecture/SKILL.md`
- Frontend task review and evidence -> `workflows/frontend-design-review.md`
- Reference-led interface build or anti-AI-slop refinement -> `skills/proven-reference-design/SKILL.md`
- Git branch/worktree choice -> `skills/task-isolation/SKILL.md`
- Repeated operational logic / service-boundary question -> `skills/code-structure/SKILL.md`
- Evidence capture depth -> `skills/evidence-driven-testing/SKILL.md`
- Visual comparison -> `skills/before-after/SKILL.md`
- Technical prose for commits/PRs/docs -> `skills/human-writing/SKILL.md`

Skills are invoked because the task needs them, not to increase process.
