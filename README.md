# ICLR Image Skill

A reusable figure-design skill for experimental ML papers, especially ICLR / NeurIPS / ICML work involving:

- mechanistic interpretability;
- language-model interventions;
- layer / block / head analysis;
- longitudinal training studies;
- multi-model comparisons;
- ablations, probes, and representation geometry.

The skill is built around one principle:

> **Expose the experimental tensor instead of collapsing rich evidence into a few scalar summaries.**

It is designed to avoid three common failure modes:

1. polished-but-empty infographic figures;
2. dashboard-like research figures;
3. sparse “undergraduate lab report” plots that hide the actual experimental depth.

## Files

- `SKILL.md` — core workflow and rules.
- `references/figure_grammar.md` — decision rules for choosing research-figure structures.
- `references/mechinterp_examples.md` — visual grammar distilled from strong mechanistic-interpretability papers.
- `references/typography_and_layout.md` — conference-paper typography, layout, color, and density guidance.
- `references/anti_patterns.md` — failure modes and QA checklist.

## Intended workflow

1. Inventory the finest-grained experimental data.
2. Identify the natural tensor: e.g. `model × checkpoint × layer × run × metric`.
3. Decide which dimensions need to be visible.
4. Choose a figure grammar: heatmap, small multiples, scatter, effect-size plot, pairwise matrix, etc.
5. Render from source data.
6. Inspect at paper-column size.
7. Audit for scientific and visual failure modes.

The skill favors **evidence density, scientific legibility, and reviewer trust** over decorative polish.
