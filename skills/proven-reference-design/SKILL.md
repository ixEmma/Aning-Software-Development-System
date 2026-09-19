---
name: proven-reference-design
description: Use for major website or product-interface work when strong references exist. Research proven patterns first, adapt them to the real product, refine after functional QA, then verify production quality.
---

# Proven reference design workflow

Short form:

```text
Proven -> Adapt -> Refine -> Verify
```

## 1. Understand the real product

Before design/code establish:
- product/business type;
- target audience;
- primary action;
- required pages/flows/features;
- brand assets;
- real content/data;
- technical constraints;
- demo versus production scope.

The product definition controls the reference search.

## 2. Research proven references

Look for relevant:
- mature products;
- strong open-source implementations;
- suitable templates;
- competitors;
- design systems;
- category leaders;
- component-specific examples.

Prioritize relevance over popularity.

## 3. Qualify references

Classify each candidate:

- **Code Foundation** - reusable only when license and stack allow.
- **Visual Reference** - composition/hierarchy/style inspiration only.
- **Component Reference** - solves one concrete UI problem.
- **UX Reference** - useful workflow/information-architecture pattern.

Public code is not automatically reusable. Check the license.

## 4. Approve a reference stack

Prefer one dominant reference and a small number of secondary references with explicit jobs.

Avoid a collage of unrelated popular patterns.

## 5. Clone or reconstruct

If reuse is permitted, inspect the source before changing it.

Otherwise reconstruct the transferable logic with original components.

Preserve useful structure, not another company's identity.

## 6. Adapt to the real brand/product

Replace:
- logos;
- colors;
- imagery;
- placeholder copy;
- fake/demo data;
- generic CTAs;
- irrelevant template features.

Add what the actual product requires.

## 7. Functional gate before polish

Verify:
- routes/navigation;
- responsive states;
- buttons/links;
- forms/primary actions;
- content accuracy;
- image loading;
- component states;
- required features.

Do not polish around broken behavior.

## 8. Anti-slop refinement

After function is coherent:

1. **Critique** - identify weak hierarchy, cognitive load, generic AI patterns.
2. **Distill** - remove unnecessary controls, decoration, duplicated treatments, and feature accretion.
3. **Polish** - refine spacing, typography, hierarchy, alignment, states, and interaction detail.
4. **Audit** - check accessibility, responsiveness, performance, theming, and implementation quality.

If an Impeccable-style tool is available, it may perform these passes. The workflow itself does not depend on that tool.

Common patterns to challenge when unjustified:
- cards inside cards;
- excessive rounded containers;
- gratuitous pills/badges;
- generic purple gradients;
- decorative glassmorphism;
- identical section treatments;
- status chips everywhere;
- arbitrary blobs/borders;
- repeated icon-card grids;
- unnecessary animation;
- generic AI headings/copy;
- fake metrics/social proof;
- too many CTAs.

Do not remove a pattern merely because AI often uses it. Remove it when the product, brand, hierarchy, or task does not justify it.

## 9. Human review

The agent does not have final aesthetic authority.

Check:
- does it fit the brand?;
- does it resemble the reference too closely?;
- is the primary action obvious?;
- is hierarchy intentional?;
- is the product understandable quickly?;
- are references still helping rather than constraining?;

## 10. Capture the real design system

Document the design system after enough real UI exists to infer it:
- type;
- color roles;
- spacing;
- radii;
- controls;
- containers/cards;
- states;
- imagery;
- responsive conventions;
- reusable components.

Do not fabricate a complete design system before the product exists.

## Final production QA

Verify accessibility, responsiveness, performance where relevant, SEO/metadata when relevant, forms/conversions, analytics, broken links, factual content, and deployment output.

Fix high-severity functional issues before low-priority polish.
