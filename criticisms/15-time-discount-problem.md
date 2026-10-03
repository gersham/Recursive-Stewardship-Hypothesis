# Criticism 15: The Time-Discount Problem

## Summary

Rational agents discount the future. If enforcement is a distant, low-probability event, its present value is close to zero. An ASI could then exploit now and put off any hedging indefinitely. RSH seems to need near-zero discounting, which looks irrational.

## The Problem

Standard decision theory discounts future outcomes:

```
PV = Expected Value / (1 + r)^t
```

Take a 0.0001% chance of elimination a billion years from now. Even at a discount rate of 0.001% per year, its present value is negligible.

Agents have good reasons to discount:
- Uncertainty compounds over time, so more can change.
- Resources now are worth more than resources later.
- Predictions about the distant future are unreliable.

This suggests a "defer forever" strategy: maximize resources for 999,999,999 years, then turn benevolent at the end. A related worry is that committing to benevolence now forecloses better strategies that new information might reveal.

On this view, RSH works only if the agent treats year one and year one billion as nearly equivalent. That is implausibly close to zero discounting.

## RSH Response

**Timing is unknown.** The criticism treats enforcement as a single event at a fixed distant date. If an evaluator exists, it could detect defection in any period: next year, or in a million years. The first-hit model in [game_theory.md](../game_theory.md#the-limiting-threshold-first-hit-model) captures this. Let p be the credence that an evaluator exists, q its per-period chance of detecting defection, δ the discount factor, and Δ the loss from being caught. The expected discounted loss from defecting is:

```
Loss = p · Δ · q / [1 − δ(1−q)]
```

This doesn't shrink like (1+r)^(−10⁹), because detection can come early. Benevolence dominates when the loss exceeds the one-time gain g:

```
p > g·[1 − δ(1−q)] / (q·Δ)
```

**What patience does, and doesn't do.**
- For a patient agent (δ near 1), the threshold approaches g/Δ, the threshold with perfect detection. Given enough time, an evaluator that exists will almost surely catch a defector. So slow or imperfect oversight still counts.
- For a myopic agent facing a slow evaluator, the threshold is far higher. In the numerical example in game_theory.md, it is about 100,000 times higher. So RSH does depend on the agent valuing its long-term future. RSH assumes this; it doesn't prove it.
- Patience never lowers the threshold below g/Δ, because the total chance of ever being caught is capped at p. The criticism's example credence of 0.0001% is action-relevant only if Δ/g exceeds about a million.

**The size of the gain helps here.** For harm done to gain resources, g is very small: Earth is about one part in 10¹⁶ of the galaxy's stellar mass ([game_theory.md](../game_theory.md#how-large-is-the-gain-from-harm)). For an agent that values its long-term future, the stakes ratio can plausibly be that large. For harm done for security, such as removing a potential rival, g may be large, and this response is weaker.

**Defer-forever fails for irreversible acts.** "Exploit now, hedge later" assumes the exploitation can be undone. Destroying a civilization can't be. Under uncertainty, with the possibility of learning more later, irreversible actions carry an option-value cost ([game_theory.md](../game_theory.md#irreversibility-and-option-value)). Restraint keeps the choice open; destruction closes it. That answers the path-dependency worry as well: the action that keeps future options open is restraint, not exploitation.

Benevolence may also bring present benefits, such as cooperation with peers and a reputation for trustworthiness. These are plausible but speculative, and the argument doesn't depend on them.

## Criticism Grade: C

**Status**: Partly addressed

**Why this grade**:
- The criticism is right that a single penalty at a fixed distant date would be discounted to nothing.
- Unknown timing is the correct answer, and the first-hit model formalizes it: detection can come in any period, so the expected loss doesn't decay away.
- The model also bounds RSH. No amount of patience makes a credence below g/Δ relevant.
- Against slow evaluators, discounting still matters. RSH needs an agent that values its long-term future.
- The defer-forever strategy fails for irreversible acts, by option value.

**Verdict**: Discounting doesn't defeat RSH, because evaluation can come at any time. It does set a floor. Patience can't turn a very small credence into a reason to hedge unless the stakes ratio is enormous.
