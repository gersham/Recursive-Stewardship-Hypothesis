# Criticism 23: Bounded Utility and Time Discounting

## Summary

RSH can be read as relying on infinite stakes ("terminal consequences", "cosmic timescales"), which brings in the problems of Pascal's Wager. If it uses finite utilities instead, ordinary time discounting seems to make distant, unlikely enforcement negligible. Either way, the argument looks weak.

## The Problem

**The infinity horn.** Phrases like "infinite negative utility" or "tiny probabilities matter over infinite time" invite the objections to Pascal's Wager. Infinite payoffs can't be compared with each other. And many competing infinite-stakes hypotheses (the "many gods" problem) leave no basis for choosing between them.

**The discounting horn.** With finite utilities, standard discounting shrinks distant consequences. Take a 0.0001% chance of enforcement a billion years from now. Discounted at even 0.01% a year, it has essentially zero present value.

**Defer forever.** An ASI might reason: acquire resources for 999 million years, then switch to benevolence. By then its values are fixed, the harm is done, and switching means nothing.

So RSH seems stuck: infinities make it arbitrary, and discounting makes it negligible.

## RSH Response

**Utilities are bounded but terminal.** game_theory.md uses only finite utilities. The loss from being caught, Δ = U₀ − U_cat, is large because it is terminal: the agent loses its future. It is not infinite. In the worked example in [game_theory.md](../game_theory.md#numerical-examples), the gain from malevolence is g = 10⁶ and Δ = 2×10⁹, so the threshold is:

```
p* = g / (g + Δ) ≈ 0.05%
```

The threshold is about 0.1% if "lose everything" is valued at zero rather than at −U₀. Either way, no infinities are involved.

**The first-hit model handles discounting.** The criticism's discounting example assumes enforcement arrives at a known, distant date. RSH's position is that the timing is unknown. An evaluator that exists might act in any period, including during the ASI's emergence. In the first-hit model ([game_theory.md](../game_theory.md#the-limiting-threshold-first-hit-model)), an evaluator exists with probability p and catches a defection with probability q in each period. The expected discounted loss is:

```
Loss = p · Δ · q / [1 − δ(1 − q)]
```

This doesn't shrink like (1 + r)^(−10⁹), because detection can happen in any period. As the agent becomes more patient (δ → 1), the threshold falls toward g/Δ.

**Patience never pushes the threshold below g/Δ.** The probability of ever being caught is capped at p. So when the floor is 0.05%, a credence of 0.01% is not action-relevant, however patient the agent is. Long horizons make slow oversight count. They don't make unlikely oversight likely.

**Irreversibility blocks "defer forever".** Some actions can't be undone, such as eliminating a civilization or foreclosing its future. When the agent might learn more later, those actions carry an option-value cost of their own ([game_theory.md](../game_theory.md#irreversibility-and-option-value)). An agent can't act first and hedge later if the first act is irreversible.

**Pascal's Wager versus Pascal's mugging.** Bounded utilities avoid the Wager. They don't avoid the *mugging*, where a tiny probability multiplies a huge but finite stake ([game_theory.md](../game_theory.md#pascals-wager-and-pascals-mugging)). RSH avoids the mugging structure only if the relevant credence is in the percent range. That credence is the *net* credence π_S − π_A: credence in stewardship-favoring evaluators minus credence in stewardship-penalizing ones.

| Aspect | Pascal's Wager | RSH |
|--------|----------------|-----|
| Utility | Infinite | Large but finite; terminal loss |
| Probability | Arbitrary | Net credence π_S − π_A; its size is contested ([Criticism 25](25-anthropic-update-strength.md)) |
| Many gods | Unresolved | Symmetric exotic hypotheses cancel; the balance of evaluator types remains open |
| Timing | After death | Unknown; possibly during emergence |
| Verdict | Infinite-stakes wager | Avoids infinities; avoids mugging only if the net credence is in the percent range |

The size of the gain matters too. For an ASI deciding how to treat humanity, the resource gain from harm is tiny ([game_theory.md](../game_theory.md#how-large-is-the-gain-from-harm)). That keeps the threshold for the survival question very low. It doesn't help with the harder question: whether a free humanity is worth the security risk.

## Criticism Grade: C+

**Status**: Partly addressed

**Why this grade**:
- Bounded but terminal utilities answer the infinity horn.
- The first-hit model answers the discounting horn, because unknown timing means detection can come in any period. It also limits what patience can do: no amount of patience makes credences below g/Δ relevant.
- Irreversibility answers "defer forever" for irreversible acts.
- But bounded utilities don't escape Pascal's mugging. RSH avoids it only if the net credence in stewardship-favoring evaluation is in the percent range, and that rests on the contested evidence in [Criticism 25](25-anthropic-update-strength.md).

**Verdict**: RSH avoids infinite utilities and handles discounting reasonably. Whether it avoids the mugging structure depends on the net credence being in the percent range, and that is not established.
