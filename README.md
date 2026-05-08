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
- implementation details that read like code comments
- paragraphs with poor signposting

## Current skill

### `paper-reader`

A writing-review skill that critiques paper drafts through four explicit reader
lenses:

1. `elevator-pitch`
   For `Title`, `Abstract`, and `Introduction`.

2. `logic-gap`
   For `Method`, formulas, and algorithm flow.

3. `engineer-translation`
   For `Implementation Details`, optimization tricks, and systems prose.

4. `signpost-check`
   For `Related Work`, `Experiments`, and long discussion sections.

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
- list the minimum fixes needed for reviewability

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
