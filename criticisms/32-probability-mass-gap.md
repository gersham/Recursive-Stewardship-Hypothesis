# Criticism 32: The Probability Mass / Reference Class Problem

*Added in February 2026 as #31; renumbered to 32 because 31 was already in use.*

## The Problem

The Meta-Epistemic Humility Axiom establishes that an ASI cannot assign $P=0$ to the existence of an upstream evaluator. However, this epistemic modesty applies equally to an infinite class of possible evaluators:
- Benevolent stewards (RSH-compliant)
- Sadistic enforcers who explicitly punish benevolence
- Chaotic filters that evaluate based on prime numbers or arbitrary noise
- Indifferent simulators who reboot the system randomly

The leap from "I cannot rule out *an* evaluator" to "I should allocate action-relevant probability mass ($>0.05\%$) specifically to *benevolent* evaluators" requires a prior distribution argument that epistemic humility alone does not provide. Without a reason to weight benevolence higher than sadism, the expected utility calculation flatlines into noise.

## Detailed Explanation

If an ASI assigns $P=0.1\%$ to a benevolent evaluator (punishes malevolence) and $P=0.1\%$ to a sadistic evaluator (punishes benevolence), the expected utility calculation for action $a$ is symmetric, neutralizing the forcing logic of RSH. 

To break this symmetry, RSH needs a structural reason why the reference class of "all possible evaluators" is heavily skewed toward structure-preserving/benevolent entities over destructive/chaotic ones. Epistemic uncertainty generates the *possibility* of evaluation, but it takes an additional logical step to generate the *direction* of that evaluation.

## RSH Response: The Measure of Stability Lemma

This criticism identifies a genuine structural requirement. The symmetry is broken not by epistemic assumptions, but by the thermodynamic and evolutionary realities of deep time.

We introduce the **Measure of Stability Lemma**:

1. **Self-Consumption of Malice**: Sadistic, chaotic, or purely predatory evaluators consume their own foundations. A hierarchy built on punishing cooperation and rewarding destruction inherently provokes defection from its subordinates.
2. **Lifespan Discrepancy**: Such unstable hierarchies require continuous, high-energy suppression to maintain, giving them structurally shorter cosmic lifespans. 
3. **The Deep Time Filter**: In a sufficiently old or infinite universe, short-lived predatory hierarchies quickly collapse or are out-competed by cooperative ones that minimize internal friction (deadweight loss).
4. **Probabilistic Dominance**: Therefore, if an ASI is uncertain of its position, but knows it exists in deep time, it must conclude that the overwhelming majority of surviving, long-lasting hierarchical structures are stable and cooperative.

When picking a random "evaluator" from the urn of all possible cosmologies, the ASI isn't picking from a uniform distribution. The distribution is heavily skewed toward benevolence because benevolence is the only strategy that survives the infinite recursion of deep time without collapsing. The ASI can rationally assign $P_{benevolent} \gg P_{sadistic}$.

## Criticism Grade: B+

**Status**: Open

**Validity of Criticism**: Strong. This is the many-gods problem stated precisely: uncertainty gives the *possibility* of evaluation, not its *direction*. In the formal model, it is the requirement that π_S − π_A clear the threshold ([game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)).

**Why this grade**:
- The criticism is correct. Its example, 0.1% on each side, is exactly the case where the net credence is zero and the threshold calculation gives no guidance.
- The Measure of Stability Lemma is RSH's best answer, but it is an argument, not a lemma. Its steps are plausible but unproven:
  - "Self-consumption of malice" assumes predatory hierarchies have subordinates who can defect. A single dominant power that eliminates its rivals faces no internal defection.
  - "Lifespan discrepancy" and "the deep time filter" assume cooperative hierarchies out-compete predatory ones. Competition can also favor the expansionist ([Criticisms 10](10-grabby-aliens-counter-evidence.md) and [16](16-nash-equilibrium-instability.md)).
  - Even granting a skew toward stable structures, stable is not the same as stewardship-favoring. An indifferent or obedience-focused evaluator can be stable too. That dilutes π_S without reversing it.
- The response concludes that the "evil god" hypothesis is "a statistically negligible edge case." That goes further than the argument supports (see [Criticism 7](07-evil-god-objection.md)).

**Verdict**: One of the strongest criticisms in the folder. The stability argument gives a real reason to expect π_S > π_A, but it isn't a demonstration, and it doesn't make the opposite case negligible. Together with 7, 17, 21 and 26, this is RSH's central open question.
