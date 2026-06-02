# Visuals, Figures, and Case Studies Guide

## Goal

Make the paper visually rich in an academic, evidence-faithful way.
Figures, plots, tables, and case studies should help readers understand the story, method, evidence, and practical behavior of the work.
Treat visuals as part of the paper's reasoning, not decoration.

Use a tri-modal presentation style:

1. Text explains the claim, reasoning, and takeaway.
2. Tables preserve exact numerical comparisons, metric values, and baseline rankings.
3. Figures show mechanisms, trends, distributions, ablations, robustness behavior, workflows, and case studies.

Do not let "visual-rich" collapse into only tables.
When a figure would clarify a trend, mechanism, or case, generate or plan the figure rather than relying only on prose and tables.

## Visual Plan

For a full-paper draft or major rewrite, create a Visual Plan before finalizing the text.
The plan should list each intended visual, where it appears, what claim it supports, what data/content it uses, and whether it is complete or TODO.

Recommended visual slots:

1. Introduction: teaser, motivation figure, task illustration, failure example, or high-level contribution overview.
2. Method: pipeline figure, framework diagram, module interaction diagram, algorithm flow, or data construction workflow.
3. Experiments: performance plots, ablation plots, robustness/safety curves, distribution plots, comparison tables, or qualitative result panels.
4. Case study: representative examples, before/after comparisons, success/failure cases, error categories, or human-readable outputs.
5. Appendix: extra qualitative examples, extended ablations, additional case studies, dataset examples, or large tables.

Common expectation:

1. Intro and Method usually deserve corresponding figures when the paper contains a new task, system, benchmark, framework, pipeline, dataset construction process, or complex method.
2. The most important experimental result should usually keep a well-designed table, because tables best preserve exact numbers, baseline rankings, and metric-level comparison.
3. Experiments should not rely only on dense tables when a plot or visual comparison would make trends easier to read; plots should complement, not automatically replace, the main result table.
4. Case studies should appear when examples are important for reader trust, qualitative behavior, safety, failure analysis, or practical value.

## Main Result Table Priority

For main comparisons, prefer a polished academic table as the primary evidence artifact unless a plot is clearly more appropriate for the claim.

Main result tables should:

1. Include the strongest and most relevant baselines.
2. Show exact metric values with consistent precision and metric direction.
3. Clearly mark best and second-best results with restrained formatting.
4. Group datasets, tasks, settings, or model families in a reader-friendly way.
5. Use `booktabs`-style minimal rules and avoid clutter.
6. Have a caption that states the comparison setting and main takeaway.

Use plots as complementary visuals for trends, scaling behavior, robustness curves, ablation patterns, or qualitative interpretation.
Do not replace a necessary main result table with a decorative plot.

## Data-Faithful AI-Assisted Figure Creation

AI may help create beautiful academic-style figures, plots, diagrams, and case-study panels, but only from faithful inputs.

Rules:

1. Do not invent numbers, trends, examples, labels, baselines, datasets, or qualitative outputs.
2. Use real experiment data, logs, tables, screenshots, model outputs, or paper text as the source.
3. If data is missing, insert a red TODO at the figure callout, caption, and Visual Plan entry.
4. Keep source data or plotting scripts available when possible so the figure is reproducible.
5. Use clear academic styling: readable fonts, consistent color palette, restrained highlights, labeled axes, metric directions, units, and captions that state the message.
6. Avoid over-designed visuals that obscure data or make unsupported claims.

## Figure Generation Workflow

When the required data or content is available, actually generate figures using appropriate tools instead of only describing that a figure should exist.
Prefer reproducible scripts for data-driven figures.

Recommended workflow:

1. Identify the figure role: story, method, evidence, case study, or diagnostic.
2. Identify source data/content: CSV/JSON/logs/tables/screenshots/model outputs/paper text.
3. Choose the generation method:
   - Python plotting scripts for quantitative plots, analytical tables, ablations, distributions, robustness curves, and data-driven panels.
   - Diagram tools, vector editors, draw.io, Mermaid, TikZ, or manual vector design for pipeline/framework/method diagrams.
   - Image 2 or another approved image-generation service for non-data-analysis illustrative images, example/showcase visuals, conceptual scenes, or polished visual assets when faithful to the paper's intent.
   - Image editing or layout scripts for case-study panels using faithful screenshots, outputs, or examples.
4. Save generated figures under `figures/`.
5. Save plotting or generation scripts when possible, for example under `figures/scripts/` or an appropriate project script directory.
6. Insert the figure into LaTeX with a caption that states the takeaway.
7. If generation cannot be completed, add a red TODO with the missing data/tool/blocker.

Python-generated academic figures should use clean styling: consistent font sizes, readable legends, restrained colors, labeled axes, metric arrows when useful, and export formats suitable for LaTeX such as PDF, SVG, or high-resolution PNG.

## Tool Selection Policy

Choose the figure-generation tool by evidence type:

1. Data analysis, quantitative plots, numerical tables, ablations, robustness curves, distribution plots, and metric summaries: use Python or another reproducible computation/plotting workflow.
2. Main result tables and analytical tables: use structured data processing when possible, then export clean LaTeX tables.
3. Method, pipeline, framework, or workflow diagrams: use diagram/vector tools such as draw.io, TikZ, Mermaid, or carefully designed vector graphics.
4. Non-data-analysis illustrative figures, conceptual examples, visual showcases, or polished scene-style assets: use Image 2 when available.
5. Case studies that claim real model behavior, dataset examples, screenshots, or experimental outputs: use real artifacts; Image 2 may only help with layout/styling, not invent content.

Never use Image 2 to fabricate evidence, experimental outputs, datasets, screenshots, or case-study examples that the paper presents as real.
If an Image 2 figure is illustrative rather than empirical, make that role clear in the caption or surrounding text.

## Figure Roles

Each figure should have one primary role:

1. Story figure: helps readers understand the problem, gap, difficulty, or contribution in Introduction.
2. Method figure: explains pipeline, modules, inputs/outputs, data flow, or design logic.
3. Evidence figure: visualizes quantitative results, ablations, robustness, or comparison trends.
4. Case-study figure: shows representative examples, qualitative behavior, errors, or practical workflow.
5. Diagnostic figure: reveals phenomenon, failure mode, distribution, or dataset/task property.

Do not include a figure without a clear role.
If a visual does not support the paper story or evidence, remove it or move it to appendix.

## Captions and Text Integration

Every figure should be integrated into the paper text.

1. The paragraph introducing a figure should state the point before referencing the figure.
2. The caption should summarize the visual's message, not only describe components.
3. The figure should be referenced in the section where it supports a claim.
4. If a figure supports a major claim, include it in the claim-evidence map.
5. If a figure is planned but not ready, use the red TODO directive.

## Case Study Writing

Case studies should be curated to support specific claims.

For each case study, identify:

1. What question the case answers.
2. Why the example is representative, challenging, or informative.
3. What input/output, intermediate behavior, or failure mode should be shown.
4. What conclusion readers should draw.
5. Whether the case belongs in the main paper or appendix.

Do not present case studies as unstructured screenshots or raw examples.
Use concise panels, annotations, and takeaway captions.
