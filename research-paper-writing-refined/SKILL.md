---
name: research-paper-writing-refined
description: Improve academic paper writing quality for ML/CV/NLP-style papers with clear section structure, paragraph flow, and reviewer-facing presentation. Use when drafting or revising Abstract, Introduction, Related Work, Method, Experiments, or Conclusion; polishing figures/tables; checking claim-support alignment; performing self-review before submission; or applying personalized academic writing preferences. 中文触发词：论文写作、摘要、引言、方法、实验、相关工作、审稿人视角、自审、claim-evidence 对齐、个性化写作偏好。
---
# Research Paper Writing

## Overview

Use this skill to rewrite a research paper into a reviewer-friendly, high-clarity draft.
Prioritize first-impression quality (figures/tables/layout), logical flow, and evidence-backed claims.

## Core Workflow

1. Confirm the target venue/conference before writing or rewriting any paper section.
2. Clarify the paper story before sentence-level edits.
3. Check target venue requirements and keep a venue compliance checklist.
4. Confirm the page budget and target draft length before generating a full paper draft.
5. For new drafts, major rewrites, or project-level writing, search for recent reference papers and save notes/PDFs/metadata under `ref/` before drafting.
6. Use section-specific guidance in `references/`.
7. Rewrite paragraph-by-paragraph with one message per paragraph.
8. Run reverse outlining after writing each section.
9. Check every major claim in Abstract/Introduction against experimental evidence.
10. For project-level writing, maintain a concrete daily writing plan with deliverables.
11. Plan and create paper figures, plots, and case-study visuals as first-class parts of the paper.
12. Run final-paper adversarial review with `references/paper-review.md`.
13. During draft review, move or plan appendix-worthy material out of the main text and into appendix/supplement files.
14. For completed LaTeX paper handoff, reorganize the project into the required delivery structure.
15. Compile the PDF, inspect the rendered output, and revise layout/content issues before final delivery.

## Target Venue Confirmation (Required)

Before drafting, rewriting, reviewing, or planning paper content, identify the target venue/conference/workshop/journal.
Use the target venue to calibrate contribution framing, evidence standard, paper length, reference-paper search, visual density, related-work coverage, and reviewer expectations.

If the user has not provided a target venue, ask for it before major writing work.
For small local edits where asking would interrupt the task, proceed with a clearly stated assumption such as `target venue: unspecified`, and add a TODO if venue-specific calibration is needed.

## Venue Requirement Compliance

After confirming the target venue, check the venue's official author instructions, CFP, template, and submission checklist when available.
Use official venue pages, official proceedings/template repositories, or the user's provided instructions as the source of truth.

Maintain a venue compliance checklist covering:

1. Page limit, appendix/supplement limits, and whether references count toward the limit.
2. Required LaTeX/Word template, font size, margins, line spacing, and paper size.
3. Anonymous submission rules, author block removal, acknowledgments, funding statements, and self-citation policy.
4. Required sections or statements such as limitations, ethics, broader impact, reproducibility, data/code availability, checklist, or responsible AI statement.
5. Figure/table/caption constraints, color accessibility expectations, and supplementary material rules.
6. Submission artifacts such as PDF, source files, supplementary PDF/ZIP, code, videos, rebuttal material, or OpenReview metadata.
7. Citation/bibliography style, checklist formatting, and cross-reference requirements.
8. Deadline-sensitive or track-specific rules such as short/long paper type, workshop format, camera-ready changes, or dual-submission policy.

If venue requirements cannot be verified, state that clearly and insert a TODO to verify official requirements.
Do not invent venue rules from memory when current official instructions are needed.
Before final handoff, re-check the draft against the compliance checklist and summarize any unresolved violations or TODOs.

## Page Budget and Draft Length Control

Before generating a complete paper draft, confirm both:

1. The venue page limit from the official requirements when available.
2. The user's intended draft length for the current stage.

Do not default to a 7-page draft.
Draft length should be a deliberate choice based on venue constraints, paper maturity, amount of available evidence, and the user's current goal.

Recommended defaults only when the user does not specify a length:

1. Early skeleton draft: concise structure-first draft, usually 3-5 pages of content.
2. Complete but still rough conference draft: target 70-85% of the main-paper page limit, leaving room for figures, tables, references if counted, and later edits.
3. Near-submission draft: target the venue limit minus safety margin, with explicit compression passes if over budget.

If the venue limit or desired length is unknown, ask before producing a full draft.
For small section-level work, state the assumed scope instead of asking for a page count.
After PDF generation, compare the actual page count with the target and revise or propose compression/expansion actions if needed.

## Global Principles

1. Keep one paragraph for one message only.
2. State the paragraph message in the first sentence.
3. Make nouns self-contained; define new terms before reusing them.
4. Maintain sentence-to-sentence flow (cause, contrast, consequence, or refinement).
5. Iterate with adversarial self-review: read as a skeptical reviewer.
6. Treat visual quality as core content, not decoration.
7. Use a clean teaser and pipeline figure.
8. Use readable, minimal-ink tables.
9. Keep formatting consistent and tidy.
10. Write for readers: provide targeted background, intuitive explanations for complex content, and inspectable details in figures, formulas, and tables.
11. Keep recent reference papers nearby when calibrating narrative structure, figure/table density, contribution framing, and experiment organization.
12. Make the paper's completeness and idea novelty easy for reviewers to evaluate.
13. Avoid raw-enumeration prose: do not dump unprocessed details into the paper when a higher-level abstraction, grouping, or synthesis is needed.
14. Make the paper visually rich when useful: coordinate text, tables, and figures to explain the story, method, evidence, and practical behavior.

## Section Hierarchy Discipline

Use a compact, reader-friendly section hierarchy.
Do not create many small, unnecessary sections just because the source material contains many ideas, modules, experiments, files, or TODOs.
Most ideas should be handled as paragraphs, figure/table captions, or appendix items rather than new headings.

Default structure:

1. Use the standard major sections unless the venue or paper type requires otherwise: Abstract, Introduction, Related Work, Method, Experiments, Conclusion, and optional Appendix.
2. Within a major section, use only a small number of meaningful subsections, typically 2-4.
3. Avoid `\subsubsection` unless it is necessary for navigation in a long Method, Experiments, or Appendix.
4. Do not create a heading for a single short paragraph.
5. Do not create parallel headings that repeat the same rhetorical function, such as many tiny sections for individual observations, minor components, or small experiment notes.

Promotion test:

1. Promote content to a section/subsection only if it introduces a distinct reader question, method module, experiment block, or contribution-level idea.
2. Keep content as a paragraph if it is an explanation, transition, example, limitation, or local analysis point.
3. Move content to appendix if it is detailed but not central to the main claim.
4. Merge adjacent small sections when they serve the same claim-thread role.

Important distinction:

1. File organization may split LaTeX source into `sections/*.tex`.
2. This does not mean the paper should contain many visible headings.
3. Source-file modularity and reader-facing section hierarchy are separate concerns.

## Core Claim Narrative Policy

Before drafting a full paper, major section, or review response, identify the paper's central claim in one sentence.
Write the paper to progressively prove that claim, not as a flat report of background, components, experiments, and results.

Core rule:

1. Every major section should have a role in supporting the central claim.
2. Every subsection should answer a reader question created by the previous part of the story.
3. Every experiment should map to a claim, contribution, design choice, or risk.
4. Every figure/table/case study should make one part of the central claim easier to understand or verify.
5. If a paragraph is merely descriptive, revise it to state why the detail matters for the claim.

Avoid flat narrative patterns such as:

1. Listing components without explaining the problem each component solves.
2. Listing experiments without explaining which claim each one verifies.
3. Listing related work without building toward the gap and difficulty.
4. Listing implementation details without connecting them to method behavior or reproducibility.

Before finalizing, run a claim-thread check:

1. Central claim: one sentence.
2. Section role map: `Section -> how it supports the claim`.
3. Evidence map: `Claim/contribution -> experiment/table/figure/case study`.
4. Remove, move to appendix, or rewrite content that does not support the claim or reader understanding.

## Abstraction over Raw Enumeration

When drafting from notes, code, repositories, experiments, logs, examples, interviews, paper lists, or other raw materials, first infer the conceptual categories and then write those categories in natural academic prose.
The paper should communicate the role, mechanism, and significance of the material rather than merely listing its surface forms.

Core rule:

1. Do not copy raw inventories directly into the main text.
2. Group details by function, role, mechanism, evidence type, or reader-facing meaning.
3. Replace long lists with concise abstractions when the individual items are not themselves the point.
4. Mention exact items only when they are scientifically important, necessary for reproducibility, or expected by reviewers.
5. Move detailed inventories to tables, appendices, artifact descriptions, or implementation details when needed.

Examples of the intended transformation:

1. File-type inventory -> artifact roles, such as natural-language resources, executable components, and configuration metadata.
2. Long metric list -> evaluation dimensions, such as effectiveness, robustness, efficiency, and safety.
3. Many dataset/task examples -> task families, difficulty axes, or coverage dimensions.
4. Many implementation details -> pipeline stages, system modules, or reproducibility components.
5. Many related papers -> research directions or technical routes.

Before finalizing a paragraph, check whether it reads like a raw list.
If so, rewrite it into a synthesized statement plus only the most necessary examples.

## Appendix and Supplement Policy

Use appendix or supplementary material to support the main paper, not to hide essential reasoning that reviewers need for the core contribution.
Before writing appendix content, check the target venue's appendix/supplement rules, page limits, anonymity rules, and submission format.

Appropriate appendix/supplement content:

1. Detailed proofs, derivations, or theoretical extensions.
2. Extra implementation details, hyperparameters, prompts, task schemas, or reproducibility instructions.
3. Additional ablations, sensitivity analyses, robustness checks, and extended comparison tables.
4. Dataset, benchmark, or annotation details that are too long for the main paper.
5. Extra qualitative examples, failure cases, case studies, or error analysis.
6. Extended related work tables, artifact inventories, or release documentation.
7. Ethics, limitations, broader impact, data/model cards, or checklist material when the venue expects them outside the main text.

Appendix writing rules:

1. The main paper must contain the core claim, core method, and core evidence; the appendix can deepen or support them.
2. Every appendix section should be referenced from the main text when it supports a main-text claim.
3. Do not use appendix as a dumping ground for raw logs, unorganized file lists, or unfiltered examples.
4. Keep appendix sections titled, numbered, and easy to navigate.
5. If an appendix item is required but not yet written, mark the main-text pointer and appendix placeholder with a red TODO.
6. If the venue does not allow supplementary material, compress the necessary content into the main paper or mark a venue-compliance TODO.

Draft review appendix-routing rule:

1. When reviewing an initial draft, actively identify material that is too detailed for the main text but still useful for completeness, reproducibility, or reviewer confidence.
2. Move such material to appendix/supplement when editing files, or explicitly propose the move when only reviewing text.
3. Typical material to route to appendix includes long proofs, extended derivations, detailed hyperparameters, prompt/task schemas, extra ablations, extended comparison tables, dataset construction details, annotation guidelines, long qualitative examples, failure cases, error analysis, extended related-work tables, artifact inventories, and reproducibility instructions.
4. Replace moved main-text material with a concise summary and a pointer such as `See Appendix~\ref{app:...} for details.`
5. If appendix content should exist but has not been written, create an appendix placeholder with a red TODO rather than leaving the main text overloaded or silently dropping the material.
6. During draft review, include an `Appendix Routing Report` listing what stayed in the main text, what moved to appendix, and what appendix TODOs remain.

## LaTeX Formatting Preferences

When writing or editing LaTeX section files:

1. Add `\noindent` to the first paragraph after each section heading, including `\section{...}`, `\subsection{...}`, and `\subsubsection{...}`.
2. Preserve venue template behavior if it explicitly controls paragraph indentation differently.
3. During final PDF QA, check that first paragraphs after section headings follow this preference unless the venue template requires otherwise.

## Reference Paper Search and Study Policy

After confirming the target venue and checking venue requirements, and before writing a new draft, substantially rewriting Introduction/Method/Experiments, or planning a full paper, search for recent papers in three categories and place the collected material under a project-level `ref/` directory:

1. Recent best papers from the target venue or closely related top venues.
2. Recent papers with similar writing logic, story structure, or contribution type.
3. Recent papers closely related in content, task, benchmark, method, or experiment setup.

For each selected paper, create a short note in `ref/` recording:

1. Citation metadata and link/PDF path.
2. Why this paper was selected.
3. Its paper story arc: background -> gap/difficulty -> proposal -> evidence -> contribution/impact.
4. Its Introduction structure.
5. Its Method organization and figure strategy.
6. Its Experiments organization, including validation/supporting/ablation roles.
7. Useful style lessons for captions, tables, formulas, and section transitions.

Use the reference set to learn writing style, story logic, evidence organization, and presentation standards.
Do not copy wording, claims, diagrams, or unsupported framing.

For full-paper drafting or major section rewrites, this step is mandatory:

1. Do not proceed directly to a full draft without either completing the reference-paper search or explicitly reporting why it cannot be completed.
2. If internet/search access is available, perform the search before drafting and save notes, links, metadata, and downloaded PDFs when possible under `ref/`.
3. If internet/search access is unavailable, inspect any user-provided bibliography, local `ref/` directory, existing `.bib` files, or related-work notes before drafting.
4. If no reference source is available, ask the user for permission, papers, links, or a bibliography; if the user still wants a draft, mark the missing reference calibration with a red TODO.
5. Create `Reference Integration Notes` before drafting: selected papers by category plus how they will shape Related Work organization, central-claim narrative, experiment design, baseline selection, and visual/table style.
6. Do not dump a long standalone reference report into the user-facing answer unless the user asks for it; provide a compact integration summary and let the draft reflect the references.

If PDF retrieval is unavailable but metadata/search results are available, proceed with metadata and abstracts while marking PDF-level reading as TODO.

## Missing Evidence and TODO Policy (Hard Constraint)

When drafting from an incomplete paper, code repository, or partial experiment record, never hide missing information behind vague wording.
If required experiments, numbers, implementation details, citations, baselines, ablations, qualitative examples, figure assets, or analysis are not yet available, mark the exact location explicitly with a red TODO.

Use this TODO directive:

1. In LaTeX drafts: `\textcolor{red}{TODO: [specific missing content or future action]}`
2. In Markdown drafts: `<span style="color:red">TODO: [specific missing content or future action]</span>`
3. In plain text drafts: `TODO: [specific missing content or future action]`

TODO placement rules:

1. Put TODO directly in the sentence, paragraph, table caption, figure caption, or claim-evidence map where the missing content is needed.
2. Make each TODO specific enough to become an action item, for example `TODO: add main comparison results on Dataset X` rather than `TODO: results`.
3. Do not invent placeholder numbers, baselines, citations, dataset names, or performance trends.
4. Do not selectively omit necessary but missing experiments; include the claim only if it is weakened appropriately and tagged with TODO, or remove the claim and list the missing evidence.
5. If a code repository suggests an intended experiment but no result file/log/table exists, mark it as TODO instead of presenting it as completed.
6. Before finalizing any draft, scan the text once for unsupported claims and missing concrete content, then add TODO markers wherever needed.

## Final LaTeX Handoff Structure

When writing a complete LaTeX paper draft, revising a full paper project, or preparing final delivery, organize or reorganize the paper project into this structure:

```text
main.tex
figures/
tables/
sections/
appendix/
```

Use this structure as the default final handoff format:

1. `main.tex`: paper preamble, package imports, title/authors if available, global macros, and `\input{sections/...}` calls.
2. `sections/`: section-level `.tex` files such as `abstract.tex`, `introduction.tex`, `related_work.tex`, `method.tex`, `experiments.tex`, and `conclusion.tex`.
3. `figures/`: all figure assets and figure source files when available.
4. `tables/`: table `.tex` files or table source assets.
5. `appendix/`: appendix or supplementary `.tex` files when the venue allows or requires them.

During reorganization:

1. Preserve existing user content and do not delete original files unless the user explicitly asks.
2. Update figure, table, and section paths in `main.tex` and section files.
3. Keep labels, citations, cross-references, and macros consistent after moving files.
4. If a required asset is missing, insert the red TODO directive at the use site and include it in the TODO summary.
5. If the current project already follows a venue template with a stricter structure, preserve the venue-required files and adapt the handoff structure without breaking compilation.

Section splitting rules:

1. If the task produces or edits an actual LaTeX project, write section content into separate files under `sections/` by default.
2. Do not leave a completed full-paper draft as one monolithic `main.tex` unless the user explicitly asks or the venue template requires it.
3. `main.tex` should orchestrate the paper with `\input{sections/...}` rather than containing all section bodies inline.
4. If appendix content exists, keep it in `appendix/` files and connect it from `main.tex` according to the venue template.
5. If the user only asks for text in chat rather than file edits, present the draft under clear section headings and state that file splitting has not been performed.

## PDF Render and QA Loop

After generating a PDF for a paper draft or final handoff, inspect the rendered PDF and revise the source until the output is clean enough to deliver.

Check at least:

1. Compilation status: no fatal LaTeX errors, missing files, undefined citations, or unresolved references.
2. Page layout: no overfull boxes that visibly damage layout, no awkward page breaks, no orphan headings, and no clipped content.
3. Figures: correct paths, readable size, non-blurry rendering, complete legends, and correct placement relative to the text.
4. Tables: readable font size, aligned columns, consistent precision, visible highlights, and no overflow beyond margins.
5. Equations: defined symbols, readable alignment, no broken line wraps, and consistent notation.
6. Captions and cross-references: captions match the visual content, and all `\ref`, `\autoref`, `\cref`, and citations point to the intended objects.
7. LaTeX formatting preferences: first paragraphs after `\section`, `\subsection`, and `\subsubsection` headings use `\noindent` unless the venue template overrides indentation.
8. TODOs: unresolved TODOs remain visibly marked in red and are summarized for the user.

When issues are found, edit the source files, recompile, and recheck the PDF.
Do not claim the paper is ready for final handoff until the rendered PDF has been inspected.
If PDF compilation or visual inspection cannot be performed in the environment, state that explicitly and provide a TODO checklist of the checks that remain.

## Paragraph Clarity Check (Important)

Use this quick test whenever the user asks whether a paragraph "flows" or is clear.

1. Read as an external reader:
   - Does this paragraph have one explicit message?
   - Does the first sentence state what this paragraph will do?
   - Are all key nouns/terms readable without hidden context?
   - Does each sentence connect to the previous one with a clear relation (cause, contrast, consequence, refinement, example)?
2. Run reverse outlining for the current section:
   - Write down thesis/main claim.
   - Write down each paragraph topic sentence.
   - Write down the evidence/explanation points under each paragraph.
   - Check mapping: topic sentence -> thesis, and evidence -> topic sentence.
   - Revise or remove any paragraph that cannot be mapped cleanly.
3. If flow is still weak, add temporary section headers and explicit transition phrases during revision, then remove unnecessary headers before finalizing.

## Section Fragmentation Check

Before finalizing a full draft, scan visible headings and merge unnecessary small sections.
If a heading does not help readers navigate the central claim, remove it and convert the content into a paragraph, caption, table note, or appendix item.

Source reference for this check:

- `references/does-my-writing-flow-source.md`

## Section Guides

Load only the needed section file:

- Introduction: `references/introduction.md`
- Abstract: `references/abstract.md`
- Related Work: `references/related-work.md`
- Method: `references/method.md`
- Experiments: `references/experiments.md`
- Conclusion: `references/conclusion.md`
- Visuals, figures, and case studies: `references/visuals.md`
- Paper review (Paper Rview): `references/paper-review.md`
- Paragraph clarity source: `references/does-my-writing-flow-source.md`
- Personalization profile: `references/personalization.md`
- Example bank index: `references/examples/index.md`

## Paper Review Core Points

Use `references/paper-review.md` for the full checklist and workflow.

1. Add an end-of-draft self-review question list in five dimensions:
   - contribution,
   - writing clarity,
   - experimental strength,
   - evaluation completeness,
   - method design soundness.
2. Treat claim-evidence alignment as a hard constraint, especially for Abstract and Introduction.
3. Perform adversarial writing: review as a skeptical reviewer and resolve every high-risk question.
4. Revise until major rejection risks are explicitly addressed.

## Execution Rules

1. Confirm or record the target venue before drafting prose.
2. Check or TODO the target venue's official requirements before major writing or final delivery.
3. Confirm page budget and intended draft length before producing a complete paper draft; never assume 7 pages by default.
4. Build a mini-outline before drafting prose.
5. Keep the visible section hierarchy compact; avoid unnecessary small sections and merge fragmented headings.
6. For each subsection, explicitly include motivation, design, and technical advantage when applicable.
7. Avoid writing style that looks like incremental patching of a naive baseline.
8. Keep terminology stable across the full paper.
9. If a claim cannot be supported by results, weaken or remove the claim.
10. Before finalizing, append and answer a five-dimension self-review question list, then revise the paper based on unresolved items.
11. Do not load all section references (Introduction/Abstract/Related Work/Method/Experiments/Conclusion) at once; load only the specific section guide needed for the current edit target.
12. When information is missing but needed for a credible draft, insert the TODO directive from the hard constraint above instead of smoothing over the gap.
13. When the task scope requires reference-paper calibration, perform the reference search/study step first and use Reference Integration Notes to guide Related Work, narrative, experiments, baselines, and visuals; if it cannot be completed, stop to report the blocker or mark a visible TODO before drafting.
14. For full drafts or major rewrites, create a Visual Plan covering intro, method, experiments, and case-study figures before finalizing.
15. During initial draft review, route appendix-worthy material out of the main text, create appendix placeholders/files when appropriate, and include an Appendix Routing Report.
16. When producing or editing a complete LaTeX paper project, split section bodies into `sections/` files and keep `main.tex` as the wrapper.
17. After PDF generation, inspect the rendered PDF and revise source files until layout, references, figures, tables, equations, TODO visibility, and page count are acceptable.

## Output Contract

When asked to rewrite or draft sections, return:

1. A compact section outline (3-7 bullets).
2. Revised paragraphs with explicit paragraph roles (opening/challenge/method/advantage/evidence/limitation).
3. A short self-review checklist covering clarity, flow, terminology consistency, unsupported claims, and missing evidence.
4. A claim-evidence map for each major claim in the revised text using `Claim: ... | Evidence: ... | Status: supported/needs evidence/TODO`.
5. A TODO list summarizing every red TODO inserted in the draft and the concrete future action needed to resolve it.

For full-paper drafting, major rewrites, or project-level writing, additionally return:

1. A central claim and claim-thread map.
2. A compact Reference Integration Summary covering the three required paper categories and how they shaped Related Work, narrative, experiments, baselines, and visuals.
3. A compact section hierarchy plan explaining major sections and only necessary subsections.
4. A venue compliance summary.
5. The confirmed page budget and target draft length.
6. An Appendix Routing Report when reviewing or restructuring a draft.
7. A Visual Plan listing required intro/method/experiment/case-study figures, their data sources, current status, and TODOs.
