# Research-Paper-Reader-Skills

Reader-first writing skills for research papers.

This repository packages reusable review-oriented skills that help authors
switch from writer mode to reader mode when drafting and revising academic
papers.

## Why

Many paper drafts fail not because the idea is weak, but because the prose is
written too much from the author's point of view.
These skills are designed to surface:

- logic gaps
- weak motivation
- unclear contribution framing
- reviewer objections and alternative explanations
- implementation details that read like code comments
- paragraphs with poor signposting

## Current skill

### `paper-reader`

A writing-review skill that critiques paper drafts through five explicit reader
lenses:

1. `elevator-pitch`
   For `Title`, `Abstract`, and `Introduction`.

2. `logic-gap`
   For `Method`, formulas, algorithm flow, claim-type mismatches, and
   analogy-as-evidence failures.

3. `counter-argument`
   For `Discussion`, `Limitations`, and result interpretation. Builds a
   reviewer threat model and tests whether the draft handles rival
   explanations.

4. `signpost-check`
   For `Related Work`, long `Experiments`, rebuttal structure, and long
   sections whose organization is hard to follow.

5. `engineer-translation`
   For `Implementation Details`, optimization tricks, and systems prose.

## Repository structure

```text
skills/
├── README.md
└── paper-reader/
    ├── SKILL.md
    └── REFERENCE.md
```

## Usage

Typical prompts:

- `use paper-reader on this abstract`
- `use paper-reader in logic-gap mode on this method section`
- `use paper-reader counter-argument on this discussion and limitations section`
- `use paper-reader engineer-translation on this implementation paragraph`
- `use paper-reader signpost-check on these experiment paragraphs`

## Example usage

### Abstract review

Input:

```text
Use paper-reader on this abstract.

Direct mesh reconstruction from images without post-processing remains
attractive because it preserves explicit surfaces and compatibility with
standard graphics pipelines. However, ...
```

Expected behavior:

- identify vague or over-claimed framing
- test whether the `limitation -> gap -> solution` transition is sharp
- suggest cleaner abstract-level wording

### Method review

Input:

```text
Use paper-reader in logic-gap mode on this method section.
```

Expected behavior:

- flag undefined variables or modules
- point out skipped reasoning
- separate factual, causal, and value claims before judging evidence
- flag analogy, inspiration, or resemblance when it is doing proof-work
- list the minimum fixes needed for reviewability

### Discussion and limitations review

Input:

```text
Use paper-reader counter-argument on this discussion and limitations section.
```

Expected behavior:

- identify what a skeptical reviewer would attack
- test whether the author's explanation is the best explanation for the evidence
- flag ignored alternative explanations and superficial limitations
- suggest ways to acknowledge and neutralize threats without weakening the core claim

### Experiments review

Input:

```text
Use paper-reader signpost-check on these experiment paragraphs.
```

Expected behavior:

- extract paragraph topic sentences
- detect weak transitions
- suggest better signposting for the section flow

## Notes

This repository currently focuses on research-paper writing for computer
graphics, vision, and adjacent systems papers, but the review patterns are
general enough to transfer to many CS writing workflows.
