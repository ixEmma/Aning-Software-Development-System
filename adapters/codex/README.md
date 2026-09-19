# Codex adapter

## Purpose

Expose the Aning Software Development System to Codex without making Codex-specific assumptions part of the core files.

## Current status

**PLANNING ONLY / adapter not installation-verified yet.**

Do not publish a one-command installer until the current Codex custom-agent and skill locations, supported formats, and selective-install behavior have been verified on Emmanuel's machine.

## Intended integration

Codex should receive:

1. project-local `AGENTS.md` generated from `templates/PROJECT_AGENTS.md`;
2. access to this repository's core rules;
3. only the specialist agents/skills needed for the task;
4. project-specific product documentation as higher-priority truth.

## Desired behavior

A Codex task should be able to say, conceptually:

```text
Use the Aning small-fix workflow.
Use Minimal Change Engineer.
Review with Code Reviewer.
Verify with Reality Checker.
```

The exact command/invocation syntax belongs here only after verification.

## Next verification

Before installation documentation is finalized:
- confirm Codex global custom-agent path on Windows;
- confirm accepted custom-agent file format;
- confirm whether reusable skills have a native install location;
- test one agent in a disposable repository;
- test project-local AGENTS.md precedence;
- test that no global rule overrides project-specific truth incorrectly.
