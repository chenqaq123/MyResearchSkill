# Paper Review (Paper Rview)

## Goal

Use an adversarial, reviewer-style checklist to detect reject risks early and revise the paper before submission.

## Core Principle

Pursue perfectionism in paper quality: assume reviewers will probe every weak point and proactively fix them.
Write for readers and reviewers: make the background targeted, the hard idea intuitive, and the visual/formal details easy to inspect.
The paper should be organized around a central claim, not written as a flat inventory of sections, components, and experiments.

## Reviewer Evaluation Lens

Assume reviewers can most directly evaluate two high-level dimensions:

1. Completeness: whether the paper has enough method detail, experiments, ablations, figures, tables, citations, and polished presentation to support its claims.
2. Novelty of idea: whether the task, insight, method, benchmark, finding, or theory gives readers genuinely new knowledge.

Every self-review should ask whether the current draft makes both dimensions easy to see.

## Critical Rule (Do Not Violate)

Every major claim, especially in Abstract and Introduction, must be:

1. technically correct, and
2. explicitly supported by experimental evidence.

If a claim is not supported, either add evidence or weaken/remove the claim.

## What Usually Gets a Paper Accepted

1. Sufficient contribution (for example: novel task, novel pipeline, novel module, novel design choices, new experimental findings, or new insight).
2. Better empirical performance than prior methods under fair comparisons.
3. Sufficient comparison experiments and ablation studies.
4. A complete, reader-facing presentation whose figures, captions, formulas, and references reduce reviewer effort.

## Common Rejection Dimensions

| Rejection Dimension          | Typical Failure Signals                                                                                                                                                                                                                                                                    |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1. Insufficient contribution | 1.1 Targeted failure cases are too common.<br /> 1.2 Proposed technique is already well explored; expected gains are predictable/well-known.                                                                                                                                               |
| 2. Unclear writing           | 2.1 Missing technical details; work is not reproducible.<br />2.2 A method module lacks clear motivation.                                                                                                                                                                                  |
| 3. Weak empirical effect     | 3.1 Improvement over prior methods is only marginal.<br /> 3.2 Even if better than previous methods, absolute performance is still not strong enough.                                                                                                                                      |
| 4. Incomplete evaluation     | 4.1 Missing ablation studies.<br />4.2 Missing important baselines or important evaluation metrics.<br /> 4.3 Datasets are too simple to prove the method truly works.                                                                                                                    |
| 5. Problematic method design | 5.1 Experimental setting is unrealistic.<br />5.2 Method has technical flaws and appears unreasonable.<br />5.3 Method is not robust and needs per-scenario hyperparameter tuning. <br /> 5.4 New design introduces stronger limitations than its benefits, leading to negative net value. |

## End-of-Paper Self-Review Question List

Add this checklist near the end of the draft while revising.
Use each question to trigger concrete edits before submission.

### 0. Central Claim and Narrative

1. Can the central claim be stated in one sentence?
2. Does each section have a clear role in proving, explaining, or qualifying that claim?
3. Do experiments, figures, tables, and case studies map to specific claims or risks?
4. Is any part of the paper merely descriptive or flat without explaining why it matters?
5. Should any descriptive detail be moved to appendix, compressed, or removed?
6. Is the visible section hierarchy compact, or has the paper been fragmented into unnecessary small sections?

### 1. Contribution

1. What new knowledge does this paper give to readers?
2. Are we solving a truly meaningful failure case, not a trivial/common one?
3. Is the technical idea genuinely non-obvious beyond well-explored practice?
4. Is our gain surprising or insightful rather than a predictable improvement?
5. Is there at least one clear novelty type (task/pipeline/module/design finding/insight)?
6. Can a reviewer quickly identify both the paper's completeness and its novelty?

### 2. Writing Clarity

1. Can a knowledgeable reader reproduce the method from the paper?
2. Did we provide enough technical detail for each key module?
3. Is the motivation of every module explicit and logically connected to a challenge?
4. Are terms and notation consistent across sections?
5. Does each paragraph carry one clear message with smooth transitions?
6. Are background and preliminaries targeted to the actual reader difficulty?
7. Are complex ideas first explained intuitively before dense notation or implementation detail?
8. Does the paper use figures where they would materially improve reader understanding of the task, method, evidence, or case studies?

### 3. Experimental Strength

1. Are improvements over strong baselines meaningful, not just statistically tiny?
2. Is absolute performance competitive enough for the target venue?
3. Are gains consistent across multiple datasets/settings/metrics?
4. Do we report both strengths and failure cases honestly?
5. Does each experimental analysis paragraph begin with a clear takeaway before presenting numbers?
6. Are experiment plots and case-study visuals faithful to real data and integrated with the analysis?

### 4. Evaluation Completeness

1. Do we include ablations for all key design choices?
2. Are all strong/recent baselines included under fair settings?
3. Are evaluation metrics standard and sufficient for this task?
4. Are datasets/scenarios challenging enough to validate real effectiveness?
5. Are comparison and ablation protocols clearly documented?
6. Are validation, supporting, and ablation experiments all represented when the contribution requires them?
7. Are extended experiments, additional tables, failure cases, or implementation details placed in appendix/supplement when they are useful but too detailed for the main paper?

### 5. Method Design Soundness

1. Is the experimental setting realistic for practical use?
2. Does the method have hidden technical defects or unreasonable assumptions?
3. Is the method robust without heavy per-case hyperparameter retuning?
4. Do benefits outweigh added complexity and new limitations?
5. Could reviewers reasonably argue that the net benefit is negative?

## Adversarial Writing Workflow

1. Read the paper as a skeptical reviewer.
2. Answer every question above with explicit evidence from the paper.
3. Mark each item as `pass`, `needs revision`, or `needs new experiment`.
4. Revise claims, writing, experiments, or method scope accordingly.
5. Route appendix-worthy material out of the main text while preserving needed support in appendix/supplement.
6. Repeat until no major rejection risk remains.

## Appendix Routing During Draft Review

When reviewing an initial draft, check whether the main text contains material that is useful but too detailed for the main paper.
Move or recommend moving that material to appendix/supplement, then replace it with a concise main-text summary and pointer.

Route to appendix when appropriate:

1. Long proofs, derivations, or theorem details.
2. Detailed hyperparameters, prompts, schemas, implementation settings, or reproducibility instructions.
3. Extra ablations, sensitivity analyses, robustness checks, extended comparison tables, or additional metrics.
4. Dataset construction details, annotation guidelines, examples, or benchmark records.
5. Extended qualitative examples, failure cases, case studies, or error analysis.
6. Extended related-work tables, artifact inventories, or long lists that support but distract from the main narrative.

Return an `Appendix Routing Report` with:

1. Main-text content that should stay.
2. Content moved or recommended for appendix.
3. Required main-text pointers to appendix.
4. Appendix TODOs that remain.

## Proof-Reading Checklist

Before submission or any serious draft handoff, check:

1. Subtitles, captions, and abstract: each should communicate the paper story without requiring the full text.
2. Figures and tables: verify both numeric correctness and intended meaning.
3. Formula symbols: ensure every symbol is defined, reused consistently, and not overloaded accidentally.
4. Citations and cross-references: check missing citations, wrong `\cite`, wrong `\ref`, stale figure/table numbers, and broken references.
5. Typos and formatting: scan spelling, punctuation, font size, figure legends, table readability, and layout consistency.
6. TODO markers: resolve them or keep them visibly marked if the draft is intentionally incomplete.
7. Appendix/supplement: verify appendix pointers, numbering, venue compliance, anonymity, and whether every appendix section supports a main-text claim.
8. Visual plan: verify intro/method/experiment/case-study visuals, data sources, captions, and TODOs for missing figures.
9. Section hierarchy: merge small unnecessary headings and keep visible sections aligned with the claim-thread.
