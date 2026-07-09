# Context

## Glossary

### Counter-argument
The paper-reader workflow for Discussion, Limitations, and late Experiments sections. It tests whether the draft anticipates hostile reviewer objections, rival explanations, fake limitations, and overextended claims.

### Reviewer threat model
The internal lens used by `counter-argument`: model what a skeptical reviewer would attack, then help the author acknowledge and neutralize the strongest threats without weakening the paper's core claim.

### Best-explanation test
The review test for result interpretation: ask whether the author's explanation is the simplest complete account of the evidence, or whether the draft forces a preferred hypothesis while ignoring stronger alternatives.

### Workflow boundary
`signpost-check` tests navigability, `logic-gap` tests missing proof inside the claim chain, and `counter-argument` tests whether result interpretation survives rival explanations and reviewer attacks.

### Claim-type audit
The `logic-gap` operation that classifies a claim before judging its proof: factual claims need observation, causal claims need causal evidence, and value claims need an explicit criterion.

### Analogy-as-evidence audit
The `logic-gap` operation that flags when an academic draft uses analogy, inspiration, resemblance, or borrowed terminology as if it were empirical, mathematical, or mechanistic evidence.
