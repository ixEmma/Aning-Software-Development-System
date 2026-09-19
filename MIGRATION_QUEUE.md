# Migration queue

The foundation intentionally grows from proven reusable knowledge rather than collecting every framework.

## Restored from Emmanuel's existing system

The September 2026 audit restored these first-class modules:
- production-readiness standard and Six Gates;
- evidence maturity: Detected / Configured / Verified / Measured;
- delivery status: local / CI / deployed / production verified;
- clean CI/CD and release gates;
- trusted-boundary / authorization verification;
- backup, restore, RPO/RTO, and rollback drills;
- Firebase dependency-aware release procedure;
- observability and incident response;
- production-readiness review template;
- Lensora production-engineering case study.

These should not be replaced by lighter external workflow conventions.

## Next candidates

### Development system
- WordPress/client-site workflow pack based on real Amplify/1st Providence procedures;
- payment/webhook/idempotency skill if repeated across projects;
- data migration/backfill skill based on proven dry-run/canary/resume patterns;
- dependency/security-audit triage skill;
- optional external-review loop only when the chosen service is actually connected and useful.

### CI/CD by stack
Keep the general CI/CD skill canonical. Add stack adapters only after repeated use justifies them:
- Vercel/Next.js;
- WordPress;
- non-Firebase Node backends;
- self-hosted/VPS/Dokploy.

### Design
The top-level design architecture is migrated.

Potential next atomic skills from Notion:
- personality and brand energy;
- color personality / palette engine;
- typography, components, and surfaces;
- design archetypes;
- product-specific design guides;
- visual-reference analysis schema;
- design evidence/pattern maturity.

Do not migrate them as one giant prompt. Keep them atomic.

### Project adapters
Create project-local packs only when useful:
- Lensora
- PostPatch
- ReplaceIt
- AningDesign

Each project keeps its own product truth in its own repository.

### Media and other domains
Video Editing has its own strong repository-contract concept in Notion. Keep it a separate domain system unless a genuinely shared skill belongs here.

### Copywriting
Router + Schwartz + Sugarman + Hopkins are migrated.

Future additions should be evidence-backed and remain separate skills rather than being blended into one mega-prompt.

## Migration test

Before adding a new skill ask:

1. Have we used this knowledge more than once?
2. Does it change execution quality?
3. Is it stable enough to codify?
4. Is it atomic enough to invoke selectively?
5. Are source/license rights clear?
6. Can we test whether the agent followed it?

If not, leave it in Notion until it matures.
