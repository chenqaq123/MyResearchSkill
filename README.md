# My Research Skills

This repository contains my personalized academic research and paper-writing skill package.

The current main skill is:

- `research-paper-writing-refined/`: a personalized academic paper writing workflow for ML/CV/NLP-style research papers.

## What This Skill Helps With

This skill is designed for drafting, revising, and reviewing research papers with a strong reviewer-facing workflow.
It emphasizes:

- target venue and requirement checking,
- central-claim-driven writing,
- reference-paper calibration,
- section-level paper structure,
- claim-evidence alignment,
- Related Work coverage and baseline alignment,
- experiment planning and analysis,
- TODO marking for missing experiments or evidence,
- visually rich paper presentation with text, tables, and figures,
- appendix routing during draft review,
- LaTeX project organization and PDF QA.

## Personalized Additions

Compared with the original academic writing skill, this refined version adds my own writing and review preferences, including:

- confirm target venue before major writing,
- check official venue requirements,
- confirm page budget instead of defaulting to a fixed draft length,
- search and integrate three categories of reference papers,
- write around a central claim instead of flat narration,
- avoid unnecessary tiny sections,
- strengthen Related Work citation coverage,
- align Related Work with experimental baselines,
- preserve polished main result tables while generating complementary figures,
- use Python for data-driven plots/tables,
- use Image 2 for non-data illustrative/showcase figures when appropriate,
- mark missing evidence with visible TODOs,
- route appendix-worthy material out of the main text during draft review,
- split final LaTeX delivery into `main.tex`, `sections/`, `figures/`, `tables/`, and `appendix/`,
- compile and inspect PDF output before final handoff.

## Installation

### Codex

Copy the skill into your Codex skills directory:

```bash
mkdir -p "$CODEX_HOME/skills"
cp -R research-paper-writing-refined "$CODEX_HOME/skills/"
```

Use it with:

```text
Use $research-paper-writing-refined to help write or review my paper.
```

### Claude Code

Global installation:

```bash
mkdir -p "$HOME/.claude/skills"
cp -R research-paper-writing-refined "$HOME/.claude/skills/"
```

Project-level installation:

```bash
mkdir -p .claude/skills
cp -R research-paper-writing-refined .claude/skills/
```

### Gemini

```bash
mkdir -p "$HOME/.gemini/skills"
cp -R research-paper-writing-refined "$HOME/.gemini/skills/"
```

## Attribution

This repository is based on a local adaptation of an academic paper-writing skill.
The original skill package itself credits much of the writing methodology to Prof. Peng Sida's public study notes:

- Notes: https://pengsida.notion.site/c1a22465a0fa4b15a12985223916048e
- Original repository: https://github.com/pengsida/learning_research

I sincerely acknowledge those public materials and the original skill packaging work.
My contribution in this repository is the personalized refinement, additional workflows, and project-specific writing preferences.

## License

This repository keeps the MIT License from the original skill package.
