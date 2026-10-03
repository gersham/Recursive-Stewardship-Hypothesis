# Criticism 29: Utility Function Assumptions Constrain the Threshold

## Summary

RSH's headline threshold (about 0.05–0.1% for one parameter set) is not a universal number. It depends on what the ASI's utility function looks like. Change the assumptions about penalties, gains or attitudes to risk, and the threshold can rise to 10–50% or stop being defined at all.

## The Problem

The threshold p* = g / (g + U₀ − U_cat) depends on the ratio between what harm gains (g) and what being caught costs (Δ = U₀ − U_cat). Across the scenarios in game_theory.md, it runs from about 10⁻⁹ to about 10% ([Parameter Sensitivity Analysis](../game_theory.md#parameter-sensitivity-analysis)). That is eight orders of magnitude, and a single figure like "0.05%" hides it.

The low end also rests on assumptions about the agent's preferences, and each can fail:
- **Lexicographic preferences.** An agent that puts infinite weight on, say, never being subordinate has no threshold. It may refuse to hedge at any probability.
- **Departures from expected utility.** An agent that weighs best cases heavily may gamble on "no evaluator" even at moderate credence.
- **Bounded, recoverable penalties.** If being caught is bad but survivable, Δ is small and the threshold can reach 10–50%.
- **Large gains from harm.** If malevolence opens futures that restraint doesn't, g approaches Δ and the threshold approaches 50%. In the extreme, g has no upper bound at all.

Nothing guarantees that a real ASI will have the utility function the calculation assumes. Training or self-modification could produce any of the cases above.

## RSH Response

RSH accepts the point. It claims to work for a large, plausible class of utility functions, not for every one. game_theory.md states the assumptions explicitly ([Utility Function Assumptions](../game_theory.md#utility-function-assumptions)):

1. **Continuity and boundedness.** No lexicographic preferences. These violate the continuity axiom, so no real-valued utility function can represent them, which makes them hard to square with expected-utility reasoning. They are not, however, vulnerable to Dutch books.
2. **Expected-utility maximization.** Payoffs are in utils, so any risk aversion over resources is already built into them. Large departures from expected utility need their own justification.
3. **A near-terminal penalty.** Being caught means elimination, permanent constraint, or loss of the agent's goals. [Criticism 33](33-proportionate-enforcers.md) presses on this.
4. **Bounded gain.** Harm gains little that restraint can't.
5. **The Bekenstein boundary condition.** Physical limits on computation and energy bound the gain from malevolence. If predation could unlock effectively unbounded utility, the calculation fails. Bounded gain is necessary for RSH, not sufficient.
6. **The evaluator-type balance favors stewardship.** Every threshold applies to the net credence π_S − π_A, not to P(evaluator exists) ([Evaluator Types](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)). This is the least secure of the six.

Two results in game_theory.md make the dependence less severe than the range suggests:
- **The resource gain from harming humanity is tiny.** Earth is about one part in 10¹⁶ of the galaxy's stellar mass ([How Large Is the Gain from Harm?](../game_theory.md#how-large-is-the-gain-from-harm)). That keeps g/Δ small even when Δ is modest.
- **The large potential gain is security, not resources.** Removing a potential rival can be worth a lot, and that case is handled separately ([Stewardship as a Dial](../game_theory.md#stewardship-as-a-dial)).

So RSH's claim is conditional: given these assumptions, the threshold is low. It does not claim every possible ASI meets them.

## Criticism Grade: C

**Status**: Acknowledged

**Why this grade**:
- The criticism is correct. The threshold depends on the parameters, and "0.05%" is one point in a wide range.
- RSH responds by stating its assumptions rather than removing them. That is honest, but it doesn't make an actual ASI satisfy them.
- The small resource gain from harming humanity narrows the problem. For harm motivated by resources, the threshold stays low across a wide range of penalties.
- What remains open is the security case, and Assumption 6, which carries most of the weight.

**Verdict**: A fair criticism, openly acknowledged. RSH works for a large, plausible class of utility functions, not all of them. Its most fragile assumption is the evaluator-type balance, not the shape of the utility function.
