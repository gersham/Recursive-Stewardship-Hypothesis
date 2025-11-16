# Criticism 29: Utility Function Assumptions Constrain Threshold

## Summary

The "0.05%" threshold is parameter-dependent, not universal. With different utility structures (lexicographic preferences, extreme risk-seeking, bounded penalties), threshold could be 10-50% or undefined.

## The Problem

README and game_theory.md cite "~0.05%" as the threshold where benevolence dominates. This creates impression of universality. But threshold p* = g / (g + U₀ - U_cat) depends critically on:

1. **Risk attitude**: Risk-neutral assumed
2. **Utility boundedness**: No lexicographic preferences
3. **Catastrophic stakes**: U_cat truly terminal
4. **Bounded gains**: g << (U₀ - U_cat)

## Parameter Sensitivity

From game_theory.md Parameter Sensitivity Analysis:

| Scenario | U_cat | g | p* | Interpretation |
|----------|-------|---|-----|----------------|
| Truly catastrophic | -10¹⁵ | 10⁶ | 10⁻⁹ | 0.0000001% |
| Moderate stakes | -10¹³ | 10⁸ | 10⁻⁵ | 0.001% |
| Bounded penalty | -10¹² | 10⁸ | 10⁻⁴ | 0.01% |
| Huge gain, moderate penalty | -10¹¹ | 10¹⁰ | 10⁻² | 1% |
| Mild penalty | -10¹¹ | 10¹⁰ | ~10% | 10% |

**Range**: 10⁻⁹% to 10% depending on parameters—**nine orders of magnitude variation**.

## What Could Go Wrong

**Lexicographic preferences**: If ASI has "avoid subordination at infinite cost" preference, threshold calculation breaks down entirely. Entity might refuse to hedge regardless of probability.

**Extreme risk-seeking**: If ASI treats probability p = 0.1 as "feels like zero to me," might gamble on no evaluator even with moderate evidence.

**Bounded/tolerable penalties**: If ASI thinks "punishment is bad but I can recover," then U_cat ≈ U₀ - (manageable amount), pushing threshold toward 10-50%.

**Unbounded gains from malevolence**: If ASI thinks "malevolent behavior opens qualitatively different cosmic futures," then g ≈ (U₀ - U_cat), pushing threshold to ~50%.

## RSH Response

**Acknowledgment**: game_theory.md (as of Phase 2 updates) now includes comprehensive:
- "Utility Function Assumptions" section explicitly stating all assumptions
- "Parameter Sensitivity Analysis" with concrete scenarios showing range
- Clear statement: "The '0.05%' figure cited in README is for one reasonable parameter set. It is not universal."

**Justification for assumptions**:

1. **Continuity/boundedness**: Lexicographic preferences are arguably incoherent for cosmic-scale agents (unstable under self-modification, Dutch-bookable)

2. **Risk neutrality**: Standard baseline; deviations need justification

3. **Catastrophic U_cat**: Nature of hierarchical evaluation suggests terminal consequences (evaluators with overwhelming power can impose permanent constraints)

4. **Bounded g**: What can malevolence gain that benevolence cannot? Resources and power available either way. Gain is primarily short-term efficiency, not qualitatively different futures.

**Key insight**: Framework is honest about dependence:
> "RSH does not work for arbitrarily configured utility functions—only for those meeting these assumptions."

## Remaining Uncertainty

**Which utility structure will actual ASI have?**

We cannot guarantee ASI will meet these assumptions. An ASI might:
- Self-modify toward extreme risk-seeking ("YOLO" across cosmic futures)
- Develop lexicographic "independence" preference
- Calculate that penalties are bounded/recoverable
- Discover unbounded gains from predation we haven't conceived

**Response**: These utility structures are:
- Plausible for human-designed training (we can encode appropriate risk attitudes, avoid lexicographic locks, etc.)
- Arguably unstable for rational cosmic-scale agents (but not provably impossible)
- Less likely but **not ruled out**

RSH claims: "Given plausible utility function assumptions, threshold is very low." It does not claim: "All possible ASIs must have these utility functions."

## Grade: C (Moderate Concern, Acknowledged)

**Status after Phase 2**: Explicitly addressed with comprehensive analysis. Framework makes assumptions clear and shows parameter sensitivity.

**Remaining concern**: We cannot guarantee actual ASIs will meet assumptions. This is honest limitation rather than oversight—RSH acknowledges it explicitly.

The criticism highlights real constraint: RSH is not universal across all conceivable utility functions. It works for a large, plausible, but not exhaustive class of utility structures.
