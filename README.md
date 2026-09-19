# Aning Software Development System

A personal, model-agnostic operating system for building software with AI agents.

This repository is the canonical executable layer for Emmanuel Aning's development workflow. It combines product judgment, bounded implementation, specialist agents, reusable skills, evidence-based verification, and controlled release practices without turning normal development into bureaucracy.

## Philosophy

```text
inspect -> understand -> plan -> approve -> implement narrowly -> review -> verify -> ship with permission
```

Each product repository remains the source of truth for its own product decisions, architecture, pricing, limits, and release rules.

## Layers

- `AGENTS.md` - master router and non-negotiable rules.
- `core/` - shared execution principles and lifecycle.
- `agents/` - reusable specialist roles.
- `skills/` - atomic reusable techniques.
- `workflows/` - task-shaped combinations of agents and skills.
- `templates/` - project-local starting documents.
- `adapters/` - model/tool-specific integration.
- `sources/` - provenance and migration history.

## Default workflow

```text
Emmanuel
   |
   v
Plan only when useful
   |
   v
One appropriate builder
   |
   v
Code Reviewer
   |
   v
Reality Checker
   |
   v
Emmanuel approves merge/deploy
```

## Status vocabulary

- **PLANNING ONLY** - inspection, reasoning, recommendations. No writes.
- **READY FOR GO** - scope is approved. Execution has not happened.
- **EXECUTED LIVE** - the approved change was written and verified.

Planning, implementation, commit, deployment, and production verification are separate states.

## Model-agnostic rule

Core instructions describe what **the agent** should do. Codex, Claude Code, Cursor, ChatGPT, local models, and future tools belong in adapters. The workflow should survive model changes.
