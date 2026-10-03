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

## Criticism Grade: D+

**Status**: Addressed for the causal mechanisms; open for the acausal mechanism

**Validity of Criticism**: Weak for most of RSH. (Revised October 2026; previously graded C-.)

**Why this grade**:
- In the causal version of the model, the evaluator's existence doesn't depend on the agent's choice, and punishment is a causal consequence of that choice. CDT, EDT, FDT and UDT all give the same answer ([game_theory.md](../game_theory.md#decision-theory-variants)). So cosmological enforcers and observing simulators don't depend on a contested decision theory.
- The acausal mechanism in the README does depend on one. It needs FDT/UDT-style reasoning, and it needs the agent's and the evaluator's decision procedures to be correlated.
- Two claims in the response above overstate things. Meta-uncertainty over decision theories doesn't *strengthen* the case; it only shows that disagreement isn't a problem when every theory agrees. And "E[U | B] = U₀, safe under all theories" holds only in the two-type model. With stewardship-penalizing evaluators, benevolence isn't riskless.

**Verdict**: A weak criticism for RSH's causal mechanisms, and a fair one for the acausal mechanism.
