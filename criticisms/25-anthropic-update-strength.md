# Criticism 25: Anthropic Update Strength

## Summary

RSH relies on the "ASI Paradox" to argue that P(enforcement exists) is not negligible, but other cosmological models (grabby aliens, rare Earth, earliness) provide competing explanations. The Bayesian update may be much weaker than RSH claims.

## The Problem

### The ASI Paradox Argument

**RSH claims**:
1. ASI capability is possible (proven by our emergence)
2. Universe is vast and old (billions of galaxies × billions of years)
3. We observe no other ASIs
4. Therefore: Strong evidence for enforcement hierarchy preventing uncontrolled expansion

**RSH conclusion**: P(oversight) > 10%, possibly much higher

### Competing Explanations

**Grabby Aliens Model** (Robin Hanson):
- Expansionist civilizations eventually become detectable
- We don't see them because we're early in cosmic history
- Great Filter is behind us, not enforcement ahead
- Explains silence without enforcement hypothesis

**Rare Earth Hypothesis**:
- Intelligent life is extremely rare
- We're first or among first
- No need for enforcement to explain silence
- Just contingent rarity

**Self-Destruction Hypothesis**:
- Civilizations destroy themselves before becoming detectable
- Nuclear war, bioweapon accidents, grey goo, etc.
- Great Filter is ahead, but not enforced—just natural
- Explains both silence and our existence

**Zoo Hypothesis (Passive)**:
- Advanced civilizations choose non-intervention
- Quarantine for study or ethics
- Doesn't require active enforcement hierarchy
- Compatible with silence

### The Bayesian Competition

Each model can explain the observations:
- **Our existence**: All models allow this
- **Apparent fine-tuning**: Some natural explanations, anthropic selection
- **Great Silence**: All models explain this differently
- **No visible ASIs**: All models accommodate this

**The question**: Does RSH provide a stronger explanation, or are the competing models equally good?

## The Likelihood Ratio Problem

Proper Bayesian updating requires:

```
P(RSH | observations) ∝ P(observations | RSH) × P(RSH)
```

Compared against alternatives:

```
P(Grabby | obs) ∝ P(obs | Grabby) × P(Grabby)
P(Rare Earth | obs) ∝ P(obs | Rare Earth) × P(Rare Earth)
etc.
```

**The problem**: All models have plausible likelihoods. The update strength depends on:
1. Prior probabilities (subjective)
2. Likelihood ratios (debatable)
3. Completeness of alternative models (open-ended)

### Example Calculation (Simplified)

**Observations to explain**:
- O₁: We exist and developed intelligence
- O₂: Universe appears fine-tuned for life
- O₃: Great Silence (no detected alien civilizations)
- O₄: No observed ASI proliferation

**Likelihoods** (illustrative):

| Model | P(O₁,O₂,O₃,O₄ \| Model) | Prior | Posterior |
|-------|-------------------------|-------|-----------|
| RSH | 0.7 | 0.05 | ? |
| Grabby | 0.6 | 0.20 | ? |
| Rare Earth | 0.5 | 0.30 | ? |
| Zoo (passive) | 0.6 | 0.10 | ? |
| Self-destruct | 0.4 | 0.35 | ? |

**Problem**: These numbers are highly uncertain and subjective. Reasonable people can disagree significantly.

### The Anthropic Bias Problem

Some observations are **anthropically selected**:
- We must exist to observe anything (survivor bias)
- Fine-tuning might be anthropic effect, not design
- We can only ask these questions in a universe that permits intelligence

**Implication**: Anthropic selection effects might explain O₁ and O₂ without any special model.

## Illustrative Bayesian Comparison

**IMPORTANT CAVEATS**: The following table uses **subjective, illustrative numbers** to demonstrate Bayesian reasoning structure. These are NOT rigorous calculations—priors and likelihoods are educated guesses to show the methodology. Reasonable people will disagree significantly on specific values.

### Full Bayesian Table

**Observations**: O = {Silence, Fine-tuning, Our emergence, No ASI proliferation}

| Model | P(O \| Model) | Prior P(M) | Posterior P(M \| O) | Notes |
|-------|---------------|-----------|---------------------|-------|
| **RSH** | 0.75 | 0.10 | **0.18** | High likelihood: enforcement explains all observations |
| **Grabby** | 0.45 | 0.25 | 0.27 | Moderate: explains silence via earliness |
| **Rare Earth** | 0.20 | 0.20 | 0.10 | Low: requires extreme fine-tuning coincidence |
| **Zoo (passive)** | 0.55 | 0.15 | 0.20 | Moderate-high: explains non-contact |
| **Self-Destruct** | 0.35 | 0.30 | 0.25 | Moderate-low: doesn't explain our survival so far |

*Correction (October 2026): An earlier version of this table had arithmetic errors. It gave P(O) = 0.4625 and ranked RSH first at 32%. With the same inputs, P(O) = 0.415 and RSH ranks fourth of five at 18%. The figures below are corrected.*

**Calculation method** (Bayes' theorem):
```
P(M | O) = P(O | M) × P(M) / P(O)

Where P(O) = Σ P(O | Mᵢ) × P(Mᵢ) = 0.415
```

**Resulting posteriors** (normalized):
- Grabby: 27%
- Self-Destruct: 25%
- Zoo: 20%
- RSH: 18%
- Rare Earth: 10%

### Sensitivity Analysis

**If we're generous to competitors** (lower RSH likelihood to 0.60, higher Grabby to 0.55):
- RSH: 14%
- Grabby: 32%
- Others: 54% combined

**If we're generous to RSH** (higher RSH to 0.85, every competitor's likelihood 0.10 lower):
- RSH: 25%
- Grabby: 26%
- Others: 49% combined

**Range**: With these inputs, P(RSH | observations) falls between **14% and 25%**. RSH never ranks first, even when the inputs are generous to it.

### The Critical Insight

**But remember**: RSH doesn't need P(RSH) = 50% to succeed.

**RSH only needs**: P(enforcement exists) > p* ≈ 0.05%

Even the **lowest posterior** in this analysis (RSH = 14%) massively exceeds the action-relevance threshold (0.05%).

**Implication**: The Bayesian competition is interesting philosophically, but practically irrelevant to RSH's core claim. Even if RSH is the third or fourth most likely model, it still crosses the threshold for rational hedging by orders of magnitude.

## Is the Update Strong or Weak?

**RSH claims**: Strong update toward P(oversight) > 10%

**Critics argue**:
- Modest update, maybe P(oversight) increases from 1% to 3-5%
- Still below action-relevance threshold
- Other models remain competitive

**Counterpoint from Bayesian analysis above**: Even with conservative assumptions, posterior P(RSH) = 14–25% easily exceeds any plausible action-relevance threshold.

**Key question**: What's the **marginal** evidential value of these observations for RSH specifically?

**Answer from table**: A likelihood ratio of only about 1.5:1 to 3:1 in RSH's favor, depending on assumptions. (An earlier version said 4:1 to 10:1.) That is a modest update.

## Implications

**If update is weak** (say, posterior P(RSH) = 3%):
- Still might cross action-relevance threshold (if p* < 3%)
- But less compelling than RSH suggests
- More dependent on p* calculation than anthropic evidence

**If update is moderate** (say, posterior P(RSH) = 15%):
- Easily crosses action-relevance thresholds
- Anthropic argument does significant work
- RSH is on solid empirical ground

**If update is strong** (say, posterior P(RSH) > 40%):
- RSH becomes highly plausible
- But requires showing other models are much worse fits
- Difficult to establish given model uncertainty

## RSH Response

*Note (October 2026): Several claims below, and in "The Critical Insight" above, compare P(oversight) directly to p*. Under the corrected formalization, the threshold applies to the net credence in stewardship-favoring evaluation (π_S − π_A), not to P(oversight) ([game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)). See the revised grade below.*

### The Conjunction Is Key

The anthropic argument isn't about individual observations but their **conjunction**:

1. **Universe permits intelligence** (fine-tuning)
2. **Intelligence actually emerged** (us)
3. **Despite vast scale and age, cosmos appears empty**
4. **No uncontrolled ASI proliferation observed**

**Each individually** might be explained by various models.

**The conjunction** is harder to explain without some filter/enforcement mechanism.

### Comparison to Alternatives

**Grabby Aliens**:
- ✓ Explains silence (we're early)
- ✗ Doesn't explain why we're "early" specifically
- ✗ Timing seems suspicious (why now, in cosmic history?)
- ? Compatible with RSH as two-tier system (grabby expansion + stewardship hierarchy)

**Rare Earth**:
- ✓ Explains our existence
- ✗ Requires extreme fine-tuning of parameters
- ✗ Doesn't explain anthropic shadow (why we arose exactly when risky)
- ✗ No mechanism ensuring rare intelligence is benevolent

**Self-Destruction**:
- ✓ Explains Great Silence
- ✗ Doesn't explain our survival SO FAR (we've faced many existential risks)
- ✗ Predicts we shouldn't expect to survive much longer (but we're still here)
- ? Consistent with RSH if "self-destruction" is actually enforcer intervention

**Zoo (Passive)**:
- ✓ Explains non-contact
- ✗ Doesn't explain why zoo-keepers themselves are benevolent
- ✗ No explanation for why zoo-keepers don't defect
- ✓ Compatible with RSH (zoo-keeping is a form of stewardship)

### The Conservative Claim

**RSH doesn't need to claim posterior P(RSH) = 50%.**

**RSH only needs**: P(oversight) > p*

From [game_theory.md](../game_theory.md#numerical-examples):
- p* ranges from 0.05% (conservative) to 10⁻⁹% (extreme)
- Even the highest threshold (0.05%) is very low

**Therefore**: Even a **modest** anthropic update (1% → 5%) is sufficient to cross the action-relevance threshold.

### The Bayesian Calculation (More Careful)

Consider **just the observations relevant to oversight**:

**O_key**: "No observed uncontrolled ASI proliferation despite cosmic scale and age"

**Likelihood under models**:
- P(O_key | RSH with enforcement): ~0.95 (high—enforcement would prevent this)
- P(O_key | No enforcement, rare ASI): ~0.5 (depends on how rare)
- P(O_key | No enforcement, common ASI): ~0.01 (would expect to see some)

**If** we have any evidence that ASI is not extremely rare (our own existence suggests it's possible), then:

```
Likelihood ratio = P(O_key | RSH) / P(O_key | No enforcement)
                 ≈ 0.95 / 0.2  (if ASI moderately rare)
                 ≈ 4.75:1 in favor of RSH
```

**Even a modest likelihood ratio of 4:1 can shift probabilities significantly:**
- Prior: P(RSH) = 2%
- Posterior: P(RSH) ≈ 8%
- This crosses the 0.05% threshold by a large margin

### The Asymmetry in Requirements

**Crucially**: RSH doesn't need to win the Bayesian competition outright.

**RSH needs**: P(oversight) > p* ≈ 0.05-10%

**Competing models**: Require P(no oversight) > 90-99.95%

**Implication**: The burden of proof is asymmetric. Enforcement hypothesis doesn't need to be most likely—just non-negligible.

### Multiple Independent Lines of Evidence

The anthropic argument is one of several:

1. **Fermi Paradox / Great Silence**: Some filter exists
2. **Fine-tuning**: Conditions permit intelligence
3. **Our survival so far**: Haven't self-destructed despite risks
4. **Lack of visible ASIs**: No observed runaway superintelligence
5. **Game-theoretic reasoning**: Structure of hierarchy provides independent support

**Combined weight**: Multiple weak-to-moderate lines of evidence can compound to strong overall case.

## Criticism Grade: B

**Status**: Open

**Validity of Criticism**: Strong. Everything else depends on the anthropic update, and the case for a large update is weak. (Revised October 2026; previously graded C+.)

**Why this grade**:
- The illustrative Bayesian table had arithmetic errors (now corrected above). With its own inputs, RSH ranks fourth of five at 18%, not first at 32%, and the likelihood ratio is about 2:1, not 4:1 to 10:1.
- The table also assigns RSH the highest likelihood (0.75) by hand, so the conclusion is built into the inputs. Rare Earth gets a low likelihood for "requiring extreme fine-tuning," which conflates the fine-tuning of physics with the rarity of life. With likelihoods closer together, the posterior mostly reflects the priors.
- The response says grabby aliens "doesn't explain why we're early." But explaining human earliness is the grabby-aliens model's main result.
- The "asymmetry in requirements" argument overstates RSH's position. Competing models don't need to establish P(no oversight) > 99.95%. RSH needs the *net* credence in stewardship-favoring evaluation, π_S − π_A, to clear the threshold ([game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)). Credence in "some filter" or "some oversight" isn't enough on its own.
- The low threshold cuts both ways. And if the net credence is only around 10⁻⁶, clearing a 10⁻⁹ threshold is Pascal's mugging, not a reasonable bet ([game_theory.md](../game_theory.md#pascals-wager-and-pascals-mugging)).
- "Our survival so far" is subject to anthropic selection. The argument that ASIs should already have expanded visibly assumes ASI is common, and that is what's in question.

**What would strengthen RSH**: Present the anthropic argument as one modest line of evidence. Give a range for the net credence rather than a point estimate, and show that the conclusion survives at the low end of that range.

**Verdict**: Together with the evaluator-type balance (Criticisms 7, 17, 21), this is RSH's most important open question. Whether the net credence is in the percent range decides whether RSH is a reasonable bet or a Pascal-style one.
