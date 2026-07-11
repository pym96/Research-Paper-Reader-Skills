---
name: write-method-causally
description: Extract and rewrite academic method descriptions as causal narratives that connect problem objects, engineering mechanisms, intermediate representations, optimization objectives, and scientific purposes. Use when drafting or revising an Abstract, Method, Contributions, or highlight paragraph; separating How to do from Why to do; converting component inventories into research prose; or auditing whether every design choice has a justified role and supportable claim strength.
---

# Write Method Causally

Turn implementation sequences into scientific arguments. Do not rewrite first.
Recover the method's causal architecture, then write only the dependencies that
the architecture supports.

## Core model

Use this adaptable chain:

```text
problem object
-> identify or assign it with mechanism A
-> construct representation B with mechanism C
-> optimize through objective D
-> compose or decode the result
-> obtain desired system property E
```

Omit stages the method does not contain. Do not invent an identification,
representation, objective, or guarantee merely to complete the template.

Distinguish three roles:

- **Scientific role**: what problem, representation, capacity, constraint, or
  property a phrase names.
- **Technical realization**: the algorithm, module, encoding, loss, or operation
  that implements it.
- **Causal bridge**: why that realization should serve the scientific role.

Technical vocabulary is not itself rationale. Force a `So what?` answer for
every engineering choice.

## Workflow

### 1. Establish the claim boundary

Extract before editing:

- the problem object the method acts on;
- the limitation in the base representation or pipeline;
- the properties the method intends to change;
- the invariants or capabilities it intends to preserve;
- the final output and how it is used;
- the evidence available for each claimed effect.

Separate representational capacity from observed quality. A mechanism may
enable a function class without guaranteeing better benchmark results.

### 2. Build the How/Why table

For each stage, fill this schema:

| Stage | Input or problem object | How to do | Immediate output | Why to do | Claim basis |
|---|---|---|---|---|---|
| 1 | What enters or must be resolved | Concrete mechanism | What the mechanism produces | Scientific purpose | Definition, architecture, objective, or experiment |

Require each mechanism to have one immediate output and one primary purpose.
Split overloaded stages instead of assigning several vague benefits to one
component.

### 3. Collapse components into conceptual modules

Group mechanisms that serve the same purpose. Prefer three to five role-led
modules over a list of implementation nouns.

Good module identities name the scientific responsibility:

- compositing-aware carrier assignment;
- renderer-consistent surface attachment;
- surface-conditioned appearance representation;
- composition-aligned residual learning.

Do not elevate every implementation detail into a contribution. Treat helper
operations as support for the nearest conceptual module.

### 4. Write purpose-first causal prose

Use this sentence progression when it matches the method:

```text
We propose X, a [scientific identity] that [primary goal] while [preserved invariant].
To [purpose], X [mechanism], providing or yielding [intermediate representation].
X then [mechanism], enabling [representational capability] while [constraint].
During training, [objective design], directing or encouraging [optimization role].
At inference, [decode or composition], producing [final output].
```

Prefer purpose-first order when the mechanism is difficult to parse:

```text
To attach the prediction to the responsible surface, we select ... and lift ...
```

Use connectors according to their actual logical function:

- stage order: `first`, `then`, `finally`, `during training`, `at inference`;
- purpose: `to`, `so that`;
- mechanism: `using`, `through`, `by`;
- immediate consequence: `yielding`, `providing`, `producing`;
- capacity: `enabling`, `allowing`;
- preservation or trade-off: `while`, `without replacing`.

Do not add transitions merely for fluency. Every connector must encode a real
dependency, purpose, consequence, or contrast.

### 5. Audit claim strength

Match verbs to what is actually supported:

- Use `guarantees` or `ensures` only for a proved or structurally unavoidable
  property.
- Use `preserves` for an architectural invariant that remains unchanged.
- Use `enables` or `allows` for representational capacity.
- Use `encourages`, `promotes`, or `directs` for a loss or training objective.
- Use `improves`, `outperforms`, or `reduces` only with experimental evidence.

Reject these failure modes:

- architecture inventory: `We use A, B, C, and two losses`;
- purpose laundering: attaching generic benefits such as efficiency or
  robustness without mechanism or evidence;
- missing input/output: naming a module without saying what enters and leaves;
- repeated rationale: restating the same purpose after every component;
- analogy as evidence: using resemblance to another system as proof;
- implementation jargon presented as scientific motivation;
- experimental outcomes written as mechanism-level guarantees.

### 6. Perform the cold-reader test

Read only the problem statement, module identities, and purpose clauses. Verify
that they recover the full story without implementation details. Then read only
the mechanism clauses and verify that they form an executable dataflow.

The section passes only when both views are coherent and map to each other.

## Output contract

When asked to **extract** a method, return:

1. the problem-to-property chain;
2. the How/Why table;
3. three to five conceptual modules;
4. missing causal bridges or unsupported claims.

Do not rewrite unless requested.

When asked to **rewrite**, perform the extraction internally first, then return:

1. the revised paragraph;
2. a concise mapping from each sentence to its How and Why;
3. any remaining evidence or claim-strength caveats.

When asked to **audit**, lead with logic gaps and overclaims rather than prose
preferences.

## Minimal example

Weak inventory:

```text
We use variance analysis, interpolation, hash encoding, and two losses.
```

Causal version:

```text
To identify ambiguous boundary elements, we measure prediction variance.
We then interpolate their features into a continuous field and encode it at
multiple resolutions to represent spatial variation efficiently. Alignment and
continuity objectives coordinate the two representations and encourage smooth
boundary predictions.
```

The causal version names the problem object, mechanism, intermediate
representation, optimization role, and intended property without claiming that
the objective guarantees the outcome.
