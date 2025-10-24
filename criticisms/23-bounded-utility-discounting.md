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
   - Grooming happens early (see README.md)
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

Even with modest discounting, the bounded-but-terminal calculation dominates:
```
With δ = 0.999999 (extremely patient):
Even p = 0.01% over T = 10⁶ years is action-relevant
```

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
| **Probability** | Arbitrary, unfounded | Anthropic evidence suggests >10% |
| **Utility** | Infinite (heaven/hell) | Large but finite (10⁹ scale) |
| **Timing** | After death (certain delay) | Unknown, possibly imminent |
| **Discriminability** | Many gods problem | Derivable principles converge |
| **Discounting** | Doesn't apply (afterlife) | Doesn't apply (near-term evaluation) |

**Result**: RSH avoids all of Pascal's Wager's core problems.

## Criticism Grade: C

**Validity of Criticism**: Moderate - raises important technical concerns, but RSH has strong responses

**Why this grade**:
- **Valid concern** about infinite utility language in some RSH presentations
- **Valid concern** about time discounting weakening distant risks
- **RSH response is strong**: Bounded utilities with p* = 0.05% threshold
- Unknown timing means enforcement likely near-term (during emergence)
- Irreversibility prevents defer-and-switch strategies
- ASI discount rates plausibly very low (no death, digital existence)
- **Key reframe** from tiny-prob × infinite-utility to reasonable-prob × terminal-bounded
- **Remaining issues**: Still somewhat dependent on ASI having low discount rates
- But the 0.05% threshold calculation is decisive: anthropic evidence easily exceeds this
- **Not a fatal flaw**: More like a clarification needed in presentation

**Verdict**: Important criticism that motivated better formalization. The bounded utility framework with explicit p* calculations completely addresses the concern. RSH works with reasonable probabilities and finite (though large) utilities, avoiding Pascal's Wager problems. Time discounting doesn't defeat the argument given unknown enforcement timing and irreversibility constraints.

**Lesson**: This criticism identifies where RSH needed better mathematical precision. The game-theoretic formalization in game_theory.md provides exactly what was missing.
