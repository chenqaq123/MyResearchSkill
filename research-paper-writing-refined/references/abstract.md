# Abstract Writing Guide

## Goal

Write a strong abstract by doing three things repeatedly:

1. Think through the abstract logic first.
2. Follow one template (Version 1/2/3 below).
3. Revise the abstract many times.

## Hard Abstract Contract

This contract has priority over the three optional templates below.
Because abstracts are short, write with high precision, concrete detail, and no filler.

Before writing an abstract, confirm the target venue's official abstract word limit when available.
If no venue limit is known, use 150-250 words.
If the venue limit conflicts with any rule below, obey the venue limit first and state the adjustment.

For a standard research-paper abstract, write exactly 5-6 sentences unless the venue format forces otherwise.
Organize the sentences in this order:

1. Background: the task, setting, or broader context.
2. Gap: the limitation, missing capability, or technical difficulty.
3. Insight: the key idea that makes the work non-obvious.
4. Method: what the paper proposes or does.
5. Result: what the paper finds, preferably with concrete evidence.
6. Significance: what the result means or why it matters.

The Insight and Method roles may be merged into one sentence when the abstract needs to be shorter.
Do not skip the Result role; if concrete numbers or evidence are missing, insert a red TODO at the result location instead of hiding the absence.

Use an IMRD-style information budget:

1. Introduction and importance: about 25% of the abstract.
2. Methods: about 25% of the abstract.
3. Results: about 35% of the abstract.
4. Discussion, implication, or significance: about 15% of the abstract.

The Result portion should receive the largest share of concrete evidence.
Do not spend so much space on background or method detail that the findings become vague.

Hard style rules:

1. Do not write a bullet-list abstract.
2. Do not use colon labels or colon-led pseudo-outlines in the final abstract, such as `Background:`, `Method:`, `Results:`, or `We make three contributions:`.
3. Avoid excessive enumeration, slash lists, semicolon inventories, and "first/second/third" contribution lists.
4. Prefer natural prose where each sentence advances the story rather than listing components.
5. Do not over-explain method internals; preserve space for concrete results.
6. Do not make unsupported claims; add a red TODO when exact results, evidence, or scope are missing.
7. Prefer one clear message per sentence.
8. Keep technical terms self-contained and readable.

Before finalizing, check:

1. Word count fits the venue or 150-250 word default.
2. Sentence count is exactly 5-6 unless the venue format forces otherwise.
3. The abstract follows Background -> Gap -> Insight -> Method -> Result -> Significance, with Insight and Method merged only when necessary.
4. The result sentence has the most concrete evidence in the abstract.
5. The abstract states the central claim without flat enumeration.
6. No colon labels, colon-led contribution lists, or overly enumerative phrasing remain.

## Pre-Writing Questions (Important)

Answer these before writing:

1. What technical problem do we solve, and why is there no well-established solution? (important)
2. What is our technical contribution?
3. Why can our method work in essence?
4. What technical advantage and new insight do we provide? (important)

## Version 1: Challenge -> Contribution

Introduce the technical challenge, then use one to two sentences to present the technical contribution that solves the challenge.

### Structure

1. Task.
2. Technical challenge for previous methods.
3. One to two sentences introducing the technical contribution for solving the challenge.
4. Benefits of the technical contribution.
5. Experiment summary.

### Expert Notes

1. Discuss previous work around the technical challenge that we actually solve.
2. For the contribution sentence(s), usually mention the technical term/name only; do not explain every detailed step.
3. The technical term must be easy to understand; readers should not feel a jump.
4. This ability is very important for writing a good abstract.

Version 1 local cite:

1. `references/examples/abstract/template-a.md`

## Version 2: Challenge -> Insight -> Contribution

Introduce the technical challenge, then use one to two sentences to present the insight for solving the challenge, and then one sentence to present the technical contribution that implements this insight.

### Structure

1. Task.
2. Technical challenge for previous methods.
3. One sentence introducing the insight for solving the challenge.
4. One to two sentences introducing the technical contribution that implements the insight.
5. Benefits of technical novelty.
6. Experiment summary.

### Expert Notes

1. Discuss previous work around the technical challenge that we actually solve.
2. Introduce the insight in one clear sentence.
3. For the implementation sentence(s), usually mention the technical term/name only; do not explain every detailed step.
4. The technical term must be easy to understand; do not create a jump in reading.
5. This ability is very important for writing a good abstract.

Version 2 local cite:

1. `references/examples/abstract/template-b.md`

## Version 3: Multiple Contributions

Version 3: When there are multiple technical contributions, describe each contribution together with its technical advantage.

### Structure

1. Task.
2. If needed, one contrast sentence about prior methods.
3. Contribution sentence 1 + technical advantage.
4. Contribution sentence 2 + technical advantage.
5. Contribution sentence 3 + technical advantage.
6. Experiment summary.

### Expert Notes

1. When there are multiple technical contributions, describe each contribution together with its technical advantage.
2. The ability to express "contribution + advantage" in one sentence is very important for writing a good abstract.

Version 3 local cite:

1. `references/examples/abstract/template-c.md`

## Example Bank

1. `references/examples/abstract-examples.md`
2. `references/examples/abstract/template-a.md`
3. `references/examples/abstract/template-b.md`
4. `references/examples/abstract/template-c.md`

## Abstract Quality Checklist

1. Can a reader identify task, challenge, insight/contribution, and results in one pass?
2. Are all major claims supported by experiments?
3. Are technical names self-contained and readable?
4. Is there any sentence that mixes too many messages?
5. Does the abstract follow the 5-6 sentence Background -> Gap -> Insight -> Method -> Result -> Significance structure?
6. Does the abstract roughly follow the 25/25/35/15 IMRD information budget?
7. Is it within the target venue word limit or the 150-250 word default?
8. Does it avoid colon labels, colon-led contribution lists, and overly enumerative phrasing?
