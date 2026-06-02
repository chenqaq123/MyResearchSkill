# Related Work Writing Guide

## Goal

Position your work against the most relevant lines of research, and make your novelty easy to verify.
Related Work should be organized by research direction or technical route, while also showing that the literature survey is sufficiently complete for the target venue.

## Workflow

1. List directly competing and recent baseline papers first.
2. Group literature by technical topic (not by publication year alone).
3. For each topic: summarize common paradigm, then key limitation relevant to your challenge.
4. End each topic by clarifying your distinction.
5. Check whether each topic has enough representative citations; if not, add a TODO to search more papers in that direction.
6. Align Related Work with the experimental baselines: every important baseline should be introduced, categorized, and connected to the evaluation rationale.

## Topic Design

Use 2-4 focused topics, for example:

1. Task-specific mainstream methods.
2. Methods closest to your core idea.
3. Auxiliary techniques your method builds on.

Each topic should correspond to a meaningful research direction, not a random citation cluster.
If a direction is important enough to mention, cite enough work to make the summary credible.

## Citation Coverage Budget

The exact number depends on venue, field, paper type, and page limit, but treat these as minimum planning targets before venue-specific adjustment:

1. Short/workshop paper: at least 15-25 total references, with at least 2-4 citations per major direction.
2. Standard conference paper: at least 25-45 total references, with at least 4-8 citations per major direction.
3. Benchmark, survey-like, dataset, or system paper with broad positioning: at least 40-70+ references when the paper needs broad positioning across tasks, datasets, evaluation protocols, and competing systems.

For each major direction, try to include:

1. 1-2 foundational or canonical papers when needed for context.
2. 2-4 recent representative papers from the last few years.
3. The strongest direct baselines or closest competing methods.
4. Any paper that reviewers are very likely to expect.

Do not pad citations for quantity.
Do not cite papers that were not actually checked for relevance.
If a direction has too few citations, do not present the Related Work as complete.
Mark the exact gap with a TODO such as `TODO: add 3-5 recent retrieval-augmented agent evaluation papers`, and include the missing direction in the search plan.

## Related Work Completeness Gate

Before producing a final Related Work draft, run this gate:

1. Count total references used in Related Work.
2. Count references per research direction.
3. Check whether each direction includes foundational papers when needed, recent representative work, direct competitors, and expected reviewer papers.
4. Check whether every important experimental baseline is introduced or contextualized.
5. Check whether any direction, baseline family, dataset/benchmark line, or method family is under-surveyed.

If the draft does not meet the citation coverage target:

1. Do not silently produce a polished but under-referenced Related Work.
2. Add visible TODOs in the affected paragraphs.
3. Add a `Related Work Coverage Report` after the draft with:
   - total citation count,
   - citations per direction,
   - missing directions or missing baselines,
   - exact search actions needed to reach the target.
4. If search access is available, search and add more relevant papers before finalizing.
5. If search access is unavailable, state the blocker and keep the TODOs visible.

## Baseline Alignment

Related Work and Experiments should explain each other.
If a method appears as an experimental baseline, Related Work should normally introduce it or its method family.
If a method family is emphasized in Related Work, Experiments should either include representative baselines from that family or explain why comparison is not applicable.

For each selected baseline, record:

1. Which research direction or technical route it represents.
2. Why it is a fair or necessary comparison.
3. Whether it is a direct competitor, strong recent method, standard classical baseline, ablation-style baseline, or practical system baseline.
4. What assumption, mechanism, or failure mode distinguishes it from the proposed method.
5. Where it appears in the Experiments section and which metric/table/figure evaluates it.

Do not introduce baselines only in tables without explaining their relevance.
Do not discuss strong competing methods in Related Work and then omit them from experiments without justification.
If a baseline is expected but not yet implemented or evaluated, mark it with a TODO at both the Related Work discussion and the experiment plan.

## Paragraph Template

1. Topic sentence: define scope of this topic.
2. Representative methods: one compact summary.
3. Limitation tied to your target technical challenge.
4. Baseline connection when relevant: identify which methods from this topic are used as experimental baselines.
5. Transition sentence that leads to your method.

## Do and Don't

1. Do compare mechanisms, assumptions, and failure modes.
2. Do emphasize the exact gap your method fills.
3. Do not make Related Work a citation dump.
4. Do not hide strongest baselines.
5. Do not leave a major direction under-cited.
6. Do not use citations only as decoration; every citation group should support a specific technical summary.
7. Do not leave experimental baselines unexplained in Related Work.
8. Do not omit an expected strong baseline without an explicit reason or TODO.

## Checklist

1. Are all strongest/recent competitors covered?
2. Is each topic connected to your problem setting?
3. Is your difference explained in technical terms, not marketing terms?
4. Is citation coverage complete for all core claims?
5. Does each major direction have enough foundational, recent, and directly competing references?
6. Are missing citations or under-surveyed directions marked with TODOs?
7. Does the reference count fit the venue, paper type, and page budget?
8. Is every important experimental baseline introduced or contextualized?
9. Does each Related Work direction map to experiments, baselines, or a justified positioning role?
10. Did the response include a Related Work Coverage Report when the coverage target was not met?
