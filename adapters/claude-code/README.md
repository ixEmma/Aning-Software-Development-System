# Claude Code adapter

## Purpose

Map the same personal operating system into Claude Code conventions.

## Current status

Adapter structure only. Installation/invocation details should be verified before they become canonical instructions.

## Intended mapping

- project rules -> project `CLAUDE.md` or supported project instruction surface;
- atomic skills -> Claude-compatible skill folders when appropriate;
- general personal rules -> user-level configuration only when they should truly apply across every project;
- project documentation remains the higher-priority product truth.

## Guardrail

Do not copy the entire repository into every project's prompt context.

Load the smallest relevant workflow, agent, and skills for the task.
