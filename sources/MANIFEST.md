# Source and provenance manifest

This repository is a personal synthesis. It intentionally does not mirror either upstream repository wholesale.

## Emmanuel-owned sources

### Aning Software Development System - Notion
Primary lifecycle source. Distilled and rewritten for executable repository use.

### Copywriting hub - Notion
Source pages:
- Copywriting
- Schwartz Copywriting - Market Desire, Awareness & Sophistication
- Sugarman Copywriting - Slippery Slide & Buyer Psychology
- Hopkins Copywriting - Scientific Advertising, Testing & Measurable Selling

Treatment: migrated as personal skills from Emmanuel's internal paraphrased frameworks.

## External repositories

### msitarzewski/agency-agents
License: MIT.
Emmanuel fork: `ixEmma/agency-agents`

Use: specialist-role inspiration and the eight-agent curation work.
Treatment: rewritten into shorter Emmanuel-native roles rather than copying full upstream personas.

### michaelshimeles/skills
Emmanuel fork: `ixEmma/softwarefactory-skills`

The repository did not expose a repository-level license in GitHub metadata when this system was created. Some vendored sub-skills have their own licenses.

Use: workflow ideas such as isolation, evidence-driven verification, before/after proof, and human-writing cleanup.
Treatment: reimplement concepts in original language unless a specific source license clearly permits reuse.

## Future migration rule

Every imported/adapted skill should record:
- source;
- source revision when practical;
- license;
- copied vs adapted vs reimplemented;
- local modifications.

If reuse rights are unclear, reimplement the idea instead of copying text or code.


## Design system sources

### Reusable Design Taste & UI Language - Notion
Use: design decision order, intentional composition quality bar, structural DNA, personality separation, and evidence discipline.

Treatment: distilled into `skills/design-architecture/SKILL.md`.

### No-AI-Slop Design - Impeccable Workflow - Notion
Use: proven-reference research, reference qualification, brand adaptation, functional-before-polish gate, anti-slop refinement, human review, and production QA.

Treatment: distilled into `skills/proven-reference-design/SKILL.md`. The core workflow is tool-agnostic; Impeccable is optional execution tooling.


## Production engineering sources restored in September 2026

### System Architecture & Production Readiness Standard - Notion
Use: readiness levels, architecture capability status, trust boundaries, reliability, performance, backup/recovery, observability, incident response, CI/CD, rollback, Six Gates, governance.

Treatment: distilled into `core/PRODUCTION_READINESS_STANDARD.md` and `templates/PRODUCTION_READINESS_REVIEW.md`.

### V1 Evidence Workflow - Notion
Use: Detected/Configured/Verified/Measured evidence maturity, evidence-gap planning, least-privilege passive evidence first, explicit active-test approval, evidence provenance, reassessment.

Treatment: distilled into `core/EVIDENCE_MATURITY.md`, `skills/trusted-boundary-verification/SKILL.md`, and `workflows/production-readiness-audit.md`.

### Lensora production-hardening evidence - Notion and project records
Use: deterministic clean CI, real-browser CI smoke testing, safe CI initialization without production secrets, synthetic authorization proof, isolated Firestore restore, rollback anchors, alert-delivery evidence, narrow-release accounting.

Treatment: distilled into `case-studies/LENSORA_ENGINEERING_LESSONS.md` and the CI/recovery/Firebase/observability skills.

### Metric Bot foundation-hardening procedure - Notion
Use: server-validated tenant boundaries, repository-managed Firebase rules, local tests before production rules, timeout/error-path guarantees, structured privacy-safe logging, explicit owner approval gates, dependency-aware deployment.

Treatment: incorporated into trusted-boundary and production-readiness rules.

These are Emmanuel's proven procedures and take precedence over borrowed workflow conventions when they conflict.
