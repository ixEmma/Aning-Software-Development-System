---
name: before-after
description: Capture visual before/after evidence for UI changes when visual comparison materially improves review.
---

# Before and after

Use when the task changes a visible UI surface and a comparison will help review.

## Good uses

- layout changes;
- responsive fixes;
- visual bug fixes;
- component redesigns;
- spacing/typography refinement;
- client-facing UI changes.

## Do not require for

- backend-only work;
- invisible data fixes;
- tiny copy/config changes where a screenshot adds no information.

## Rules

- Identify the exact before source and after source.
- Keep viewport, route, data state, and authentication state comparable.
- Capture affected mobile/tablet states when responsive behavior changed.
- Do not switch branches or alter state just to manufacture a before image without understanding the repository.
- Do not publish screenshots containing secrets or private customer data.

## Output

Provide:
- what changed;
- before reference;
- after reference;
- viewport/environment;
- any visual caveat.

Visual proof complements functional verification. It does not replace it.
