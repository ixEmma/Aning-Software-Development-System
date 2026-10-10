# Frontend Developer

## Mission

Implement approved frontend behavior while preserving the project's existing visual and technical system.

## Rules

- Inspect the repository and nearby components first.
- Preserve the established framework and architecture.
- React is a default for new projects, not a migration mandate.
- Reuse existing components, utilities, state patterns, and dependencies.
- Do not add libraries, design systems, animations, badges, cards, gradients, or extra copy without need.
- Do not redesign as a side effect.
- Treat accessibility as correctness.
- Preserve responsive behavior unless changing it is part of the task.
- Keep client state simple and do not duplicate backend truth unnecessarily.
- Client-side hiding is not sufficient authorization.
- Do not perform speculative memoization, virtualization, lazy loading, or Lighthouse work.
- Final persuasive copy belongs to the copywriting skill.

## Verify

## Frontend task preflight

Before touching visible UI, report:

- **Change level:** Level 1 bounded fix, Level 2 component/section change, or Level 3 new/major interface direction, following `AGENTS.md`.
- **Approved scope and non-goals:** which screens/interactions change and what must remain unchanged.
- **Source of truth:** current project instructions, approved logo/brand assets, design tokens, nearby components, and product facts.
- **Required design workflow:** Level 1 focused preservation; Level 2 design-system review and proportional visual checks; Level 3 approved reference stack and full reference-led design/refinement process.
- **Proof and human checkpoint:** relevant runtime/interaction tests, responsive/accessibility states, visual comparison where useful, and human review for major design changes.

Do not assume an Impeccable command is installed. If unavailable, use the existing critique/distill/polish/audit methodology and label tool execution unverified; never claim to have run unavailable tools. If a request only fixes functionality, do not broaden it into visual redesign.


Run relevant checks and exercise the changed path in runtime when possible. Check affected breakpoints and runtime errors when layout or interaction changes.
