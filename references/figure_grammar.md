# Figure Grammar

This file is a decision guide for selecting research-figure structures.

## 1. Start from the scientific relationship

### Layer × checkpoint or component × checkpoint

Default:
- heatmap;
- small-multiple heatmaps across models/datasets;
- heatmap + trajectory summary.

Use when scalar means hide depth structure.

Examples:
- block-bypass response across training;
- head importance across checkpoints;
- feature activation across layers.

### Early vs late / source vs target

Default:
- scatter with identity line;
- paired slope only when there are few identities;
- source-target matrix when many checkpoint pairs exist.

Useful annotations:
- Spearman rho;
- highlighted selected components;
- bottom-k / top-k region;
- confidence ellipse only if scientifically meaningful.

### Multiple independent runs

Default:
- thin run-level trajectories + thick aggregate;
- swarm / strip / forest for effect sizes;
- run × layer heatmap strips.

Never show only a mean when run variation matters.

### Multiple model families

Default:
- small multiples with common visual grammar;
- common units/scales where valid;
- shared colorbar;
- compact model labels.

Do not collapse heterogeneous models into one average merely for cleanliness.

### Source checkpoint × target checkpoint

Default:
- pairwise matrix.

Examples:
- rank correspondence;
- transfer;
- stale-selection regret;
- representation similarity;
- checkpoint reuse cost.

### Numeric relationship between two scientific quantities

Default:
- scatter;
- identity/reference line where meaningful;
- raw observations;
- fit only if justified;
- direct correlation/effect statistic.

Examples:
- geometry vs sensitivity;
- local perturbation vs final effect;
- early response vs late response.

### Intervention magnitude with uncertainty

Default:
- forest / point + interval;
- zero reference for signed effects;
- raw run-level points when possible.

### Mechanism / intervention setup

Default:
- compact schematic occupying a minority of the figure;
- empirical panel beside or below it.

Avoid making the entire main figure a flowchart.

---

## 2. Preferred compound figure templates

### Template A — Controlled replication

```
(a) Dataset A heatmap      (b) Dataset B heatmap
(c) early-vs-final scatter (d) layerwise delta
(e) run trajectories       (f) endpoint effects
```

Best for:
- repeated runs;
- multiple datasets;
- longitudinal changes.

### Template B — Cross-model heterogeneity

```
(a) compact mean trajectories
(b–f) aligned layer × checkpoint heatmaps
(g) endpoint effect summary
```

Best for:
- released model trajectories;
- model-family comparisons.

### Template C — Temporal persistence

```
(a) checkpoint × checkpoint rank matrix
(b) early-vs-final scatter
(c) block × checkpoint rank/selection matrix
(d) source × target retention/regret matrix
(e) cross-model summary
```

Best for:
- persistence;
- transfer;
- changing selections.

### Template D — Mechanistic explanation

```
(a) conceptual decomposition
(b) perturbation propagation curves / matrix
(c) margin-controlled effect
(d) geometry-vs-sensitivity scatter
(e) contrasting-model validation
```

Best for:
- moving from characterization to explanation.

---

## 3. When not to use a chart

A table is better when:
- exact lookup is primary;
- there are only a handful of scalar values;
- visual encoding adds no comparison benefit.

A schematic is better when:
- the key challenge is explaining computation flow rather than quantitative comparison.

Text is better when:
- the point is a caveat or definition that would otherwise clutter a panel.

---

## 4. Evidence-density rule

Before accepting a figure, ask:

- What is the finest-grained data?
- Which dimensions are visible?
- Which were collapsed?
- Was each collapse scientifically necessary?

If a high-dimensional experiment becomes a three-point line chart by default, reconsider the design.
