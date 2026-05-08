---
name: paper-reader
description: Review paper drafts through explicit reader roles such as logic-gap reviewer, impatient area chair, engineering translator, and signpost editor. Use when writing or revising academic papers and the user asks for reader perspective, reviewer mode, logic-gap checking, elevator-pitch testing, paragraph signposts, or clearer academic prose.
---

# Paper Reader

Use this skill to switch from author mode to reader mode when revising paper drafts.
Pick one workflow based on the section type and the user's request.

## Quick start

- If the user gives `Abstract` or `Introduction`, use `elevator-pitch`.
- If the user gives `Method`, use `logic-gap`.
- If the user gives `Implementation` or systems detail, use `engineer-translation`.
- If the user gives `Related Work` or long `Experiments`, use `signpost-check`.
- If the user does not specify a mode, infer it from the section and state the chosen mode in one short line.

## Output contract

Unless the user asks otherwise, structure the response as:

1. `Findings`
2. `Why it matters`
3. `Rewrite suggestions`

For review-style outputs, prefer harsh but concrete criticism over encouragement.
Quote only short phrases from the user's text when necessary for localization.

## Workflows

### `logic-gap`

Use for `Method`, formulas, algorithm flow, and system design claims.

Tasks:
- Scan sentence by sentence for unstated assumptions and skipped reasoning.
- Flag variables, symbols, modules, or branches introduced without definition.
- Identify places where causal claims are asserted but not justified.
- Ask whether the coupling boundary to prior components is clear.

Return:
- `Logic-gap list` with local references
- `Missing definitions`
- `Minimum fixes needed to make the section reviewable`

### `engineer-translation`

Use for `Implementation Details`, optimization tricks, CUDA/PyTorch discussion, and systems paragraphs.

Tasks:
- Detect prose that reads like code comments or lab notes.
- Lift low-level implementation detail into design rationale.
- Force a `So what?` answer for each engineering decision.
- Connect implementation choices to accuracy, speed, memory, robustness, or usability.

Return:
- `Too low-level passages`
- `Why the current phrasing is weak`
- `Rewrite of the two worst passages`

### `elevator-pitch`

Use for `Title`, `Abstract`, `Introduction`, and submission metadata such as `Benefit` or `Contribution`.

Tasks:
- Summarize the paper's core contribution in one sentence.
- Check whether the summary matches the user's intended claim.
- Test whether `limitation -> gap -> solution -> evidence` flows naturally.
- Flag vague novelty language, weak motivation, and over-claiming.

Return:
- `One-line summary the reader would retain`
- `Where the framing fails`
- `How to sharpen the story`

### `signpost-check`

Use for long `Related Work`, `Experiments`, discussion, and rebuttal drafts.

Tasks:
- Extract each paragraph's opening sentence and closing transition.
- Judge whether the section remains logically traceable from those lines alone.
- Flag paragraphs whose topic sentence does not orient the reader.
- Suggest better signpost sentences and transitions.

Return:
- `Paragraph map`
- `Broken transitions`
- `Suggested topic sentences`

## Escalation rule

If multiple workflows apply, use the most reader-critical one first:

1. `elevator-pitch`
2. `logic-gap`
3. `signpost-check`
4. `engineer-translation`

If the user asks for deep revision, first critique, then rewrite.
