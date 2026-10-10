# Frontend design review workflow

Use alongside `AGENTS.md` and the project-specific source of truth for any visible UI task. This is a routing and review contract, not permission to implement a redesign.

## Preflight
1. Inspect the project's current branch, worktree, instructions, design-system tokens, and affected components.
2. State affected surfaces, approved scope, non-goals, and risk.
3. Classify **Level 1** bounded fix, **Level 2** component/section change, or **Level 3** new or major design direction.
4. State proof required and any human checkpoints before writing.

## Evidence by level
| Level | Before implementation | Verification | Human gate |
| --- | --- | --- | --- |
| 1 | Existing design and bounded defect | Focused runtime check, viewport/state where relevant | Only normal merge authorization |
| 2 | Current project design system and relevant patterns | Interactions, responsive/accessibility checks; useful before/after evidence | Review significant visual deviations |
| 3 | Reference research, reusable-code license check, approved reference stack | Functional QA, critique -> distill -> polish -> audit, desktop/mobile visual evidence | Explicit owner approval for reference direction before implementation and final visual acceptance before design approval |

Never treat a test pass, PR checkbox, or AI self-review as human approval. Preserve the project's existing behavior, accessibility, brand, privacy, and architecture. If Impeccable is unavailable, use the documented critique/distill/polish/audit methodology and report it as manual review, **not** executed Impeccable commands.

## PR evidence contract
The project's PR must accurately identify the design level, scope, affected routes/states, evidence and limitations. Non-UI work may state `Not applicable`; do not invent screenshots or audits. For major design changes, record the owner's actual reference-direction and final visual approval links or notes. A project CI check may require these fields but cannot independently certify aesthetic quality or the authenticity of approvals.

## Completion
Use Code Reviewer and Reality Checker proportionately. Record test commands and outcomes, what is unverified, deferred issues, exact commit, and whether merge, deployment or production verification happened. Never merge or deploy without separate permission.
