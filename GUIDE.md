# Repository Documentation Readability Guide

Guide version: **0.1**

## Purpose

This guide helps make repository documentation easier to understand, scan, and maintain without reducing technical precision.

It focuses on presentation: how to explain technical material, structure a README, choose between prose, tables, procedures, code blocks, file trees, and Mermaid diagrams, and keep the result usable on both mobile and desktop.

It is **not** a standard, protocol, schema, certification system, or replacement for a project's own documentation rules. Project-native semantics, required structures, specifications, and source-of-truth documents take precedence.

The core principle is:

> Preserve technical truth, then reduce reader effort.

## What good repository documentation should do

Good documentation should help a reader answer four different kinds of questions:

| Reader need | Typical question | Usually best served by |
| --- | --- | --- |
| Understand | What is this, why does it exist, and how does it work? | Explanation, examples, small diagrams |
| Do | How do I install, configure, run, or change it? | Numbered procedures, commands |
| Look up | What option, file, field, API, state, or rule applies? | Tables, reference sections, code |
| Evaluate | What changed, what is supported, or what evidence exists? | Status, comparisons, evidence links |

A document does not need to fit one category only. A README often begins with understanding, supports a small amount of doing, and then links to deeper reference material.

## Preserve meaning before presentation

Readability work should not weaken semantics, contracts, schemas, source fidelity, or required project structure.

Use this decision rule:

```text
Can presentation improve without changing meaning or a required contract?
├── Yes → improve the presentation.
└── No  → preserve the structure and explain it clearly.
```

If a specification requires a four-column table, keep the four columns. Improve scanability through shorter cells, better headings, progressive disclosure, or nearby explanation instead of changing the contract.

Presentation preferences never override technical requirements.

## Reader-first explanation

Technical accuracy is necessary, but accuracy alone does not make documentation easy to learn from.

Prefer an explanation order that gives the reader a mental model before implementation detail:

1. State what the project, component, or concept is.
2. Explain why it exists or what problem it solves.
3. Show the simplest useful example.
4. Introduce the important terms and structure.
5. Add implementation details, edge cases, and deeper reference material.

Do not force every section into that sequence, but use it when readers need to build understanding.

### Be didactic without becoming vague

A didactic explanation should make the technical material easier to grasp, not remove it.

Prefer:

- concrete examples before abstract edge cases;
- one new idea at a time;
- short definitions near first use;
- explicit relationships between concepts;
- examples that demonstrate the real rule;
- explanations of why a command, constraint, or design choice matters.

Avoid:

- unexplained jargon;
- long conceptual preambles before the useful point;
- oversimplifications that become technically false;
- examples that contradict the actual contract.

### Make documentation engaging through clarity

Repository documentation does not need decorative language to be engaging.

Engagement usually comes from:

- visible structure;
- short feedback loops;
- concrete examples;
- useful diagrams;
- clear progress through a procedure;
- answers appearing near the questions that motivated them.

Do not add jokes, decorative diagrams, badges, animations, or marketing copy merely to make technical documentation feel more lively.

## Choose the simplest useful representation

Use the format that best matches the information.

| Information | Preferred representation |
| --- | --- |
| Simple explanation or rationale | Short prose |
| Comparison, roles, options, properties | Markdown table |
| Ordered procedure | Numbered list |
| Repository or directory structure | Text tree |
| Literal commands, code, config, logs | Fenced code block |
| Process, decision, branching, dependency | Mermaid flowchart |
| States and transitions | Mermaid state diagram |
| Interactions over time | Mermaid sequence diagram |
| Complex visual composition Mermaid cannot express clearly | External diagram as an exception |

Do not use a diagram when prose, a table, or a short list communicates the idea more clearly.

Do not use a table for narrative explanation.

Do not turn a directory tree into a diagram unless relationships, rather than filesystem structure, are the point.

## Progressive disclosure

Readers should encounter detail in layers.

A useful progression is:

```text
orientation
    ↓
small working example
    ↓
important concepts
    ↓
task-specific detail
    ↓
deep reference / evidence
```

Keep the entry point compact. Link to deeper material instead of front-loading everything.

This does not mean hiding important constraints. Put prerequisites, warnings, unsupported states, and required conditions before the reader reaches the action they affect.

## Prose

Use prose for concepts, rationale, constraints, caveats, interpretation, and information that does not depend on visual relationships.

Prefer:

- short paragraphs;
- one main idea per paragraph;
- important information early;
- concrete terminology;
- active voice when it improves clarity;
- links near the claims or concepts they support.

Avoid:

- walls of text;
- decorative introductions;
- repeating information already expressed clearly elsewhere;
- paragraphs that mix several unrelated ideas;
- headings followed by multiple dense screens without internal structure.

For long explanations, use headings to expose the argument or learning path.

## Headings and navigation

Use a stable heading hierarchy:

```text
H1 → document title
H2 → major section
H3 → subsection
H4+ → only when deeper nesting is genuinely useful
```

Headings should communicate what the reader will learn or find beneath them.

When refactoring an existing document:

- preserve established heading anchors when practical;
- check relative links before renaming headings;
- add direct reading-path links when a long document has several independent destinations;
- avoid excessive heading depth;
- do not create a heading for every short paragraph.

Navigation should reduce search effort, not create another documentation layer to maintain.

## Tables

Use Markdown tables for compact comparison, mapping, or reference.

Good uses include:

- file → responsibility;
- concept → meaning;
- option → tradeoff;
- state → interpretation;
- topic → authoritative source.

Prefer a few meaningful columns over many metadata columns.

If a table becomes very wide and its exact shape is not required, split it or move secondary detail into prose.

If a contract requires a wide table, preserve the required columns and improve readability through concise cells, nearby explanation, or sectioning.

A table and a diagram should coexist only when they answer different questions.

## Procedures

Use numbered lists when order matters.

Example:

1. Confirm prerequisites.
2. Run the setup command.
3. Verify the expected result.
4. Continue to the next configuration step.

Put commands inside the step where they are used.

Do not turn a straightforward procedure into a flowchart unless branching, loops, or multiple paths materially affect comprehension.

When a step can fail in a predictable way, place the relevant check or recovery guidance close to that step.

## Code, commands, and technical excerpts

Use fenced code blocks for commands, source code, configuration, logs, schemas, or literal file excerpts.

Prefer:

- one purpose per block;
- the smallest excerpt that supports the explanation;
- syntax highlighting when useful;
- surrounding prose that explains why the block matters;
- examples that can be copied with minimal editing.

Avoid:

- giant logs without selection;
- entire files when only a small excerpt matters;
- unrelated commands grouped into one block;
- screenshots of text that could be selectable text;
- example output that looks authoritative when it is only illustrative.

Distinguish commands from output when confusion is possible.

## Repository and file structures

Use text trees for filesystem structure.

```text
repository/
├── README.md
├── GUIDE.md
├── docs/
├── examples/
└── src/
```

Text trees are compact, copyable, diff-friendly, and usually easier to read on mobile than a diagram.

Use Mermaid instead when the important information is how components relate, not where files live.

## Mermaid diagrams

Mermaid is the default diagram format when a diagram materially improves comprehension and Git-hosted Markdown is the target.

Use inline Mermaid when practical.

Do not require diagrams.net, `.drawio`, generated PNG/SVG files, or a diagram build pipeline for ordinary repository documentation.

### A diagram should answer a harder visual question

Good diagram questions include:

- What happens next?
- Where does the flow branch?
- Which component depends on which other component?
- How does a state transition?
- Which actor communicates with which system?

If a diagram only restates one short sentence, remove it.

### One diagram, one idea

Prefer small diagrams over one giant diagram.

Roughly **3–7 primary nodes** is a useful default, not a hard limit.

Split a diagram when readers have to zoom, pan, or remember too many relationships at once.

### Keep labels short

Prefer:

```text
Select relevant sources
```

over a sentence-sized node.

Put the full explanation in nearby prose.

### Choose orientation from the content

Prefer top-to-bottom (`TD` or `TB`) when:

- the diagram is sequential;
- it has several levels;
- horizontal layout would become too wide;
- vertical layout materially helps mobile reading.

Prefer left-to-right (`LR`) when:

- the flow is short;
- there are few nodes;
- the relationship is naturally pipeline-like;
- it remains readable on a phone.

Do not make every diagram vertical or every diagram horizontal.

### Match the diagram type to the question

Use:

- `flowchart` for processes, branching, dependencies, and navigation;
- `stateDiagram-v2` for lifecycle states and transitions;
- `sequenceDiagram` for interactions over time.

Use more specialized Mermaid types only when they clearly improve the explanation.

## Accessibility and visual independence

Essential meaning should not depend on visual presentation alone.

Do not rely only on:

- Mermaid rendering;
- color;
- icons;
- screenshots;
- spatial position;
- images containing text.

Important rules, decisions, constraints, and outcomes should remain understandable from Markdown text.

Use screenshots when the visual state itself is the subject, such as a UI defect, design comparison, or rendered result that cannot be explained adequately as text.

Do not use color as the only distinction between pass/fail, active/inactive, required/optional, or similar states.

## Avoid duplication

Do not repeat the same information in prose, a table, and a diagram.

Use different representations together when each answers a different question.

For example:

- prose explains **why** something exists;
- a table explains **what each part means**;
- a diagram explains **how the parts relate**.

If removing one representation loses no useful information, remove it.

## README guidance

A README is usually an entry point, not the entire documentation system.

A useful progressive structure is:

```text
README
│
├── Quick understanding
│   ├── what the project is
│   ├── what problem it solves
│   ├── who it is for
│   └── project status when relevant
│
├── Practical use
│   ├── prerequisites
│   ├── installation / setup
│   ├── smallest useful example
│   └── common next action
│
└── Deeper material
    ├── architecture / concepts
    ├── reference
    ├── decisions
    ├── contributing
    └── evidence / research
```

Not every README needs every section. The shape should follow the project and its audience.

### First screen

A reader should normally be able to learn quickly:

- what the project is;
- why it exists;
- whether it is relevant to them;
- where to go next.

Do not make readers scroll through badges, giant logos, exhaustive tables of contents, or implementation history before reaching that information.

### Smallest useful example

When the project is something a reader can use directly, show the smallest example that demonstrates real value.

A useful example should be:

- technically correct;
- short enough to understand quickly;
- representative of normal use;
- followed by a path to deeper configuration or reference.

### Keep deep material out of the README when necessary

Move detailed architecture, exhaustive API reference, historical decisions, long tutorials, and validation evidence into dedicated documents when they begin to obscure the entry path.

The README should link to those sources clearly.

## Mobile and desktop balance

Optimize for both contexts.

### Mobile

Prefer:

- short sections;
- clear headings;
- narrow optional tables;
- vertical multi-step diagrams;
- short diagram labels;
- small examples;
- important information near the start of a section.

Avoid:

- optional six-column tables;
- dense horizontal diagrams;
- diagrams that require zoom to understand every node;
- long unbroken sections.

### Desktop

Use available width when it improves comprehension.

A compact horizontal flow or comparison may be better on desktop and still be acceptable on mobile.

The goal is not mobile-first at all costs. The goal is readable documentation in both contexts.

## Anti-patterns

### Diagram as decoration

Do not add a diagram that says exactly what a nearby sentence already says.

### Giant architecture diagram

Do not combine every service, file, actor, state, dependency, and validation path into one diagram.

Separate concerns when multiple diagrams genuinely help.

### Paragraphs inside diagram nodes

Keep node labels short and move explanation into prose.

### Wide optional metadata tables

If many columns are optional and the table becomes difficult to scan, keep the important comparison fields and move the rest elsewhere.

### Breaking a contract for presentation

Do not remove required fields, columns, headings, or identifiers merely to make a document visually narrower.

### Screenshots of copyable text

Use code blocks for commands, configuration, errors, or logs unless the visual rendering itself is important.

### README as the whole documentation system

Do not force specification, architecture, decisions, tutorials, history, and evidence into a single README when dedicated documents would make navigation clearer.

### Technical dump before orientation

Do not begin with implementation internals when a new reader still does not know what the project is or why it matters.

## Worked examples

The guide includes two fictional before/after transformations in [examples/before-after.md](examples/before-after.md):

- a dense README section rewritten into a clearer explanation, procedure, and compact reference table;
- an overengineered Mermaid flow simplified into a numbered procedure, keeping visual structure only where it adds information.

Use the examples to understand the reasoning behind the transformations, not as mandatory templates. The right representation still depends on the project, audience, and technical contract.

## Review checklist

Before considering a README or documentation refactor complete, check:

- [ ] Can the reader understand the purpose quickly?
- [ ] Is the intended audience or use case clear?
- [ ] Are technical semantics and required structures preserved?
- [ ] Does important information appear before dependent detail?
- [ ] Are long explanations divided into meaningful sections?
- [ ] Is the heading hierarchy clear and stable?
- [ ] Were existing anchors and links preserved or deliberately updated?
- [ ] Are comparisons represented as tables where appropriate?
- [ ] Are ordered procedures represented as numbered steps?
- [ ] Are code and command blocks focused and copyable?
- [ ] Are file structures represented as text trees?
- [ ] Does every diagram materially improve comprehension?
- [ ] Does each diagram communicate one main idea?
- [ ] Is diagram orientation appropriate for its content?
- [ ] Are diagrams usable on narrow screens without excessive zoom?
- [ ] Does essential meaning remain available as text?
- [ ] Does anything important depend only on color or an image?
- [ ] Is information unnecessarily duplicated?
- [ ] Does the README remain an entry point instead of becoming a reference dump?
- [ ] Can readers reach deeper material progressively?
- [ ] Are examples technically correct and representative?

## Related foundations

This guide does not replace existing documentation practices. It draws compatible ideas from established work and applies them specifically to repository-documentation readability.

- [Standard Readme](https://github.com/RichardLitt/standard-readme) provides a structured README specification for many open-source projects.
- [Diátaxis](https://diataxis.fr/) distinguishes tutorials, how-to guides, reference, and explanation according to reader need.
- [The Good Docs Project](https://www.thegooddocsproject.dev/) provides reader-centered documentation templates and guidance.
- [Google Developer Documentation Style Guide](https://developers.google.com/style) provides detailed technical-writing and accessibility guidance.
- [Write the Docs](https://www.writethedocs.org/guide/) collects practical software-documentation guidance and community practice.
- [CommonMark](https://spec.commonmark.org/) defines a Markdown syntax specification.
- [GitHub documentation on READMEs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes) describes README behavior and common repository entry-point expectations on GitHub.

Use those sources when their broader or more specialized guidance is needed. This guide focuses on the presentation decisions that most directly affect repository readability.

## Summary

Use:

**prose for explanation, tables for comparison, numbered lists for ordered procedures, code blocks for literal technical material, text trees for filesystem structure, and Mermaid for relationships or flows.**

Preserve technical meaning first.

Teach the reader enough to build a mental model.

Then expose deeper detail progressively.

The objective is not more visual material.

The objective is less friction between the reader and the technical truth.
