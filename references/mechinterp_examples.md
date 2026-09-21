# Mechanistic-Interpretability Figure References

These notes summarize reusable visual grammar from strong nearby papers. They are not templates to clone.

## Progress Measures for Grokking via Mechanistic Interpretability

### Visual pattern
- mechanism diagram beside quantitative evidence;
- multiple complementary measurements supporting one training-dynamics story;
- dense analysis of weights, activations, ablations, and derived progress measures.

### Why it works
The figures do not merely report that performance changes. They connect:
- a learned algorithm;
- mechanistic evidence;
- intervention evidence;
- training dynamics.

### Reusable lesson
When the paper has an explanatory mechanism, make the figure show both:
1. what the mechanism is;
2. how the quantitative evidence supports it.

---

## Towards Best Practices of Activation Patching in Language Models

### Visual pattern
- method schematic;
- multi-setting comparisons;
- dense curves across layers / windows / tasks;
- direct comparison of methodological choices.

### Why it works
Methodological degrees of freedom become visible empirical objects rather than prose caveats.

### Reusable lesson
If the scientific claim concerns sensitivity to methodology, expose:
- many settings;
- many observations;
- shared axes;
- the contrast itself.

Do not summarize methodological instability with one aggregate number.

---

## Is This the Subspace You Are Looking For?

### Visual pattern
- conceptual geometry;
- distributions;
- quantitative comparison tables;
- success and failure cases.

### Why it works
The conceptual counterexample and real-model evidence reinforce each other.

### Reusable lesson
For methodological failure modes:
- show the geometric / conceptual reason;
- then show empirical consequence;
- then show a success case or boundary condition.

---

## The Unreasonable Ineffectiveness of the Deeper Layers

### Visual pattern
- intervention pipeline schematic;
- pruning curves;
- multi-model comparisons;
- large layer/block-size matrices;
- benchmark and loss behavior shown together.

### Why it works
The reader sees the search space and the consequences simultaneously.

### Reusable lesson
If the experiment sweeps many layers / block sizes / models, show the sweep. Do not collapse it to the selected optimum alone.

---

## The Remarkable Robustness of LLMs: Stages of Inference?

### Visual pattern
- multi-model layerwise intervention curves;
- representation-similarity matrices;
- probing curves;
- neuron / norm statistics;
- multiple mechanistic signatures supporting one hypothesis.

### Why it works
The hypothesis is supported by several complementary measurement families.

### Reusable lesson
For a unifying hypothesis, use a figure package with:
- behavioral intervention evidence;
- representation-level evidence;
- probe / mechanistic evidence;
- aligned depth axes.

---

## Layer Importance for Mathematical Reasoning is Forged in Pre-Training and Invariant after Post-Training

### Visual pattern
- four model variants on the same layerwise axes;
- multiple reasoning tasks;
- direct layer-ablation curves;
- representation-analysis curves.

### Why it works
Critical-layer structure is visually obvious because many variants and tasks are overlaid consistently.

### Reusable lesson
When comparing model variants:
- keep layer axis aligned;
- show the curves directly;
- avoid reducing each model to one “critical layer” scalar.

---

# Cross-paper visual principles

Across these papers, strong figures repeatedly:

1. expose layerwise structure;
2. show multiple models / tasks / variants directly;
3. combine matrices, scatters, curves, and intervals when they answer different subquestions;
4. use small multiples instead of giant legends;
5. pair raw/fine-grained evidence with summaries;
6. treat the figure as part of the scientific argument, not decoration;
7. keep aesthetics academic rather than dashboard-like.
