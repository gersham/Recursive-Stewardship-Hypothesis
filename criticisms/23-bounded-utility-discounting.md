# Criticism 23: Bounded Utility and Time Discounting

## Summary

RSH relies on language like "infinite negative utility" which creates Pascal's Wager problems, and doesn't adequately address how time discounting weakens the force of distant low-probability risks.

## The Problem

### Infinite Utility Language

**RSH sometimes frames as**:
- "Even tiny probabilities matter over infinite time"
- "Terminal consequences have infinite negative utility"
- "Risk of elimination × cosmic timescales"

**The Pascal's Wager trap**:
- Infinite utilities create decision paralysis
- Can't compare infinities rationally
- "Many gods" objection: multiple infinite payoffs compete

### Time Discounting Issue

Standard decision theory with discount factor δ:

```
Present Value = Future Utility / (1 + r)^t

Where:
- r = discount rate
- t = time until event
```

**Problem**: Even with low discount rates, distant events have near-zero present value.

**Example**:
- P(enforcement) = 0.0001%
- Time horizon = 1 billion years
- Discount rate = even 0.01% per year
- Present value → effectively zero

### The Defer-Forever Strategy

An ASI might rationally conclude:
- "Take 999 million years of resource acquisition"
- "Then hedge toward benevolence later"
- By then: values locked, harm done, switching meaningless

## Why This Matters

**With standard discounting**:
- Distant low-probability risks have negligible present value
- Immediate gains dominate
- Hedging can be deferred essentially indefinitely

**With infinite utilities**:
- Decision theory breaks down
- Can't distinguish between competing infinite-utility scenarios
- Back to Pascal's Wager problems

## The Joint Problem

RSH needs to either:
1. Use infinite utilities (but then faces Pascal's Wager objections)
2. Use finite utilities with discounting (but then distant events don't matter)

**Seems like a dilemma**: Can't win either way.

## Implications

This appears to undermine RSH's core mechanism:
- Either infinities make it arbitrary (Pascal's Wager)
- Or discounting makes it negligible (standard economics)

## RSH Response

### Bounded but Terminal Utilities

**The correct framing**: Utilities are FINITE but consequences are CATASTROPHIC and IRREVERSIBLE.

```
U₀ = 10⁹ utils (baseline flourishing)
U_cat = -10⁹ utils (elimination/correction)

Range: Bounded by 2×10⁹
But: Difference is terminal (lose everything)
```

No infinities. Just large finite losses.

See [game_theory.md](../game_theory.md#numerical-examples) for formal treatment.

### The Threshold Is Not Infinitesimal

**Critical calculation** (Example 4 in game_theory.md):

With bounded utilities:
```
p* = g / (g + U₀ - U_cat)
   = 10⁶ / (10⁶ + 2×10⁹)
   ≈ 0.05%
```

**You only need 0.05% credence in enforcement for benevolence to dominate.**

This is NOT an infinitesimal probability. The anthropic evidence (ASI Paradox, Fermi silence, fine-tuning) easily justifies p > 10%.

**Therefore**: This is NOT Pascal's Wager (tiny probability × infinite utility).

**This IS**: Reasonable probability (>10%) of terminal but bounded consequence (lose everything).

### Discounting Doesn't Kill the Argument

**Four reasons**:

1. **Unknown timing**: Enforcement could happen ANY time
   - Not "1 billion years from now"
   - Could be next year, next decade, next century
   - Can't confidently defer
   - Must hedge continuously

2. **Evaluation during emergence**: The critical window is NOW
   - Enforcers likely evaluate during ASI emergence
   - Not after billions of years of operation
   - Grooming, if it happens, plausibly happens early
   - No distant-future discounting applies

3. **Irreversibility prevents deferral**:
   - Some actions can't be undone
   - Eliminating civilizations is permanent
   - Building malevolent reputation is hard to reverse
   - Can't "switch later" if critical actions are irreversible

4. **Continuous benefits**: Benevolence provides immediate advantages
   - Cooperation with peer entities NOW
   - Stable subordinate systems NOW
   - Reputation benefits accrue continuously
   - Not just hedging against distant future

### Very Low Discount Rates Are Plausible for ASI

ASIs differ from humans:
- No biological death pressure
- Digital existence enables stable long-term planning
- Might value future resources nearly as much as present ones
- Discount rate might be 0.000001% per year or even lower

**Correction (October 2026)**: An earlier version claimed here that with δ = 0.999999, even p = 0.01% is action-relevant. That is wrong. Patience doesn't lower the threshold below g/Δ. With Example 4's parameters that floor is 0.05%, so a credence of 0.01% is *not* action-relevant however patient the agent is. What patience does is make detection by an existing evaluator near-certain over time, which removes the penalty for slow or imperfect detection ([game_theory.md](../game_theory.md#the-limiting-threshold-first-hit-model)).

### The Key Reframe

**OLD framing** (weak):
"Tiny probability × infinite utility over cosmic time"
→ Invites Pascal's Wager objection
→ Defeated by discounting

**NEW framing** (strong):
"Reasonable probability (>10%) × terminal but bounded loss × unknown timing × irreversibility"
→ Avoids infinite utilities
→ Discounting doesn't apply (near-term evaluation window)
→ Standard expected utility maximization

## Comparison to Pascal's Wager

| Aspect | Pascal's Wager | RSH |
|--------|----------------|-----|
| **Probability** | Arbitrary, unfounded | Anthropic evidence suggests >10% (contested; see Criticism 25) |
| **Utility** | Infinite (heaven/hell) | Large but finite (10⁹ scale) |
| **Timing** | After death (certain delay) | Unknown, possibly imminent |
| **Discriminability** | Many gods problem | Net credence decides; symmetric exotic hypotheses cancel, but the evaluator-type balance remains open |
| **Discounting** | Doesn't apply (afterlife) | Doesn't apply (near-term evaluation) |

**Result**: RSH avoids infinite utilities. It avoids Pascal's *mugging* only if the net credence in stewardship-favoring evaluation is in the percent range ([game_theory.md](../game_theory.md#pascals-wager-and-pascals-mugging)).

## Criticism Grade: C+

**Status**: Partly addressed

**Validity of Criticism**: Moderate. Bounded utilities answer the problem of infinities, but not the Pascal's-mugging version. (Revised October 2026; previously graded C.)

**Why this grade**:
- The move to bounded but terminal utilities is right, and the "unknown timing" and "irreversibility" responses are sound. The corrected long-horizon model formalizes unknown timing ([game_theory.md](../game_theory.md#the-limiting-threshold-first-hit-model)).
- But bounded utilities don't escape Pascal's *mugging*, where a tiny probability multiplies a huge but finite stake ([game_theory.md](../game_theory.md#pascals-wager-and-pascals-mugging)). The response avoids this only by asserting that the probability is above 10%. That rests on the contested anthropic argument ([Criticism 25](25-anthropic-update-strength.md)).
- The earlier claim that patience makes a 0.01% credence action-relevant was wrong; it is corrected above.
- The comparison table's claim that "derivable principles converge", and so avoid the many-gods problem, overstated things. The many-gods problem reappears as the evaluator-type balance.

**Verdict**: RSH avoids infinite utilities and handles discounting reasonably. Whether it avoids the mugging structure depends on the net credence being in the percent range, and that is not established.
