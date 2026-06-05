# Personalization Profile

Use this file to store the user's preferred academic writing habits, recurring paper constraints, and project-specific review standards.

## Current Status

Personalization has started. Current user-specific rules cover target-venue confirmation, venue requirement compliance, page budget control, missing-evidence TODOs, the user's preferred Introduction story model, experiment taxonomy, reader-facing writing, recent reference-paper search and study, daily writing plans, proof-reading priorities, final LaTeX handoff organization, and PDF render QA.

## User-Specific Hard Rules

### Target Venue Confirmation

Before writing, rewriting, reviewing, or planning paper content, confirm the target venue/conference/workshop/journal.
Use the venue to calibrate writing style, contribution framing, evidence standard, paper length, reference-paper search, related-work coverage, and reviewer expectations.

If the target venue is missing, ask the user before major writing work.
For tiny local edits, proceed only with an explicit `target venue: unspecified` assumption and add a TODO when venue-specific calibration matters.

### Venue Requirement Compliance

After confirming the target venue, check official venue requirements when available and keep a compliance checklist.

The checklist should cover:

1. Page limit, appendix/supplement rules, and whether references count.
2. Official template, font size, margins, line spacing, and paper size.
3. Anonymous submission rules, acknowledgments, funding, and self-citation policy.
4. Required statements or sections such as limitations, ethics, broader impact, reproducibility, data/code availability, or checklists.
5. Figure/table/caption constraints and supplementary material rules.
6. Required submission artifacts such as PDF, source files, supplementary ZIP/PDF, code, videos, or metadata.
7. Citation style, bibliography style, and cross-reference requirements.
8. Track-specific, deadline-specific, camera-ready, rebuttal, or dual-submission rules.

Use official venue instructions or user-provided instructions as the source of truth.
If requirements cannot be verified, explicitly mark a TODO rather than relying on memory.

### Page Budget and Draft Length Control

Before generating a complete paper draft, confirm the intended page budget.
Do not default to 7 pages.

Use:

1. Official venue page limit when available.
2. User-specified target length for the current draft stage.
3. Paper maturity and available evidence to decide whether the draft should be a skeleton, rough complete draft, or near-submission draft.

If the user does not specify a target length:

1. Ask before producing a full paper draft.
2. For small section-level work, proceed with an explicit local scope assumption.
3. After PDF generation, compare actual pages with the target and revise or propose compression/expansion actions.

### Missing Evidence TODO Policy

The user may use this skill to draft early paper versions from a code repository before all experiments are finished.
In that case, the model must explicitly mark missing but necessary content instead of ignoring it or writing around it.

Required behavior:

1. If an experiment, number, baseline, ablation, implementation detail, citation, figure, table, qualitative example, or analysis is needed but unavailable, insert a TODO at the exact location.
2. Red TODO format is required whenever the output format supports it:
   - LaTeX: `\textcolor{red}{TODO: [specific missing content or future action]}`
   - Markdown: `<span style="color:red">TODO: [specific missing content or future action]</span>`
   - Plain text fallback: `TODO: [specific missing content or future action]`
3. TODOs must be specific action items, not vague placeholders.
4. Never invent missing results, citations, dataset names, baselines, or performance trends.
5. If the repository implies planned experiments but no concrete evidence exists, mark them as TODO rather than presenting them as completed.
6. At the end of the response, include a TODO summary list for all unresolved draft positions.

### Introduction Story Model

Prefer this Introduction structure when suitable:

1. Big background.
2. Small background.
3. Related work.
4. Research gap and technical difficulty.
5. What we propose.
6. Method overview: how the method solves the difficulty.
7. Experimental results and important theorem if available.
8. Contributions and impact: meaning, method, and experiments.

The gap must be paired with difficulty.
Do not only say prior work is missing something; explain why the missing capability is technically hard.

### Abstract Hard Contract

When writing abstracts, use a strict short-form structure.
This rule has priority over optional abstract templates.
Before writing, confirm the target venue's abstract word limit when available.

Default requirements:

1. 150-250 words unless the target venue gives a different official limit.
2. Exactly 5-6 sentences for a standard research-paper abstract, unless the venue format forces otherwise.
3. Sentence flow: Background -> Gap -> Insight -> Method -> Result -> Significance.
4. Insight and Method may be merged when needed.
5. Approximate IMRD information budget:
   - 25% introduction and importance,
   - 25% methods,
   - 35% results,
   - 15% discussion or significance.
6. The Result portion should contain the most concrete evidence and should not be skipped.
7. Do not use colon labels or colon-led pseudo-outlines in the final abstract, such as `Background:`, `Method:`, `Results:`, or `We make three contributions:`.
8. Avoid excessive enumeration, slash lists, semicolon inventories, and "first/second/third" contribution lists.
9. Do not write the abstract as a list of contributions.
10. Missing concrete results, evidence, or scope must be marked with red TODOs at the exact result or claim location.

### Core Claim Narrative

Before drafting a full paper or major section, identify the central claim in one sentence.
The paper should be written as a progressive argument for that claim, not as a flat report.

Requirements:

1. Each section should support, explain, test, or qualify the central claim.
2. Each paragraph should make its role in the claim-thread clear.
3. Experiments should map to claims, contributions, design choices, or risks.
4. Figures, tables, and case studies should make the claim easier to understand or verify.
5. Descriptive details that do not support the claim should be rewritten, moved to appendix, or removed.

Before finalizing, include a brief claim-thread check when working on full drafts or major rewrites.

### Compact Section Hierarchy

Avoid many unnecessary small sections.
The paper should read like a coherent argument, not a fragmented outline.

Rules:

1. Use standard major sections unless the venue or paper type requires otherwise.
2. Use only meaningful subsections, typically 2-4 inside a major section.
3. Do not create a heading for a single short paragraph.
4. Use paragraphs, bold takeaway sentences, figure/table captions, or appendix items for local points.
5. Merge adjacent small sections when they serve the same claim-thread role.
6. Use `\subsubsection` sparingly, mainly for long Method, Experiments, or Appendix navigation.
7. Keep LaTeX source files modular, but do not let source-file splitting create excessive visible headings.

### Experiment Taxonomy

Use three experiment roles when planning or auditing Experiments:

1. Validation experiments: phenomenon, discovery, or problem diagnosis.
2. Supporting experiments: performance indicators, safety/reliability when relevant, broad coverage, strong and convincing results tied to contribution.
3. Ablation experiments: hyperparameters, modules, and design choices that justify method innovation.

Supporting experiments should map to contributions.
Ablations should map to method innovations.
Missing experiment-role coverage should become TODOs.

### Experimental Analysis Style

When writing experimental analysis, each analysis point or paragraph should start with a concise bold conclusion sentence.
Then provide the table/figure evidence, numeric comparison, and interpretation.

Preferred pattern:

1. Bold takeaway first.
2. Evidence from table/figure.
3. Interpretation tied to claim, contribution, or design choice.
4. Boundary, exception, or TODO if evidence is incomplete.

Do not begin analysis paragraphs with raw numbers before giving readers the conclusion.

### Reader-Facing Writing

Write for readers, not only for authors:

1. Provide targeted background and preliminaries.
2. Explain complex content intuitively before dense technical detail.
3. Treat details such as figure legends, formulas, table readability, and font size as part of the paper's scientific communication.
4. Learn from the larger research group's prior work when relevant examples or standards are available.

### Visual-Rich Paper Preference

The paper should be visually rich when the content benefits from figures.
Figures should help communicate the story, method, evidence, and case studies, not merely decorate the draft.
Visual-rich writing means coordinated use of text, tables, and figures.

Default expectations:

1. Introduction often includes a teaser, motivation, task, failure, or contribution overview figure.
2. Method often includes a pipeline, framework, module interaction, algorithm flow, or construction workflow figure.
3. Experiments should preserve a polished main result table for exact baseline and metric comparison.
4. Plots should complement tables when data trends, ablations, robustness, safety, or qualitative behavior are easier to understand visually.
5. Case studies should be shown with curated panels, annotations, and takeaway captions when examples are important for reader trust.
6. Appendix can contain extra qualitative examples, extended visual analyses, large tables, and additional case studies.

Tri-modal presentation preference:

1. Text communicates the claim and reasoning.
2. Tables preserve exact values and comparisons.
3. Figures show trends, mechanisms, distributions, workflows, and case studies.

Main result table preference:

1. Keep the main comparison table unless a plot is clearly more appropriate for the core claim.
2. Beautify the table with clean grouping, consistent precision, metric arrows, restrained best/second-best highlighting, and a takeaway caption.
3. Use plots as complementary evidence, not as automatic replacements for important tables.

AI may create academic-style plots and figures from real experiment data or faithful paper content.
Never invent data, trends, examples, labels, baselines, datasets, or outputs.
If data or visual assets are missing, use red TODOs in the text, caption, and Visual Plan.
When source data exists, use Python, plotting scripts, diagram tools, or other appropriate generation workflows to actually create figure assets.
Save generated figures under `figures/` and keep scripts when possible.

Tool preference:

1. Use Python or another reproducible workflow for data analysis, analytical tables, quantitative plots, ablations, robustness curves, and distributions.
2. Use Image 2 for non-data-analysis illustrative figures, example/showcase visuals, conceptual scenes, or polished visual assets when available.
3. Use real screenshots, real outputs, or real dataset examples for case studies that are presented as evidence.
4. Do not use Image 2 to fabricate empirical results, dataset examples, screenshots, or model outputs.
5. If an Image 2 visual is illustrative rather than empirical, make that clear in the caption or text.

For full drafts and major rewrites, include a Visual Plan listing each planned figure, its section, source data/content, supported claim, status, and TODOs.

### Abstraction over Raw Enumeration

Avoid redundant writing that directly lists raw materials without synthesis.
When source material contains many files, scripts, metrics, datasets, examples, tasks, logs, papers, or implementation details, first infer the higher-level categories and then write those categories in natural academic prose.

Preferred behavior:

1. Group details by function, role, mechanism, evidence type, or reader-facing meaning.
2. Use concise abstractions instead of long inventories.
3. Keep only the examples needed to make the abstraction concrete.
4. Move detailed inventories to tables, appendices, artifact descriptions, or reproducibility sections.
5. Mention exact items only when they are scientifically important, necessary for reproducibility, or expected by reviewers.

The underlying principle is synthesis over enumeration.

### Appendix and Supplement Preference

Use appendix or supplementary material to support the main paper, not to hide the core contribution.
Before writing appendix content, check venue rules for page limits, anonymity, allowed supplementary files, and submission format.

Appendix is appropriate for:

1. Proofs, derivations, and extended theory.
2. Implementation details, hyperparameters, prompts, task schemas, and reproducibility instructions.
3. Additional ablations, robustness checks, sensitivity analyses, and extended comparison tables.
4. Dataset, benchmark, annotation, or construction details.
5. Extra qualitative examples, failure cases, case studies, and error analysis.
6. Extended related work tables, artifact inventories, or release documentation.

Rules:

1. Main paper keeps the core claim, method, and evidence.
2. Appendix sections should be referenced from the main text.
3. Appendix should be organized, titled, and navigable, not a dumping ground.
4. Missing appendix material should be marked with red TODOs.
5. If the venue disallows supplement, compress necessary material into the main paper or mark a venue-compliance TODO.

Draft review routing:

1. During initial draft review, actively identify content that should not remain in the main text but should still exist for completeness.
2. Move or propose moving that content into appendix/supplement.
3. Replace moved content with a concise summary and a main-text pointer.
4. Create appendix placeholders with red TODOs when the content should exist but has not been written.
5. Return an `Appendix Routing Report` listing moved content, retained main-text content, required pointers, and appendix TODOs.

### LaTeX Formatting Preference

When writing LaTeX section files, add `\noindent` to the first paragraph after each section heading, including `\section{...}`, `\subsection{...}`, and `\subsubsection{...}`.
Preserve venue template behavior if it explicitly controls indentation differently.
Check this preference during PDF QA.

### Related Work Coverage

Related Work should be organized by research direction or technical route, not by isolated papers.
Each major direction should have enough citations to show a real survey rather than a thin citation gesture.
Related Work should also align with the selected experimental baselines.

Default citation coverage before venue-specific adjustment should be treated as a minimum planning target, not a loose suggestion:

1. Short/workshop paper: at least 15-25 total references, usually at least 2-4 citations per major direction.
2. Standard conference paper: at least 25-45 total references, usually at least 4-8 citations per major direction.
3. Benchmark, dataset, system, or survey-like paper: at least 40-70+ references when broad positioning is needed.

For each important direction, include foundational papers when needed, recent representative papers, strongest baselines, and papers reviewers would expect.
Do not pad citations.
If a direction lacks enough references, mark a specific TODO to search and add more papers.

Completeness gate:

1. Before presenting Related Work as complete, count references by direction.
2. If the target is not met, add visible TODOs and a `Related Work Coverage Report`.
3. The report should list total citation count, citations per direction, missing directions/baselines, and concrete search actions.
4. If search access is available, search and add papers before finalizing instead of leaving the section thin.
5. If search access is unavailable, state the blocker and keep TODOs visible.

Baseline alignment preference:

1. Every important experimental baseline should be introduced or contextualized in Related Work.
2. Each baseline should map to a research direction or technical route.
3. Related Work should explain why the baseline is a fair or necessary comparison.
4. If an expected strong baseline is not evaluated, mark a TODO or justify the omission.
5. Experiments should not contain unexplained baseline names that never appear in the paper story.

### Reference-Paper Search and Study Habit

Before writing a new draft, substantially rewriting a major section, or planning a full paper, search for recent papers and save the selected references under a project-level `ref/` directory.

The reference set should cover three categories:

1. Recent best papers from the target conference or closely related top venues.
2. Recent papers with similar writing logic, narrative structure, or contribution type.
3. Recent papers closely related in content, task, benchmark, method, or experiment setup.

For each paper, create a compact note in `ref/` covering:

1. Citation metadata and source link/PDF path.
2. Why it was selected.
3. Story logic and Introduction flow.
4. Method organization and figure strategy.
5. Experiments organization, especially validation/supporting/ablation roles.
6. Caption, table, formula, and transition lessons worth emulating.

Use these papers to calibrate story structure, figure/table density, contribution framing, experiment organization, and reviewer expectations.
Do not copy wording.
For full-paper drafting or major section rewrites, do not skip this step silently.

Required behavior:

1. Search first when internet/search access is available.
2. If search is unavailable, inspect local `ref/`, `.bib`, related-work notes, or user-provided papers.
3. If no reference source is available, ask for papers/links/bibliography or mark the missing calibration as a red TODO.
4. Create `Reference Integration Notes` before the draft, listing selected papers by category and how they should shape Related Work, central-claim narrative, experiment design, baseline selection, and visual/table style.
5. Do not output a long standalone reference report unless requested; provide a compact integration summary and make the draft visibly reflect the references.
6. If PDFs cannot be downloaded, use metadata/abstracts only with a TODO for PDF-level reading.

### Writing Plan Preference

When the user asks for project-level writing help, propose and follow a daily writing plan.
The plan should divide work by concrete deliverables such as outline, Introduction, Method, experiments table draft, figures, Related Work, and proof-reading.

### Final LaTeX Handoff Organization

When writing a complete LaTeX paper draft, revising a full paper project, or preparing final delivery, organize the project into:

```text
main.tex
figures/
tables/
sections/
appendix/
```

Expected organization:

1. `main.tex` contains the main paper wrapper, preamble, macros, metadata, and `\input{sections/...}` calls.
2. `sections/` contains section-level `.tex` files.
3. `figures/` contains figure assets and figure source files.
4. `tables/` contains table `.tex` files or table source assets.
5. `appendix/` contains appendix or supplementary `.tex` files when allowed or required.

Preserve user content and update paths, labels, citations, and cross-references after moving files.
If venue templates require additional files, keep those files and adapt the structure without breaking compilation.

Section splitting is the default for actual LaTeX project output:

1. Put section bodies in separate files under `sections/`.
2. Keep `main.tex` as the wrapper with `\input{sections/...}` calls.
3. Do not keep a full completed paper as one monolithic `main.tex` unless the user explicitly asks or the venue template requires it.
4. If the response is only chat text and no files are edited, state that file splitting was not performed.

### PDF Render QA Preference

After generating a PDF, inspect the rendered output and revise the source before final delivery.

Required checks:

1. LaTeX compilation errors, warnings that affect output, unresolved citations, and unresolved references.
2. Page layout, awkward breaks, clipped content, overfull boxes, and orphan headings.
3. Figure readability, legends, placement, and path correctness.
4. Table readability, alignment, precision consistency, highlights, and margin overflow.
5. Equation layout, symbol definitions, and notation consistency.
6. Caption accuracy and cross-reference correctness.
7. Red TODO visibility and final TODO summary.

If PDF generation or inspection cannot be performed, say so explicitly and list the remaining QA TODOs.

### Proof-Reading Priorities

During proof-reading, check:

1. Subtitles, captions, and abstract.
2. Figure/table data and whether the visual meaning matches the intended claim.
3. Formula symbols and notation consistency.
4. Citations and cross-references.
5. Typos and formatting details.

### Reviewer Lens

Remember that reviewers can most directly evaluate completeness and novelty of idea.
The writing should make both visible quickly.

## Preference Categories

1. Target fields and venues.
2. Preferred paper story patterns.
3. Preferred writing style and tone.
4. Common weaknesses to check aggressively.
5. Figure, table, and caption preferences.
6. Claim-evidence standards.
7. Revision workflow preferences.

## How to Apply

1. Load this file only when the user asks for personalized refinement or when using this refined skill.
2. Treat these preferences as user-specific defaults, but do not override explicit instructions in the current task.
3. If a preference conflicts with paper evidence, venue rules, or technical correctness, explain the conflict and choose the more faithful paper-specific choice.
