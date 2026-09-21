---
name: iclr-image-skill
description: Design, critique, and rebuild publication-quality figures for ICLR/NeurIPS/ICML machine-learning papers, especially mechanistic interpretability, LLM analysis, layer ablation, longitudinal experiments, and multi-model comparisons. Optimize for evidence density, scientific readability, and conference-paper visual grammar rather than dashboards, infographics, or presentation graphics.
---

# ICLR / ML Paper Figure Skill

## Purpose

Create figures that function like strong experimental figures in top-tier ML papers.

The primary objective is **not prettiness**. It is to:

1. expose the experimental structure;
2. make the scientific comparison visible;
3. preserve replication and uncertainty;
4. show enough fine-grained evidence that the result feels systematically characterized;
5. compress complexity without collapsing it into a few scalar summaries.

A successful figure should make a reviewer think:

> “This experiment was systematically characterized.”

not:

> “This is a polished summary slide.”

---

## 1. Start from the experimental tensor, not the old figure

Before plotting, inventory the finest-grained available evidence.

Typical dimensions include:

- model / model family;
- run / seed;
- checkpoint / training stage;
- layer / block / head / component;
- dataset / text panel / task;
- intervention;
- metric;
- uncertainty / bootstrap replicate;
- source checkpoint × target checkpoint.

Write down the natural tensor, e.g.

```
model × checkpoint × layer × run × metric
```

Then ask which dimensions are being hidden by the current visualization.

**Never start by merely restyling the previous figure.**

If hundreds of layer/run/checkpoint measurements exist but the plot shows three mean points, redesign the figure so the underlying structure is visible.

---

## 2. Core visual philosophy

### 2.1 Evidence density over minimalist infographic design

Do not aggressively reduce evidence to:

- one mean line;
- three large points;
- one scalar;
- a few decorative cards;
- a schematic matrix when real values exist.

Prefer scientifically meaningful combinations of:

- heatmaps;
- small multiples;
- dense scatter plots;
- paired observations;
- source-target matrices;
- multi-line comparisons;
- effect-size / forest plots;
- confidence intervals;
- representative raw observations plus aggregate summaries.

Complexity is acceptable when it is **structured**.

The target is:

> complex, but not confusing.

### 2.2 Raw evidence + summary

For important empirical claims, show two levels when possible:

**Fine-grained evidence**
- run-level values;
- layerwise values;
- checkpoint matrices;
- individual trajectories.

**Summary**
- mean / median;
- confidence interval;
- correlation;
- endpoint effect;
- fitted relationship.

Do not show only the summary when the fine-grained evidence is available.

---

## 3. Preferred research-figure grammar

### A. Intervention / mechanism schematic

Use for:
- activation patching;
- ablation;
- bypass;
- causal intervention;
- architecture flow.

Rules:
- compact;
- little prose;
- arrows and computation blocks;
- visually emphasize the changed component;
- accompany with empirical evidence when possible.

A schematic should rarely consume an entire main figure by itself.

### B. Layer × checkpoint / component × metric heatmap

Use whenever the experiment forms a natural 2-D field.

Examples:
- layer × checkpoint;
- layer × layer;
- block × block-size;
- source checkpoint × target checkpoint;
- head × layer;
- model × metric.

Heatmaps are especially useful when scalar means hide structure.

Use one quantitative color scale and shared scales across comparable panels when scientifically valid.

### C. Small multiples

Use for:
- multiple models;
- model families;
- datasets;
- seeds;
- intervention types.

Small multiples should share:
- units;
- axis semantics;
- ordering;
- time window / checkpoint normalization where appropriate;
- visual encoding.

### D. Scatter + reference / fit

Use for relationships such as:
- early response vs late response;
- geometry vs sensitivity;
- perturbation magnitude vs final effect.

Prefer:
- raw points;
- identity line when meaningful;
- direct statistic (e.g. Spearman rho);
- fit / smoother only when statistically justified;
- uncertainty band when supported.

Never add a regression line merely to make the figure look sophisticated.

### E. Dense multi-line comparison

Use when trajectory shape matters.

Show:
- thin individual runs/models;
- thicker aggregate;
- uncertainty where available.

Avoid showing only the aggregate if run variation matters.

### F. Effect-size / forest / interval plot

Use for:
- early-to-late changes;
- per-model effects;
- replication summaries;
- uncertainty intervals.

Show the zero reference for signed effects.

Prefer raw run-level points plus aggregate interval.

### G. Pairwise matrix

Use for:
- checkpoint correspondence;
- transfer;
- reuse regret;
- similarity;
- intervention cost.

Examples:

```
R_ij = rank correlation between checkpoint i and checkpoint j
G_ij = cost at checkpoint j of reusing a choice from checkpoint i
```

A pairwise matrix is often more informative than reporting only first-to-last values.

---

## 4. Figure composition

A strong ML-paper figure commonly contains **3–7 panels**.

That is acceptable if all panels form one scientific argument.

Good example:

```
(a) response heatmap
(b) second-dataset heatmap
(c) early-vs-late scatter
(d) layerwise change
(e) run-level trajectories
(f) endpoint effects
```

Bad example:

```
six unrelated panels added only to look comprehensive
```

Every panel must answer a distinct subquestion.

Prefer layouts such as:

- 2×2;
- 2×3;
- one large primary panel + two smaller supporting panels;
- one overview row + one evidence-dense matrix row.

Use strict alignment of:
- panel boundaries;
- title baselines;
- axes;
- colorbars;
- plot heights.

Avoid dashboard-card composition.

---

## 5. Typography and hierarchy

Use academic figure typography, not marketing typography.

Default guidance:
- panel label + short title: 8–9 pt bold/semibold;
- axis labels: 7–8 pt;
- tick labels: 6.5–7.5 pt;
- annotations: about 7 pt.

Use one font family consistent with the manuscript.

Usually omit:
- giant figure-level headline;
- promotional subtitle;
- explanatory paragraphs inside plots.

Prefer panel titles such as:

```
(a) Layerwise response
(b) Early versus final
(c) Perturbation propagation
```

The full scientific claim belongs primarily in the caption and surrounding text.

---

## 6. Color system

Use color semantically.

A robust default:
- blue: baseline / early / one comparison group;
- orange: late / contrast / signed alternative;
- neutral gray: background observations;
- one sequential colormap: scalar magnitude;
- one diverging colormap: signed change / correlation when needed.

Do not assign every block/model a unique saturated color unless identity is scientifically important.

Richness should come from **data structure**, not decorative color.

Do not rely on color alone when line style, marker fill, direct labels, or faceting can add redundancy.

---

## 7. Uncertainty and replication

Respect the true independent experimental unit.

Do not make token-, layer-, or prompt-level observations look like independent training replications when the run/seed is the independent unit.

Where uncertainty is available:
- show intervals with the estimate;
- identify interval meaning and level;
- preserve asymmetry;
- do not invent uncertainty.

When showing many within-run observations, pair them with run-level summaries or make dependence explicit.

---

## 8. Evidence-density check

Before approval ask:

1. How many empirical observations are visibly represented?
2. Which experimental dimensions are visible?
3. Did we collapse a high-dimensional experiment into a scalar unnecessarily?
4. Is raw variation visible?
5. Are replication and uncertainty visible?
6. Can the reader see why the conclusion follows?
7. Is any panel redundant?

If the experiment contains hundreds of layer/run/checkpoint measurements but the figure visually contains three points, redesign it.

---

## 9. Anti-patterns

### Dashboard aesthetic
Symptoms:
- card-like widgets;
- giant KPI numbers;
- UI-style labels;
- excessive whitespace;
- several unrelated miniature panels.

### Infographic aesthetic
Symptoms:
- large narrative headline;
- excessive prose;
- icons and decorative arrows;
- too little empirical evidence.

### Undergraduate lab-report aesthetic
Symptoms:
- one default line chart;
- three points connected by a line;
- default Matplotlib appearance;
- no uncertainty;
- no raw observations;
- no comparison structure.

### Artificial complexity
Symptoms:
- unnecessary regressions;
- fake interpolation;
- redundant panels;
- decorative heatmaps;
- arbitrary metrics;
- extra colors added just to look richer.

Never fabricate evidence density.

---

## 10. Workflow

### Step 1 — Data inventory

Create a short inventory containing:
- available dimensions;
- number of values along each dimension;
- finest-grained stored data;
- uncertainty / bootstrap artifacts;
- which pairwise quantities can be derived without new inference.

### Step 2 — Claim decomposition

For each figure state:
- one sentence the figure should support;
- subquestions each panel answers;
- which panel is the primary evidence;
- which panels are supporting evidence.

### Step 3 — Choose grammar

Use the decision rules in `references/figure_grammar.md`.

### Step 4 — Build from source data

Every empirical mark must trace to:
- stored data;
- a reproducible analysis;
- or an explicitly documented deterministic derivation.

No invented values.
No fake checkpoints.
No smoothing across unobserved time points unless explicitly labeled and scientifically justified.

### Step 5 — Render and inspect

Inspect the actual rendered figure:
- full size;
- paper-column size;
- grayscale;
- 10-second reviewer scan.

Check:
- clipping;
- text collisions;
- font size;
- panel alignment;
- colorbar consistency;
- scale consistency;
- whether the scientific hierarchy is obvious.

### Step 6 — Audit

Use the checklist in `references/anti_patterns.md`.

---

## 11. Reviewer test

After looking at the figure for ~10 seconds, a reviewer should be able to answer:

1. What experiment was run?
2. What is the main pattern?
3. How much evidence supports it?

If not, revise.

---

## 12. Reference style

Use the nearby ICLR/NeurIPS mechanistic-interpretability examples summarized in:

- `references/mechinterp_examples.md`
- `references/figure_grammar.md`
- `references/typography_and_layout.md`
- `references/anti_patterns.md`

Do not clone exact figures.
Extract and reuse the visual grammar.
