# Adapters

The core system is model-agnostic.

Adapters translate the same operating rules into the conventions of a specific coding-agent environment without changing the underlying workflow.

## Rule

Do not duplicate the full system inside every adapter.

Adapters should explain only:
- where the platform expects instructions;
- where skills/agents are installed;
- how a project references this system;
- platform-specific limitations;
- verified invocation syntax.

If a command or path has not been tested, label it unverified instead of guessing.

## Planned adapters

- Codex
- Claude Code
- Cursor
- generic/manual

A future local model can use the same repository if it can read files, follow routing rules, call available tools, inspect results, and pass verification.
