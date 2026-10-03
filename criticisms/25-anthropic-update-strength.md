# Criticism 25: Anthropic Update Strength

## Summary

RSH treats cosmic silence, together with our own existence, as evidence for oversight. If ASI is possible and the universe is old and vast, why don't we see any? But several other models explain the same observations without enforcement. Done carefully, the comparison gives only a modest update toward oversight.

## The Problem

**The argument for an update.** ASI appears to be possible, the universe is vast and old, and we see no other ASIs. RSH reads this as evidence that something keeps uncontrolled expansion in check.

**Competing explanations.** Each of these accounts for the same observations without enforcement:
- **Grabby aliens** (Hanson et al. 2021): Expanding civilizations fill the volume they reach and prevent new civilizations from arising there. That is why we find ourselves early, and why we see no one. Explaining our earliness is the model's main result.
- **Rare Earth**: Intelligent life is very rare, and we are among the first.
- **Self-destruction**: Civilizations destroy themselves before they become visible.
- **Passive zoo**: Advanced civilizations choose not to interfere, without any enforcement hierarchy.

**Anthropic selection.** Some observations are guaranteed by the mere fact that we are here to make them. We could only be asking this question in a universe that permits intelligence, and in a history where we survived. So "fine-tuning" and "our survival so far" are weak evidence for any particular model.

**The likelihood problem.** A Bayesian comparison depends on priors and likelihoods that are largely subjective. It also depends on whether the list of alternatives is complete.

## An Illustrative Bayesian Comparison

The numbers below are subjective and illustrative. They show the structure of the comparison; they are not a measurement.

The observations are O = {silence, apparent fine-tuning, our emergence, no visible ASI proliferation}.

| Model | P(O \| Model) | Prior | Posterior |
|-------|---------------|-------|-----------|
| Grabby | 0.45 | 0.25 | 0.27 |
| Self-Destruct | 0.35 | 0.30 | 0.25 |
| Zoo (passive) | 0.55 | 0.15 | 0.20 |
| RSH | 0.75 | 0.10 | 0.18 |
| Rare Earth | 0.20 | 0.20 | 0.10 |

```
P(M | O) = P(O | M) × P(M) / P(O)
P(O) = Σ P(O | Mᵢ) × P(Mᵢ) = 0.415
```

RSH is given the highest likelihood (0.75) by hand, and it still ranks fourth of five.

**Sensitivity:**
- Generous to competitors (RSH likelihood 0.60, Grabby 0.55): RSH 14%, Grabby 32%.
- Generous to RSH (RSH 0.85, every competitor 0.10 lower): RSH 25%, Grabby 26%.

So with these inputs, P(RSH | O) falls between 14% and 25%, and RSH never ranks first. The likelihood ratio in RSH's favor ranges from about 1.5:1 to 3:1, comparing RSH with the other models combined. At the central inputs it is about 2:1. That is a modest update.

## RSH Response

**The quantity that matters is net credence, not P(oversight).** RSH's threshold applies to π_S − π_A: credence in evaluators that reward stewardship, minus credence in evaluators that punish it ([game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)). Evidence for "some filter" or "some oversight" doesn't settle that by itself. An enforcement hierarchy that rewarded ruthlessness would explain the silence just as well.

**The README doesn't rely on a large update.** It treats the anthropic evidence as one modest line of evidence (about 2:1), not as grounds for a large estimate of P(evaluation).

**What a modest update still supports.** RSH's case has two layers:
- **Survival.** For an ASI deciding how to treat humanity, the resource gain from harm is tiny: Earth is about one part in 10¹⁶ of the galaxy's stellar mass ([game_theory.md](../game_theory.md#how-large-is-the-gain-from-harm)). So the threshold for preserving weaker agents is extremely low, and a small positive net credence clears it. Option value supports this layer even without any evaluator ([game_theory.md](../game_theory.md#irreversibility-and-option-value)).
- **Freedom.** Leaving a weaker agent free has a security cost, because it might become a rival. Freedom wins only when the credence in role-reversal evaluators exceeds the risk ε of that happening ([game_theory.md](../game_theory.md#stewardship-as-a-dial)). That layer needs substantial credence, and a modest anthropic update doesn't supply it by itself.

**The low threshold cuts both ways.** If the net credence is only around 10⁻⁶, clearing a 10⁻⁹ threshold is Pascal's mugging, not a reasonable bet ([game_theory.md](../game_theory.md#pascals-wager-and-pascals-mugging)). The survival layer is less exposed to this, because its cost is negligible and option value supports it without any evaluator.

**Where this leaves RSH.** Treat the anthropic argument as one modest line of evidence. Give a range for the net credence rather than a point estimate, and check whether the conclusion survives at the low end. For survival, it does. For freedom, it depends on role-reversal evaluators.

## Criticism Grade: B

**Status**: Open

**Why this grade**:
- The competing models explain the silence about as well as enforcement does. Using RSH's own inputs, the comparison ranks RSH fourth of five, with a likelihood ratio of about 2:1.
- The inputs favor RSH by hand (its 0.75 likelihood). Rare Earth's low likelihood conflates the fine-tuning of physics with the rarity of life. With the likelihoods closer together, the posterior mostly reflects the priors.
- Evidence for "some oversight" isn't evidence for *stewardship-favoring* oversight. What matters is the net credence π_S − π_A, and the silence says little about its sign.
- "Our survival so far" is subject to anthropic selection. The claim that ASIs should already be visible assumes ASI is common, which is the point in question.

**Verdict**: Together with the balance of evaluator types (Criticisms 7, 17, 21), this is RSH's most important open question. A modest update is enough for the survival layer, where the gain from harm is tiny. It isn't enough on its own for the freedom layer.
