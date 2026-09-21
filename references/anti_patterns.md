# Anti-Patterns and QA Checklist

## 1. Dashboard figure

Symptoms:
- card-like panels;
- giant KPI values;
- decorative separators;
- UI labels;
- too much empty space;
- visually unrelated mini-widgets.

Fix:
- use a strict research-figure grid;
- enlarge empirical plots;
- reduce prose;
- align axes and titles.

## 2. Infographic figure

Symptoms:
- giant claim headline;
- long subtitle;
- icons;
- large arrows;
- little raw data;
- educational poster feel.

Fix:
- move prose to caption;
- shrink schematic;
- add real empirical panels.

## 3. Undergraduate lab-report figure

Symptoms:
- default Matplotlib;
- 3 points connected by a line;
- one series;
- no uncertainty;
- no run-level evidence;
- no layerwise structure.

Fix:
- return to source data;
- expose layer/run/checkpoint dimensions;
- add fine-grained evidence.

## 4. Artificial complexity

Symptoms:
- decorative heatmaps;
- redundant metrics;
- unjustified regression;
- fake interpolation;
- extra panels with the same conclusion;
- many colors without semantics.

Fix:
- every panel must answer a distinct scientific subquestion.

## 5. Over-collapsed evidence

Symptoms:
- high-dimensional source data;
- only mean trajectory shown;
- model heterogeneity hidden;
- pairwise structure summarized by one endpoint.

Fix:
- heatmap;
- small multiples;
- pairwise matrix;
- raw + aggregate.

## 6. Pseudoreplication

Symptoms:
- thousands of token/layer points visually imply thousands of independent replications;
- confidence intervals computed at the wrong unit.

Fix:
- make independent run/seed unit explicit;
- show run-level summaries;
- distinguish within-run observations from independent runs.

## 7. Scale mismatch

Symptoms:
- small multiples use different y-scales without disclosure;
- heatmaps use incomparable color ranges;
- axis truncation exaggerates small effects.

Fix:
- shared scales when scientifically valid;
- explicit annotation when scales differ.

## 8. Color overload

Symptoms:
- every layer/model has a saturated unique color;
- several unrelated colormaps in one figure;
- color semantics change panel to panel.

Fix:
- establish global semantic palette;
- use faceting/direct labels for identity.

---

# Final QA

## Science
- [ ] Every mark traces to source data or a documented derivation.
- [ ] No fake checkpoints or interpolated observations are presented as measured.
- [ ] Uncertainty is real and correctly defined.
- [ ] Independent experimental unit is respected.
- [ ] Shared-run / shared-data dependence is disclosed where relevant.

## Structure
- [ ] Figure supports one main scientific argument.
- [ ] Every panel answers a distinct subquestion.
- [ ] Fine-grained evidence is visible where available.
- [ ] Summary statistics do not replace all raw structure.
- [ ] Primary panel is visually dominant.

## Style
- [ ] No dashboard aesthetic.
- [ ] No marketing headline.
- [ ] Typography is manuscript-compatible.
- [ ] Panel boxes and titles align.
- [ ] Color has stable semantics.
- [ ] Figure is legible at paper size.

## Reviewer test
After 10 seconds:
- [ ] I know what experiment was run.
- [ ] I see the main pattern.
- [ ] I can tell how much evidence supports it.
