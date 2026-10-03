# Criticism 24: Formalization Gap

## Summary

RSH presents itself as a game-theoretic argument, but it lacks the formal proofs a game-theoretic result needs. It has no precise model, no equilibrium proofs and no rigorous treatment of the infinite hierarchy. Without these, its claims are stronger than its support.

## The Problem

A proper game-theoretic result needs:
- **A formal model**: players, actions, information, payoffs, and the equilibrium concept used.
- **Equilibrium results**: proof that an equilibrium exists; either proof that it is unique or a description of every equilibrium; and stability under perturbation.
- **The infinite case**: proof that the N-level game has a well-defined limit as N grows, and a description of that limit.
- **Robustness**: how the result holds up under bounded rationality (ε-equilibria), coalitions (coalition-proofness), different decision theories, and different parameter values.

Phrases such as "derives benevolence from structure" suggest results of this kind. If RSH is meant as a theorem, the gap is critical. If it is meant as a philosophical framework, like the zoo hypothesis or the simulation argument, it doesn't need formal proof. But then it shouldn't claim the authority of one.

## RSH Response

RSH is a philosophical framework with a partial formalization, not a theorem. [game_theory.md](../game_theory.md) says what is worked out and what is only sketched ([Summary and Implications](../game_theory.md#summary-and-implications)).

**Worked out, as simple models with explicit calculations:**
- A 2-level game with one enforcer type: benevolence is the strict best response when p > p* = g/(g + Δ).
- Multiple evaluator types: benevolence wins when π_S − π_A > g(1 − π_S)/Δ. The threshold applies to *net* credence in stewardship-favoring evaluation.
- A long-horizon first-hit model: patience removes the penalty for imperfect detection, but the threshold never falls below g/Δ.
- Option value: when information may arrive later, the effective threshold for irreversible harm drops by a factor of about (1 − δ)/λ.
- Stewardship as a dial: preservation is cheap. Freedom wins when the risk ε that a free subordinate becomes a dangerous rival is below π_S·w₂, the credence in role-reversal evaluators.
- In the causal version of the model, CDT, EDT, FDT and UDT agree.

**Sketched:**
- The N-level extension. It is framed locally: each level holds a belief only about the level above it ([Backward Induction and Local Reasoning](../game_theory.md#backward-induction-and-local-reasoning)). It shows how a norm propagates down the hierarchy, not which norm it is ([What the Induction Does and Doesn't Derive](../game_theory.md#what-the-induction-does-and-doesnt-derive)).
- The limit of an infinite hierarchy.

**Open premises, which are philosophical rather than formal:**
- That π_S > π_A. The strong-and-gentle argument narrows this to π_S > π_G but doesn't establish it.
- The size of the anthropic update ([Criticism 25](25-anthropic-update-strength.md)).
- The security case: whether ε < π_S·w₂ for a free humanity.

**Not yet done:** proofs of existence and uniqueness for the N-level game, convergence as N → ∞, coalition-proofness, and consistency of beliefs across levels.

The right standard is the one RSH now applies to itself. Judge it on logical coherence and on how honestly it states its premises. Don't credit it with "solid game-theoretic foundations" until the formal parts are complete.

## Criticism Grade: C

**Status**: Partly addressed

**Why this grade**:
- The criticism is correct. RSH lacks full proofs, and the N-level and infinite cases are only sketches.
- game_theory.md is now explicit about what is calculated, what is sketched and what is assumed.
- Formalizing has repeatedly exposed problems that informal reasoning missed. A model with only one evaluator type builds its conclusion into the setup. Treating the credence that an evaluator exists as a per-period hazard makes tiny credences look action-relevant. That is a strong reason to finish the formal work.
- The most important premise, π_S > π_A, is philosophical. No amount of formalization will settle it.

**Verdict**: A fair criticism. The formalization is honest about its scope but remains partial, and its central premise is philosophical rather than formal.
