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

Use the smallest set that materially helps.

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
