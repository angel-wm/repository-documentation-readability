# Repository Documentation Readability

Practical guidance for clear, readable, and mobile-friendly repository documentation.

This project focuses on **how technical repository documentation is presented**: how to explain difficult material without removing technical detail, structure a README for progressive reading, and choose appropriately between prose, tables, procedures, code blocks, text trees, and Mermaid diagrams.

It is useful for repository maintainers, developers, technical writers, and AI-assisted documentation workflows.

It is not a documentation standard, protocol, schema, or certification system. A project's own semantics, specifications, required structures, and authoritative sources always take precedence.

## Guide

Read [GUIDE.md](GUIDE.md) for the full guidance.

The guide combines compatible ideas from established documentation practice while staying focused on repository readability.

It covers:

- reader intent using the tutorial / how-to / reference / explanation distinction;
- audience, relevance, prerequisites, and limitations;
- preserving technical meaning before presentation;
- progressive disclosure and documentation-set qualities;
- prose, headings, navigation, tables, procedures, and troubleshooting;
- code, commands, example validation, and file trees;
- Mermaid diagram selection and orientation;
- accessibility, descriptive links, terminology, and source-readable Markdown;
- README structure and repository coherence;
- mobile/desktop balance;
- anti-patterns and a review checklist;
- worked before/after transformations in [examples/before-after.md](examples/before-after.md).

## Agent Skill

For repeated AI-assisted documentation work, this repository also ships an installable skill at [`skills/repository-documentation-readability/`](skills/repository-documentation-readability/).

The skill uses progressive loading:

- `SKILL.md` contains the compact operational rules used for ordinary documentation tasks;
- `references/GUIDE.md` bundles the complete guide for targeted or comprehensive loading when a task is complex;
- `references/before-after.md` provides worked examples only when they are useful.

This keeps routine context small without removing access to the full guidance.

When installing the skill elsewhere, copy the **entire skill directory**, not only `SKILL.md`. The root `GUIDE.md` and `examples/before-after.md` remain canonical in this source repository; the copies under `references/` exist so the skill remains self-contained when installed.

## Use it from another repository

For repeated AI use, prefer installing the skill above. For an ad-hoc task without installation, another project can point an AI assistant or human reviewer to the current `main` guide:

```text
https://github.com/angel-wm/repository-documentation-readability/blob/main/GUIDE.md
```

A concise instruction is enough:

> Read and apply the Repository Documentation Readability Guide from the repository above as presentation guidance for this task. Preserve this project's native semantics, specifications, and required structures.

Do not copy the entire guide into every repository unless the project specifically needs a local copy.

Use `main` to follow the current development guide. When reproducibility matters, pin a published release tag instead.

## Relationship to existing documentation practice

This project does not try to replace established documentation work such as Diátaxis, Standard Readme, The Good Docs Project, technical-writing style guides, or Markdown specifications.

Instead, it concentrates on a narrower question:

> How should repository documentation present technical information so that it remains rigorous, understandable, scannable, and useful across mobile and desktop?

See [Influences and boundaries](GUIDE.md#influences-and-boundaries) for what the guide adopts from each source and what it deliberately leaves out.

## Status

The guide currently defines version **0.2** on `main`. Fixed release snapshots are represented by Git tags and GitHub Releases. `main` may continue to evolve after a release.

For corrections or suggestions, [open a GitHub issue](https://github.com/angel-wm/repository-documentation-readability/issues).

## License

Original material in this repository is dedicated under [CC0-1.0](LICENSE). External references retain their own terms.
