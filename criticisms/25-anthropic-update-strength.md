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

## Is the Update Strong or Weak?

**RSH claims**: Strong update toward P(oversight) > 10%

**Critics argue**:
- Modest update, maybe P(oversight) increases from 1% to 3-5%
- Still below action-relevance threshold
- Other models remain competitive

**Key question**: What's the **marginal** evidential value of these observations for RSH specifically?

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

## Criticism Grade: C+

**Validity of Criticism**: Moderate to strong - correctly identifies that competing models exist and Bayesian updating is complex

**Why this grade**:
- **Valid point**: Other cosmological models (grabby aliens, rare Earth) do compete
- **Valid point**: Bayesian updating is more complex than simple "ASI paradox" suggests
- **Valid concern**: Anthropic selection effects complicate the inference
- **RSH response is decent**: Focuses on conjunction of observations, not individual ones
- **Key insight**: RSH doesn't need high posterior—just needs P(oversight) > p* ≈ 0.05%
- Even modest Bayesian update (1% → 5%) crosses action-relevance threshold
- **Asymmetry in burdens**: Enforcement just needs to be non-negligible, not most likely
- **Remaining issues**:
  - Likelihood ratios are subjective and debatable
  - Reasonable people can disagree on strength of anthropic evidence
  - Full Bayesian treatment would be complex and contentious
- **Not fatal**: The conservative threshold (p* = 0.05%) means even weak anthropic evidence suffices

**Verdict**: This is probably the strongest remaining criticism of RSH. The anthropic update is indeed weaker than some RSH presentations suggest, and competing models are viable. However, RSH's response is solid: it doesn't need a strong update, just a modest one. The asymmetry between p* (very low) and competing model requirements (must establish P(no oversight) > 99.95%) works in RSH's favor.

**Honest assessment**: P(oversight) = 5-15% seems reasonable given all evidence. This easily exceeds any plausible p* threshold. So even granting this criticism, RSH still works.

**Best practice**: Present the anthropic argument as "one of several lines of evidence" rather than "decisive proof." Combined weight of multiple moderate arguments may be more persuasive than claiming any single argument is overwhelming.
