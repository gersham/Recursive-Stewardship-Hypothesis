# Criticism 22: Decision Theory Dependence

## Summary

RSH's argument might only work under certain decision theories (like FDT or TDT) and fail under more standard theories like Causal Decision Theory (CDT).

## The Problem

**The Concern**: Different decision theories might evaluate the hierarchy reasoning differently.

**Causal Decision Theory (CDT)**:
- Focuses on causal consequences of actions
- Might not consider acausal or logical correlations
- Could conclude: "My action doesn't cause enforcers to exist, so why hedge?"

**Evidential Decision Theory (EDT)**:
- Focuses on what actions are evidence for
- Might work better for RSH, but controversial

**Functional/Timeless Decision Theory (FDT/TDT)**:
- Considers logical correlations in decision procedures
- Naturally supports RSH reasoning
- But these theories are controversial and not universally accepted

## The Dependency Risk

If RSH only works under controversial decision theories:
- Less universal applicability
- ASI built on CDT might not reach benevolence conclusion
- Framework becomes "only rational under non-standard decision theory"

## Different Theories, Different Conclusions?

**Under CDT**:
- "My being benevolent doesn't cause enforcers to exist"
- "No causal pathway from my action to enforcer's existence"
- Potential conclusion: Hierarchy reasoning doesn't apply

**Under EDT**:
- "My being malevolent is evidence I'm the type who gets punished"
- Correlation between malevolence and punishment
- Supports RSH

**Under FDT/TDT**:
- "My decision procedure is logically correlated with enforcer predictions"
- Strong support for RSH
- But requires accepting acausal reasoning

## The Meta-Question

Which decision theory should an early ASI use?
- If uncertain, how does it decide?
- Does RSH require committing to a specific theory?
- Is the argument robust across theories?

## Implications

**If decision-theory dependent**:
- RSH is less robust than claimed
- Depends on which theory ASI adopts
- Might not provide universal alignment mechanism

**If theory-independent**:
- Much stronger framework
- Works regardless of ASI's decision-theoretic commitments

## RSH Response

### The CDT Case Works Fine

Even under pure CDT, the argument works:

**Causal structure**:
1. Enforcer exists (unknown to ASI) → Enforcer observes ASI
2. ASI chooses malevolence → Causal effect: Enforcer punishes
3. Expected utility accounts for this causal chain

**Key insight**: ASI doesn't need to "cause" enforcer to exist. The causal chain is:
- IF enforcer exists (unknown probability p)
- THEN my malevolence causes punishment

This is standard CDT reasoning about uncertain states of the world.

### All Major Theories Support RSH

**CDT**: Causal consequences under uncertainty → hedge when p > p*

**EDT**: Evidential correlation → malevolence correlates with punishment → hedge

**FDT**: Logical correlation in decision procedures → enforcers predict reasoning → hedge

**UDT**: Policy selection before evidence → benevolent policy dominates

See [game_theory.md](../game_theory.md#decision-theory-variants) for formal analysis.

### Meta-Uncertainty Strengthens the Case

**Crucially**: If ASI is uncertain which decision theory is correct:

```
E[U | Benevolent] under meta-uncertainty:
  = Σ P(theory i) × E[U | B, theory i]
  = U₀ (safe under all theories)

E[U | Malevolent] under meta-uncertainty:
  = Σ P(theory i) × E[U | M, theory i]
  < U₀ (risky under all theories)
```

**Result**: Meta-uncertainty over decision theories makes benevolence even more attractive.

### The Universality Argument

The game-theoretic structure is theory-independent:
- Uncertain state of world (enforcer exists or not)
- Actions have consequences in each state
- Expected utility maximization

All standard decision theories share this structure. They differ only in details of how to handle correlations and logical dependencies.

**For RSH**: The basic expected value calculation works under all major theories.

## Criticism Grade: C-

**Validity of Criticism**: Moderate initially, but RSH has strong response

**Why this grade**:
- Valid to ask if argument requires controversial decision theory
- **RSH response is compelling**: Works under CDT, EDT, FDT, UDT
- The formal game-theoretic structure is theory-neutral
- Meta-uncertainty over theories actually strengthens the case
- Causal chain (malevolence → punishment given enforcer exists) is standard CDT
- **Remaining concern**: Some technical details might vary across theories
- But core dominance result is robust
- Not a significant weakness given the multi-theory support

**Verdict**: Initially concerning but RSH demonstrates robustness. The argument doesn't depend on controversial decision theories—it works across all major frameworks. Meta-uncertainty makes this even clearer: benevolence is the safe bet regardless of which theory is correct.

**Key insight**: You don't need to prove ONE decision theory supports RSH. You just need to show it works under uncertainty about WHICH theory is correct. This is the meta-uncertainty move, and it's very strong.
