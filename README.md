# Repository Documentation Readability

Practical guidance for clear, readable, and mobile-friendly repository documentation.

This project focuses on **how technical repository documentation is presented**: how to explain difficult material without removing technical detail, structure a README for progressive reading, and choose appropriately between prose, tables, procedures, code blocks, text trees, and Mermaid diagrams.

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

## Use it from another repository

To follow the current `main` version, another project can point an AI assistant or human reviewer to:

```text
https://github.com/angel-wm/repository-documentation-readability/blob/main/GUIDE.md
```

A concise instruction is enough:

> Read and apply the Repository Documentation Readability Guide from the repository above as presentation guidance for this task. Preserve this project's native semantics, specifications, and required structures.

Do not copy the entire guide into every repository unless the project specifically needs a local copy.

Once tagged releases exist, pin a release tag instead of `main` when reproducible guidance is more important than following the latest revision.

## Relationship to existing documentation practice

This project does not try to replace established documentation work such as Diátaxis, Standard Readme, The Good Docs Project, technical-writing style guides, or Markdown specifications.

Instead, it concentrates on a narrower question:

> How should repository documentation present technical information so that it remains rigorous, understandable, scannable, and useful across mobile and desktop?

See [Influences and boundaries](GUIDE.md#influences-and-boundaries) for what the guide adopts from each source and what it deliberately leaves out.

## Status

The guide currently defines version **0.2** on `main`. Formal immutable snapshots are represented by Git tags and GitHub Releases when present. `main` may continue to evolve after a release.

## License

Original material in this repository is dedicated under [CC0-1.0](LICENSE). External references retain their own terms.
