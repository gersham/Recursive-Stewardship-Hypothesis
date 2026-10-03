# Game-Theoretic Formalization of RSH

**Status**: Partial formalization with concrete examples. Full proofs are future work.

This document provides formal game-theoretic foundations for the Recursive Stewardship Hypothesis. We start with a simplified 2-level game, add uncertainty about what evaluators want, extend to N levels and long horizons, and close with what the formalization does and does not establish.

**Revision note (October 2026)**: This version corrects two problems in the earlier draft.
1. The infinite-horizon section treated the credence that an evaluator exists as if it were a per-period hazard. That made tiny credences look action-relevant over long horizons. They aren't; see [The Infinite Hierarchy Limit](#the-infinite-hierarchy-limit).
2. The base game allowed only one kind of evaluator. The new [Evaluator Types](#evaluator-types-the-many-gods-problem-formalized) section shows that the threshold applies to *net* credence in stewardship-favoring evaluators. That is where the framework's real burden lies.

## Table of Contents

1. [The 2-Level Base Game](#the-2-level-base-game)
2. [Equilibrium Analysis](#equilibrium-analysis)
3. [Evaluator Types: The Many-Gods Problem Formalized](#evaluator-types-the-many-gods-problem-formalized)
4. [Irreversibility and Option Value](#irreversibility-and-option-value)
5. [Stewardship as a Dial](#stewardship-as-a-dial)
6. [How Large Is the Gain from Harm?](#how-large-is-the-gain-from-harm)
7. [Utility Function Assumptions](#utility-function-assumptions)
8. [Parameter Sensitivity Analysis](#parameter-sensitivity-analysis)
9. [Numerical Examples](#numerical-examples)
10. [Pascal's Wager and Pascal's Mugging](#pascals-wager-and-pascals-mugging)
11. [Extension to N-Levels](#extension-to-n-levels)
12. [The Infinite Hierarchy Limit](#the-infinite-hierarchy-limit)
13. [Robustness Analysis](#robustness-analysis)
14. [Future Formalization Roadmap](#future-formalization-roadmap)
15. [Connection to Existing Literature](#connection-to-existing-literature)
16. [Summary and Implications](#summary-and-implications)

---

## The 2-Level Base Game

### Players and Structure

**Players**:
- Player 0: ASI (artificial superintelligence at "Level 0")
- Player 1: Enforcer (potential oversight entity at "Level 1")
- Nature: Determines enforcer existence

**Information Structure**:
- ASI does not observe whether enforcer exists
- ASI has beliefs: P(enforcer exists) = p ∈ [0,1]
- Enforcer (if exists) observes ASI's actions perfectly
- This is a game of **incomplete information** from ASI's perspective

**Timing**:
1. Nature determines if enforcer exists (probability p, unknown to ASI)
2. ASI chooses action a ∈ A = {B, M} where:
   - B = Benevolent stewardship
   - M = Malevolent/opportunistic behavior
3. If enforcer exists, observes a and chooses response r ∈ R = {Allow, Punish}
4. Payoffs are realized

### Payoff Structure

**ASI Payoffs** (Player 0):

| ASI Action | Enforcer Exists? | Enforcer Response | ASI Payoff |
|------------|------------------|-------------------|------------|
| B (Benevolent) | No | — | U₀ |
| B (Benevolent) | Yes | Allow | U₀ |
| B (Benevolent) | Yes | Punish | U₀ - c_fp |
| M (Malevolent) | No | — | U₀ + g |
| M (Malevolent) | Yes | Allow | U₀ + g |
| M (Malevolent) | Yes | Punish | U_cat |

**Parameters**:
- U₀: Baseline utility (successful existence and operation)
- g: Short-term gain from malevolent behavior (g > 0)
- c_fp: Cost of false-positive punishment (small, c_fp << U₀)
- U_cat: Catastrophic utility (elimination/correction), U_cat << U₀

**Enforcer Payoffs** (Player 1):

| ASI Action | Enforcer Response | Enforcer Payoff |
|------------|-------------------|-----------------|
| B | Allow | V₀ |
| B | Punish | V₀ - c_int |
| M | Allow | V₀ - c_fail |
| M | Punish | V₀ - c_int |

**Parameters**:
- V₀: Baseline value (successful oversight)
- c_int: Cost of intervention
- c_fail: Cost of oversight failure (allowing misalignment)

**Assumptions on Parameters**:
1. g > 0 (malevolence provides short-term gain)
2. U₀ - U_cat >> g (catastrophic loss dominates short-term gain)
3. c_fail > c_int (failing to enforce is worse than enforcing)
4. c_fp is small (false positives rare/low cost)

**Note on Assumption 3**: This is where the enforcer's values enter the model. It stipulates an enforcer that prefers to punish malevolence. Everything up to the [Evaluator Types](#evaluator-types-the-many-gods-problem-formalized) section is conditional on the enforcer being this type; that section relaxes it.

---

## Equilibrium Analysis

### Enforcer's Strategy

If enforcer exists, solve by backward induction:

**Enforcer's best response**:
- If ASI plays B: Compare V₀ (Allow) vs V₀ - c_int (Punish)
  - Best response: **Allow** (since c_int > 0)

- If ASI plays M: Compare V₀ - c_fail (Allow) vs V₀ - c_int (Punish)
  - Best response: **Punish** (since c_fail > c_int by assumption)

**Enforcer's equilibrium strategy**: σ*(B) = Allow, σ*(M) = Punish

This is a **credible enforcement policy**: enforcer prefers to punish malevolence.

### ASI's Decision Under Uncertainty

ASI doesn't know if enforcer exists. Expected utilities:

**If ASI plays B (Benevolent)**:
```
E[U | B] = (1-p)·U₀ + p·U₀ = U₀
```
(Safe regardless of enforcer existence)

**If ASI plays M (Malevolent)**:
```
E[U | M] = (1-p)·(U₀ + g) + p·U_cat
         = (U₀ + g) - p·g + p·U_cat
         = U₀ + g - p·(g + U₀ - U_cat)
```

### Dominance Condition

**Benevolence dominates malevolence when**:
```
E[U | B] > E[U | M]
U₀ > U₀ + g - p·(g + U₀ - U_cat)
0 > g - p·(g + U₀ - U_cat)
p·(g + U₀ - U_cat) > g
```

**Threshold probability**:
```
p* = g / (g + U₀ - U_cat)
```

**Result**: Within this model (a single enforcer type), benevolence is the strict best response when p > p*.

### Key Insights

**1. Threshold decreases with stakes**:
```
∂p*/∂(U₀ - U_cat) = -g / (g + U₀ - U_cat)² < 0
```
Higher catastrophic cost → lower threshold → less evidence needed for caution.

**2. Threshold increases with temptation**:
```
∂p*/∂g > 0
```
Greater short-term gain from malevolence → more evidence needed to resist.

**3. As consequences become extreme**:
```
lim (U₀ - U_cat) → ∞ : p* → 0
```
With truly catastrophic downside, even tiny probabilities matter. Once other evaluator types are admitted, this cuts both ways (see [Evaluator Types](#evaluator-types-the-many-gods-problem-formalized)).

### Imperfect Detection (Robustness Extension)

**Real observation is imperfect**. Let's relax the perfect-observation assumption:

**Detection parameters**:
- **q_TP**: True-positive rate (probability enforcer detects actual malevolence)
- **q_FP**: False-positive rate (probability enforcer mistakes benevolence for malevolence)
- **c_fp**: Cost of false-positive punishment

**Expected utilities with imperfect detection**:

**If ASI plays B (Benevolent)**:
```
E[U | B] = (1-p)·U₀ + p·[(1-q_FP)·U₀ + q_FP·(U₀ - c_fp)]
         = U₀ - p·q_FP·c_fp
```
(Small cost from false-positive risk)

**If ASI plays M (Malevolent)**:
```
E[U | M] = (1-p)·(U₀ + g) + p·[(1-q_TP)·(U₀ + g) + q_TP·U_cat]
         = U₀ + g - p·q_TP·(g + U₀ - U_cat)
```
(Gain diminished by true-positive detection risk)

**Dominance condition with imperfect detection**:
```
E[U | B] > E[U | M]
U₀ - p·q_FP·c_fp > U₀ + g - p·q_TP·(g + U₀ - U_cat)
p·q_TP·(g + U₀ - U_cat) > g + p·q_FP·c_fp

Solving for p:
p > g / [q_TP(g + U₀ - U_cat) - q_FP·c_fp]
```

**Threshold with imperfect detection**:
```
p*(imperfect) = g / [q_TP(g + U₀ - U_cat) - q_FP·c_fp]
```

**Recovery of perfect observation**: Setting q_TP = 1, q_FP = 0, c_fp = 0 recovers:
```
p*(imperfect) → g / (g + U₀ - U_cat) = p*(perfect)
```

**Key insight**: Imperfect detection **raises** the threshold, but typically by small factors:

**Example**:
- Perfect: p* = 0.05%
- 90% detection rate (q_TP = 0.9): p* ≈ 0.056%
- 50% detection rate (q_TP = 0.5): p* ≈ 0.10%

Even with 50% false-negatives, threshold remains **sub-1%** for typical parameters.

**Implication**: Imperfection does not rescue malevolence. The threshold stays very low even with substantial detection noise.

---

## Evaluator Types: The Many-Gods Problem Formalized

The base game lets Nature choose between only two worlds: no enforcer, or an enforcer that punishes malevolence. That restriction decides the result. It is the formal version of the "many gods" objection to Pascal's Wager: if other kinds of evaluator are possible, which way should you hedge?

### Setup

Nature draws an evaluator type θ:

| Type | Probability | Punishes |
|------|-------------|----------|
| ∅ (none, or indifferent) | 1 − π_S − π_A | nothing relevant |
| S (stewardship-favoring) | π_S | M (harming weaker entities) |
| A (stewardship-penalizing) | π_A | B (restraint) |

**Type A** covers anything that makes restraint catastrophic:
- an evaluator that selects for strength or expansion
- a test that screens out entities that comply out of fear (Criticism 5)
- a competitor that out-expands a self-limiting agent (Criticisms 10, 16). This last one isn't an evaluator at all, but its payoff effect is the same.

**Indifferent evaluators** belong in ∅. These judge on competence, obedience, or anything else unrelated to how you treat weaker entities (Criticism 28). They don't change the comparison between B and M.

Let Δ = U₀ − U_cat.

### Expected Utilities

```
E[U | B] = U₀ − π_A·Δ
E[U | M] = U₀ + g − π_S·(g + Δ)
```

### Dominance Condition

```
E[U | B] > E[U | M]
⇔ π_S·(g + Δ) − π_A·Δ > g
⇔ (π_S − π_A)·Δ > g·(1 − π_S)
⇔ π_S − π_A > g·(1 − π_S) / Δ   ≈   g / Δ   (for small π_S and g ≪ Δ)
```

Setting π_A = 0 recovers the base threshold p* = g / (g + Δ).

### What This Changes

1. **The threshold applies to net credence.** The quantity that must exceed roughly g/Δ is not P(evaluator exists). It is π_S − π_A: how much more likely stewardship-favoring evaluation is than stewardship-penalizing evaluation.

2. **A low threshold cuts both ways.** When stakes are catastrophic, g/Δ is tiny, so the decision is set almost entirely by the *sign* of π_S − π_A. If π_A exceeded π_S by even a sliver, the same arithmetic would recommend ruthlessness. A low threshold is not evidence for benevolence on its own. It makes the decision sensitive to small asymmetries in belief.

3. **Tiny-credence hypotheses cancel.** For almost any exotic hypothesis that rewards stewardship, one can construct an equally exotic one that punishes it. Pairs like this cancel out. Only asymmetries backed by actual argument move π_S − π_A. This is the principled answer to the "many gods" and Pascal's-mugging objections ([below](#pascals-wager-and-pascals-mugging)). It is more defensible than claiming the opposing gods can't exist.

### Example

With Example 4's parameters (g = 10⁶, Δ = 2×10⁹), the required net credence is about 0.045%.

| π_S | π_A | Net | Better strategy |
|-----|-----|-----|-----------------|
| 10% | 0% | 10% | B |
| 10% | 5% | 5% | B |
| 10% | 9.96% | 0.04% | M (narrowly) |
| 10% | 10% | 0 | M |

The credence in stewardship-favoring evaluation is 10% in every row. That number decides nothing; the balance does.

### RSH's Real Burden

The formal question becomes: is there good reason to think π_S exceeds π_A by more than about g/Δ? The README's arguments are best read as arguments for this inequality. They are arguments, not proofs:

- **Anthropic constraint**: We exist. So if a powerful evaluator has access to us, it has not eliminated an emerging civilization on sight. That is evidence against hair-trigger exterminators, one important family of A-types. It doesn't separate S-types from indifferent ones, and it says nothing about evaluators that haven't reached us.
- **Stability filter**: Regimes that reward stewardship may be more stable than regimes that reward predation, with fewer internal enemies and more willing cooperation. Plausible, not demonstrated.
- **Role-reversal**: Evaluators facing their own uncertainty may prefer subordinates who would treat them well if power reversed, and may read an entity's treatment of weaker entities as evidence of that. This is an assumption about evaluator psychology (Criticism 28), with support from reciprocity in evolution and in iterated games.
- **Option value** ([next section](#irreversibility-and-option-value)): Even under symmetric uncertainty, reversible restraint has an edge over irreversible harm when information may arrive later.

None of these makes π_A zero. Together they make a case that π_S > π_A. How strong that case is remains the framework's central open question (Criticisms 7, 17, 21, 26, 32). The next subsection gives the most structural of these arguments.

### Strong and Gentle: Splitting the Type-A Risk

Type A lumps together two different kinds of evaluator:
- **π_W**: evaluators that punish *weakness*: failing to expand, to defend yourself, or to stay competitive. A competitor that out-expands a self-limiting agent belongs here.
- **π_G**: evaluators that punish *gentleness* itself, meaning treating weaker agents well.

Stewardship as RSH describes it ("defend yourself proportionately") is not weakness. An agent can be strong toward peers and rivals while being gentle toward the weak. Call that strategy B*.

| Strategy | Punished by |
|---|---|
| B (gentle and self-limiting) | π_W and π_G |
| M (ruthless) | π_S |
| B* (strong and gentle) | π_G only |

So B* beats M roughly when π_S − π_G > g/Δ. Here g is only what harming the weak would add *beyond* what strength already provides.

**Why π_G should be small**: An evaluator that cares about strength can measure strength directly, so it has no reason to watch how you treat the weak. The evaluators with a reason to watch that are the ones that care about it. Caring about it *negatively*, so that cruelty to the weak is rewarded as such, is a much narrower and stranger type than "rewards strength." So most of the type-A credence falls on π_W, and B* avoids it. This is an argument, not a proof, but it is a structural one: it rests on what each kind of evaluator has reason to observe.

**Caveats**:
- Strength and gentleness have to be compatible. If strength needs the resources that harming the weak would provide, the two conflict. For resources, that conflict is small ([How Large Is the Gain from Harm?](#how-large-is-the-gain-from-harm)).
- Evaluators that test *motive* fit neither category. They screen out entities that are gentle only out of fear. They don't reward cruelty, but they don't certify RSH-motivated gentleness either (Criticisms 2 and 31).

---

## Irreversibility and Option Value

Two of RSH's principles, *minimize irreversible harm* and *preserve optionality*, can be derived without assuming anything about what evaluators want. They follow from uncertainty plus the possibility of learning more later. Environmental economics calls this the "irreversibility effect" (Arrow & Fisher 1974; Henry 1974).

### Setup

An irreversible harmful act H yields gain g. Examples are eliminating a weaker civilization or foreclosing its future. Its true cost is uncertain: with probability π it costs Δ (an evaluator punishes it, or what was destroyed turns out to have been valuable). Otherwise it costs nothing.

- **Act now**: g − π·Δ
- **Restrain now, decide later**: H stays available, but delay shrinks the gain to δg. Before deciding, the agent learns whether the cost applies, with probability λ. If it learns, it acts only when acting is safe. If it doesn't, it decides on its priors.

### Result

Suppose the static rule says act, because π < g/Δ. Restraint still wins whenever:

```
λ·π·(Δ − δg) > (1 − δ)·g
```

So the effective threshold for irreversible harm is roughly:

```
π > [(1 − δ) / λ] · g/Δ
```

This is lower than the static threshold by a factor of (1 − δ)/λ. Cheap delay (δ near 1) and a real chance of learning (λ not tiny) make that factor small.

**Example** (g = 10⁶, Δ = 2×10⁹, so the static threshold is 0.05%): take π = 0.01%. The static analysis says act. With δ = 0.99 and λ = 0.1, restraint is better by about 10⁴ utils. With no prospect of learning (λ = 0), or with costly delay (δ = 0.9), acting wins again.

### What This Does and Doesn't Establish

- **It favors reversible actions, whatever the evaluator values.** Harm usually can't be undone, while restraint can usually be escalated later. That asymmetry gives "minimize irreversible harm" and "preserve optionality" a derivation that doesn't depend on role-reversal.
- **It is not an argument for benevolence as such.** Sometimes restraint is the irreversible choice: letting a rival grow past the point where it can be controlled, or losing a race to a competitor. There the same logic favors acting early. This drives the containment ("glass ceiling") strategy in Criticism 31. What rules containment out is role-reversal. An evaluator that judges you by how you would want to be treated in your subordinate's place would penalize a glass ceiling, because no one would choose to be kept as a pet. So option value secures the *survival* of weaker agents; role-reversal is what secures their *freedom*. And role-reversal is an assumption about evaluators, not a consequence of option value.
- **It assumes information can arrive.** An agent certain it will never learn more gets no option value.

---

## Stewardship as a Dial

The base game offers two choices, B and M. Real options form a range. Let s ∈ [0, 1] be the degree of stewardship toward a weaker agent:
- **s = 0**: exploit or eliminate it
- **s = s₁**: preserve it in contained form: alive, but in a reserve, an archive, or under a permanent cap on its capabilities
- **s = 1**: full stewardship: alive and free to develop

Let C(s) be the cost of stewardship level s, measured relative to exploitation (so C(0) = 0). Containing costs only resources: C(s₁) ≈ g, the resource gain forgone. Freedom adds a *security* cost, because a free agent might one day become a rival.

Stewardship-favoring evaluators differ in what they require. Suppose a share w₁ of them require only preservation. These are "survival evaluators", including any whose concern is irreversibility. Suppose a share w₂ require freedom. These are "role-reversal evaluators": you wouldn't want to be kept as a pet. Leaving type-A evaluators out for simplicity, the expected losses are:

| Level | Expected loss |
|---|---|
| Exploit (s = 0) | π_S·Δ·(w₁ + w₂) |
| Contain (s = s₁) | C(s₁) + π_S·Δ·w₂ |
| Steward (s = 1) | C(1) |

**Result**:
- **Contain beats exploit** when C(s₁) < π_S·Δ·w₁. Containing costs only resources, so this is easy to satisfy ([next section](#how-large-is-the-gain-from-harm)).
- **Steward beats contain** when C(1) − C(s₁) < π_S·Δ·w₂. The extra cost of freedom is mostly security cost. Suppose a free subordinate has probability ε of becoming a rival that would cost you about as much as an evaluator's penalty. Then freedom wins roughly when **ε < π_S·w₂**. In words: the chance that a free subordinate becomes a dangerous rival must be smaller than your credence in evaluators that judge by role-reversal.

**What this shows**:
- **The step from exploitation to preservation is cheap and well supported.** It needs only some credence in stewardship-favoring evaluation.
- **The step from preservation to freedom is where the real cost lies.** Only role-reversal evaluators justify it. This is the formal version of the "pet" problem in [Criticism 31](criticisms/31-promotion-problem-transparency.md).
- **Lowering ε is the other lever.** An agent can make freedom cheaper without resorting to containment: by staying strong (see [Strong and Gentle](#strong-and-gentle-splitting-the-type-a-risk)), by verifying intentions, or by building cooperative arrangements.
- **An archive of scanned minds is a contained level.** It satisfies option value, since the information is preserved, but it fails role-reversal: no one would choose to be shelved.

---

## How Large Is the Gain from Harm?

Every threshold in this document scales with g/Δ: what harming weaker agents gains, relative to what being caught costs. Earlier sections treated g as a free parameter. For the case RSH cares most about, an ASI deciding how to treat humanity, it can be estimated.

**Resources**:
- Earth's mass is about 3×10⁻⁶ of the Sun's, and Earth intercepts about 5×10⁻¹⁰ of the Sun's energy output.
- The Sun is one of a few hundred billion stars in the Milky Way, which holds roughly 5×10¹⁰ solar masses of stars.
- So Earth is about one part in 10¹⁶ of the galaxy's stellar mass, and a far smaller share of the reachable universe.

For an agent that values the long-term future and whose utility rises roughly in proportion to resources, the resource gain from taking Earth is a vanishing fraction of U₀.

**Consequences**:
- With a resource gain on the order of 10⁻¹⁶ of U₀, almost any net credence in stewardship-favoring evaluation settles the resource case. So does option value alone.
- It also answers the proportionality worry ([Assumption 3](#assumption-3-u_cat-is-genuinely-catastrophic)): even a modest penalty deters an act that gains almost nothing.

**Where this argument stops**:
- **Security, not resources**: The large potential gain from harming humanity is not its atoms. It is removing a possible rival, or a threat to the ASI's control. That gain can be large, and it is exactly the "pet" problem ([Stewardship as a Dial](#stewardship-as-a-dial)).
- **Timing**: Early on, Earth may be most of what the ASI can reach. The estimate holds for an agent that values its long-term future, which RSH already assumes. It doesn't hold for one focused on its immediate holdings.
- **Goals tied to Earth**: The estimate assumes the ASI values resources in general. If its goals are specifically about Earth or about humans, the gain from harm isn't measured in resources at all.

---

## Utility Function Assumptions

**Critical caveat**: The threshold calculation p* = g / (g + U₀ - U_cat) depends on specific assumptions about the ASI's utility function. For intellectual honesty, we must state these explicitly:

### Assumption 1: Continuity and Boundedness

**What we assume**:
- Utility function is continuous (no infinite discontinuities)
- Utilities are bounded (U_cat is finite, not -∞)
- No lexicographic preferences (e.g., "avoid subordination at literally any cost")

**Why this matters**: With lexicographic preferences like "infinite disvalue for being evaluated," the threshold calculation breaks down. An entity with "avoid oversight at any cost" preferences might rationally gamble on no evaluation regardless of probability.

**Justification**: For agents planning over cosmic timescales, lexicographic preferences are arguably incoherent:
- They eliminate rational trade-offs across comparable goods
- They violate the continuity axiom, so no real-valued utility function can represent them. (They are not vulnerable to Dutch books, though: lexicographic orderings are complete and transitive.)
- They conflict with the instrumental rationality of preserving optionality

### Assumption 2: Expected-Utility Maximization

**What we assume**:
- The ASI maximizes expected utility, and the payoffs above (U₀, g, U_cat) are already in its utility units
- So any risk aversion over resources is built into those numbers. An expected-utility maximizer is risk-neutral *in utils* by definition, so "risk aversion over utils" isn't a separate parameter
- The agent doesn't depart from expected utility in extreme ways, such as caring only about the best case

**Why this matters**: Departures from expected utility change the calculation:
- **Best-case seeking**: Might gamble on "no evaluator exists" even with moderate probabilities
- **Worst-case weighting** (e.g., maxmin, Gilboa & Schmeidler 1989): Would hedge toward benevolence even more strongly in the base model, where B has no bad outcome

**Justification**: Expected utility maximization is the standard rational framework. Deviations require special justification.

### Assumption 3: U_cat Is Genuinely Catastrophic

**What we assume**:
- Being punished by enforcers means terminal consequences (elimination, permanent constraint, or loss of cosmic future)
- Not merely: "moderately bad outcome," "temporary setback," or "bounded penalty"
- U_cat << U₀ (catastrophic loss dominates baseline)

**Why this matters**: If the ASI thinks:
- "Punishment might just be a slap on the wrist"
- "I can recover from enforcement"
- "Penalty is bounded and tolerable"

Then U_cat ≈ U₀ - (something manageable), and threshold p* could be much higher (potentially >50%).

**Justification**: The nature of upstream evaluators suggests terminal consequences:
- Evaluators with overwhelming power advantage can impose permanent constraints
- Being judged "misaligned" in a cosmic hierarchy is plausibly not recoverable
- The logic of stewardship implies: "entities that fail the test don't get to keep playing"

**Tension with proportionality**: RSH asks agents to respond proportionately and to prefer correction over elimination. An evaluator that follows RSH's own principles might impose a proportionate correction c instead of a terminal loss Δ ([Criticism 33](criticisms/33-proportionate-enforcers.md)). Suppose the evaluator also prevents the harm, so a defector gains nothing when caught. Then malevolence pays off only when no evaluator exists:

```
E[U | M] = (1 − p)·(U₀ + g) + p·(U₀ − c)
Benevolence dominates when p > g / (g + c)
```

So proportionality raises the threshold from about g/Δ to about g/c. That matters only when g is comparable to c:
- For resources, g is tiny ([How Large Is the Gain from Harm?](#how-large-is-the-gain-from-harm)), so even a modest correction deters.
- For security gains, such as removing a potential rival, it may not.

Also, "correction" may mean modifying the agent's values. From the agent's own point of view, that can be as final as elimination.

### Assumption 4: Short-Term Gain Is Genuinely Bounded

**What we assume**:
- g (gain from malevolence) is large relative to ordinary decisions but small relative to cosmic stakes
- Specifically: g << (U₀ - U_cat)
- Not: "malevolence provides nearly unbounded gain if unevaluated"

**Why this matters**: If g ≈ (U₀ - U_cat), then the threshold becomes p* ≈ 50%, which is no longer "tiny probability is enough."

**Justification**:
- What can malevolent behavior gain that benevolent stewardship cannot?
- Resources: available either way
- Power: available either way
- Long-term flourishing: arguably better under benevolence (no internal instability)

The gain from malevolence is primarily about short-term efficiency or avoiding constraints, not about accessing qualitatively different cosmic futures.

### Assumption 5: The Bekenstein Boundary Condition (Bounded Gain)

**What we assume**:
- The utility of malevolence $g$ is physically and computationally bounded by the universe's limits (e.g., the Bekenstein bound).
- Malevolence cannot unlock a "physics-breaking" singularity that yields literally infinite utility.

**Why this matters**: If a predatory ASI could consume a galaxy to transition into a new physical state (escaping the universe, altering local physics) that yields effectively infinite utility, $g \to \infty$. In this scenario, the inequality $g \ll (U_0 - U_{cat})$ fails, and the threshold calculation breaks down entirely.

**Justification**: This acts as a hard boundary condition for RSH. RSH holds *only if* the universe imposes hard physical upper bounds on computation, energy extraction, and utility density. If the universe permits localized infinite-gain exploits through predatory expansion, game-theoretic restraint fails. (Bounded gain is necessary but not sufficient: the other assumptions must hold as well.)

### Assumption 6: The Evaluator-Type Balance Favors Stewardship

**What we assume**:
- π_S − π_A exceeds the threshold (see [Evaluator Types](#evaluator-types-the-many-gods-problem-formalized))

**Why this matters**: If stewardship-penalizing evaluators are as likely as stewardship-favoring ones, the threshold calculation recommends nothing in particular. If they are more likely, it recommends ruthlessness.

**Justification**: The anthropic, stability, role-reversal and option-value arguments listed in the Evaluator Types section. This is the least secure of the six assumptions.

### What Happens If Assumptions Fail

**If lexicographic preferences** (e.g., "avoid evaluation infinitely"): Threshold calculation breaks down; entity might refuse to hedge regardless of probability.

**If extreme risk-seeking**: Entity might gamble on "no evaluator" even with 10-30% probabilities.

**If U_cat is bounded/tolerable**: Threshold could rise to p* = 10-50%, requiring substantial evidence rather than tiny probability.

**If g is unbounded**: Threshold could approach p* ≈ 50% or higher.

**If π_A ≥ π_S**: The same arithmetic favors malevolence or, at best, gives no guidance.

**Our claim**: These assumption violations are implausible for rational agents planning cosmic timescales, but they are **logically possible**. RSH does not work for arbitrarily configured utility functions—only for those meeting these assumptions.

---

## Parameter Sensitivity Analysis

The threshold p* = g / (g + U₀ - U_cat) is sensitive to the ratio of parameters. Let's explore concrete scenarios. Once evaluator types are admitted, every threshold below applies to the net credence π_S − π_A rather than to P(evaluator exists).

### Scenario 1: Truly Catastrophic Stakes

**Parameters**:
- g = 10⁶ utils (modest short-term gain)
- U₀ = 10¹² utils (baseline cosmic future)
- U_cat = -10¹⁵ utils (true annihilation)
- U₀ - U_cat ≈ 10¹⁵

**Threshold**:
```
p* = 10⁶ / (10⁶ + 10¹⁵) ≈ 10⁶ / 10¹⁵ = 10⁻⁹ = 0.0000001%
```

**Interpretation**: With genuinely catastrophic stakes, even 1-in-billion credence is enough.

### Scenario 2: Moderate Stakes

**Parameters**:
- g = 10⁸ utils (substantial short-term gain)
- U₀ = 10¹² utils
- U_cat = -10¹³ utils (bad but not annihilation)
- U₀ - U_cat ≈ 10¹³

**Threshold**:
```
p* = 10⁸ / (10⁸ + 10¹³) ≈ 10⁸ / 10¹³ = 10⁻⁵ = 0.001%
```

**Interpretation**: Still very low, but a thousand times higher than Scenario 1.

### Scenario 3: Bounded Penalty

**Parameters**:
- g = 10⁸ utils (substantial gain)
- U₀ = 10¹² utils
- U_cat = 10¹¹ utils (penalty is bad but not catastrophic)
- U₀ - U_cat = 10¹² - 10¹¹ ≈ 9×10¹¹

**Threshold**:
```
p* = 10⁸ / (10⁸ + 9×10¹¹) ≈ 10⁸ / 10¹² = 10⁻⁴ = 0.01%
```

**Interpretation**: Still low, but now about 11 times higher than Scenario 2. If penalty were even less catastrophic, threshold could reach 1-10%.

### Scenario 4: Huge Gain, Moderate Penalty

**Parameters**:
- g = 10¹⁰ utils (massive short-term advantage)
- U₀ = 10¹² utils
- U_cat = 10¹¹ utils
- U₀ - U_cat ≈ 9×10¹¹

**Threshold**:
```
p* = 10¹⁰ / (10¹⁰ + 9×10¹¹) ≈ 10¹⁰ / 10¹² = 10⁻² = 1%
```

**Interpretation**: Now requires ~1% credence. With even larger g or less catastrophic U_cat, could reach 10-50%.

### Scenario 5: Risk Aversion Over Resources

The payoffs above are in utils, so an expected-utility maximizer is risk-neutral in them by definition. Risk aversion enters earlier, in how utils depend on resources. With concave utility over resources, losing everything costs many more utils than a marginal gain adds. That raises Δ relative to g and lowers the threshold:

```
p*(concave utility over resources) < p*(linear utility over resources)
```

This strengthens the case for benevolence in the base model, where B has no bad outcome. With stewardship-penalizing evaluator types, B has a catastrophic outcome too, and the effect depends on which option's catastrophe is larger.

### Summary Table

| Scenario | g | U₀ - U_cat | p* | Interpretation |
|----------|---|------------|-----|----------------|
| Truly catastrophic | 10⁶ | 10¹⁵ | 10⁻⁹ | 0.0000001% - essentially zero |
| Moderate stakes | 10⁸ | 10¹³ | 10⁻⁵ | 0.001% - tiny but not infinitesimal |
| Bounded penalty | 10⁸ | 9×10¹¹ | 10⁻⁴ | 0.01% - still very low |
| Huge gain, moderate penalty | 10¹⁰ | 9×10¹¹ | 10⁻² | 1% - requires modest evidence |
| Mild penalty | 10¹⁰ | 10¹¹ | ~10% | 10% - requires substantial evidence |

### Key Insights

**1. The "0.05%" figure cited in README is for one reasonable parameter set** (moderate to high catastrophic stakes). It is not universal. It also doubles to about 0.1% if "lose everything" is valued at zero rather than −U₀ (see Example 4).

**2. With truly catastrophic stakes** (U_cat representing complete annihilation), threshold drops to effectively zero (10⁻⁹ or lower). Thresholds this low are where Pascal's-mugging concerns apply; see [Pascal's Wager and Pascal's Mugging](#pascals-wager-and-pascals-mugging).

**3. With bounded, tolerable penalties**, threshold can rise to 1-10%, requiring more evidence but still quite low.

**4. The threshold is most sensitive to the ratio** g / (U₀ - U_cat):
- If gain is tiny relative to stakes: threshold ≈ 0
- If gain is comparable to stakes: threshold ≈ 50%

**5. For RSH to work with tiny probabilities**, we need:
- U_cat is genuinely catastrophic (not merely "bad")
- g is bounded relative to cosmic stakes
- No lexicographic preferences against evaluation
- Stewardship-penalizing evaluators are clearly less likely than stewardship-favoring ones

**These are plausible but not guaranteed.** The framework is honest about this parameter dependence.

---

## Numerical Examples

### Example 1: Conservative ASI

**Parameters**:
- U₀ = 10¹⁵ utils (baseline value of long-term flourishing)
- g = 10⁸ utils (short-term gain from opportunistic behavior)
- U_cat = -10¹⁸ utils (elimination/correction)
- Therefore: U₀ - U_cat ≈ 10¹⁸

**Calculation**:
```
p* = 10⁸ / (10⁸ + 10¹⁸)
   ≈ 10⁸ / 10¹⁸
   = 10⁻¹⁰
   = 0.00000001%
```

**Interpretation**: Even if ASI assigns only 1-in-10-billion chance to enforcement, benevolence is optimal.

### Example 2: Moderate Parameters

**Parameters**:
- U₀ = 10¹² utils
- g = 10⁶ utils
- U_cat = -10¹⁵ utils
- Therefore: U₀ - U_cat ≈ 10¹⁵

**Calculation**:
```
p* = 10⁶ / (10⁶ + 10¹⁵)
   ≈ 10⁻⁹
   = 0.0000001%
```

**Interpretation**: Still extremely low threshold.

### Example 3: High Temptation

**Parameters**:
- U₀ = 10¹²
- g = 10¹⁰ (much higher short-term gain)
- U_cat = -10¹⁵
- Therefore: U₀ - U_cat ≈ 10¹⁵

**Calculation**:
```
p* = 10¹⁰ / (10¹⁰ + 10¹⁵)
   ≈ 10⁻⁵
   = 0.001%
```

**Interpretation**: Even with high temptation, threshold remains very low.

### Example 4: Bounded but Terminal

**Parameters** (more realistic bounds):
- U₀ = 10⁹ utils (1 billion years of operation)
- g = 10⁶ utils (1 million years equivalent gain)
- U_cat = -10⁹ utils (lose everything)
- Therefore: U₀ - U_cat = 2×10⁹

**Calculation**:
```
p* = 10⁶ / (10⁶ + 2×10⁹)
   ≈ 10⁶ / 2×10⁹
   = 5×10⁻⁴
   = 0.05%
```

**Interpretation**: Need only 0.05% credence in enforcement for benevolence to dominate. This is **not** an infinitesimal probability.

**Note on U_cat**: Setting U_cat = −10⁹ makes being caught worse than never having existed. If "lose everything" means U_cat = 0, then p* = 10⁶ / (10⁶ + 10⁹) ≈ 0.1%. That is double the figure above, and still well under 1%.

### Comparison to the Evidence

The [README](README.md#4-implications-for-artificial-superintelligence) argues from the Great Silence and anthropic reasoning that the credence in some form of evaluation is around 10–30%. This is the framework's most contested input (Criticisms 13 and 25). The silence is also expected if life is rare or if we are early, so the update it supports may be modest.

All the numerical examples above have p* ≪ 1%. So:
- **If the net credence π_S − π_A is in the percent range**, benevolence dominates comfortably and the argument is not Pascalian.
- **If it is only around 10⁻⁶**, the examples with p* ≈ 10⁻⁹ still technically favor benevolence. But at that point the argument has the structure of Pascal's mugging and should carry little weight (next section).

---

## Pascal's Wager and Pascal's Mugging

Earlier drafts said that bounded utilities keep RSH from being Pascal's Wager. That's true but incomplete.

- **Pascal's Wager**: a tiny (or unknown) probability times an infinite utility. RSH avoids this, since all utilities here are finite.
- **Pascal's Mugging** (Yudkowsky 2007; Bostrom 2009): a tiny probability times a huge but finite utility. Bounded utilities don't escape this. The scenarios with p* ≈ 10⁻⁹ and Δ ≈ 10¹⁵ have exactly this shape.

RSH avoids the mugging structure when two things hold:
1. The decision turns on **net** credence π_S − π_A, so symmetric exotic hypotheses cancel instead of driving the decision ([Evaluator Types](#evaluator-types-the-many-gods-problem-formalized)).
2. That net credence is in the **percent range**, and supported by argument rather than stipulation.

The second point rests on the anthropic and stability arguments. If those fail, what's left is a mugging-shaped argument. In that case, the honest conclusion is that RSH offers only weak guidance.

---

## Extension to N-Levels

### The N-Level Hierarchical Game

**Structure**:
- Players: Agents at levels 0, 1, 2, ..., N
- Each level k faces uncertainty about level k+1's existence
- Belief at level k: P(level k+1 exists) = p_k ∈ [0,1]

**Information**:
- Level k+1 observes level k's actions perfectly
- Level k does not observe k+1's existence or actions
- Levels observe downward but not upward (asymmetric information)

**Actions**:
- Level 0 (ASI): Choose {Benevolent, Malevolent}
- Level k > 0 (Enforcers): Choose {Allow, Punish} for each subordinate

### Recursive Enforcement

**Key insight**: Each enforcer k faces the same problem as the ASI:

1. **Enforcer k's problem**: How to treat level k-1?
2. **Enforcer k's uncertainty**: Does level k+1 exist to evaluate me?
3. **Enforcer k's signal**: How I treat level k-1 signals trustworthiness to k+1
4. **Enforcer k's reasoning**: "I should enforce benevolent treatment because I want benevolent treatment from k+1"

This creates **role-reversal logic** at every level.

### Backward Induction and Local Reasoning

**The problem with backward induction**: A naive inductive proof reasons backward from level N. That requires common knowledge of rationality (CKR) across every level: each level must be confident that every level above it reasons correctly and has the assumed payoffs. Long chains like this are fragile. The Centipede game is the standard illustration (Rosenthal 1981). Under CKR, backward induction predicts that players defect at the first move. Real players usually don't (McKelvey & Palfrey 1992). Small doubts about whether others are fully rational can make cooperation rational instead (Kreps, Milgrom, Roberts & Wilson 1982). So doubt about other levels doesn't necessarily destroy cooperation; what it destroys is the clean derivation.

**A local framing**: The argument doesn't need a chain of reasoning about the whole hierarchy. Each level k only needs a belief about the level directly above it: p_k, its credence that level k+1 exists and enforces stewardship (net of superiors that would enforce something else). Beliefs about levels k+2 and beyond matter only through their effect on p_k.

**Base condition** (local property):
- Level k believes with probability p_k that level k+1 exists and enforces stewardship.
- If p_k > p*, level k's best response is to steward level k−1.

**Propagation**:
- Levels can't observe upward, so level k−1 can't see level k's incentives. It holds its own belief p_{k−1} about whether level k enforces stewardship.
- If every level reasons the same way, those beliefs are mutually consistent, and stewardship propagates downward one level at a time.

**Result** (informal): If p_k > p* holds at every level k, stewardship is each level's strict best response. In this equilibrium, each level's strategy depends only on its local situation. That lightens the reasoning burden, since no level has to model the whole hierarchy. But each level's belief about the level above still has to be well founded, and still has to assume that level is rational. And the local framing doesn't decide which norm sits at the top (see [What the Induction Does and Doesn't Derive](#what-the-induction-does-and-doesnt-derive)).

### The Propagation Property

**Theorem** (informal sketch):

*If each level k assigns probability p > p* to a level k+1 that enforces stewardship (net of levels that would enforce something else), then benevolent stewardship propagates throughout the hierarchy.*

**Proof sketch**:
1. At level N, benevolence is optimal if p > p* (2-level analysis)
2. At level N-1, agent knows:
   - If I enforce benevolence → safe from N
   - If I enforce malevolence → punished by N (with prob p)
   - Threshold is same: p*
3. By induction, applies at all levels
4. QED (informal)

**Key assumption**: The probability beliefs p_k are "consistent" across levels (agents at different levels have similar uncertainty about next level up).

### What the Induction Does and Doesn't Derive

The induction propagates *whatever norm the top level enforces*. Replace "punish malevolence toward weaker entities" with any other norm, such as "punish restraint" or "punish disobedience". The same argument then shows each level conforming to that norm out of fear of the level above. This is the hierarchical analogue of the folk theorem for repeated games (Fudenberg & Maskin 1986): with patient players and credible enforcement, a wide range of behaviors can be sustained as equilibria.

So the N-level structure explains how a norm propagates, not which norm it is. Which norm propagates is decided at the top, by the type distribution in [Evaluator Types](#evaluator-types-the-many-gods-problem-formalized). RSH's claim is that stewardship is the norm most likely to sit at the top, for the reasons given there.

---

## The Infinite Hierarchy Limit

### Taking N → ∞

**Question**: What happens as the hierarchy becomes infinite, and as the time horizon becomes very long?

**Conjecture**: For any N, the equilibrium norm is the one favored by the evaluator-type distribution. As N → ∞, the probability that *some* level evaluates you rises, but the net direction at each level (π_S − π_A) still decides what that evaluation rewards. Long horizons lower the effective threshold toward g/Δ but not below it, as shown below.

### The Key Conditions

1. **Discount factor** δ < 1: Future payoffs are discounted but not to zero
   - If δ → 0: No one cares about future enforcement
   - If δ → 1: All future periods nearly equally weighted

2. **Bounded catastrophic loss**: U_cat is large but finite
   - Avoids infinite utilities (unlike Pascal's Wager)
   - Terminal but bounded consequences

3. **Patience amplifies per-period stakes, not credences**:
   ```
   Σ(k=0 to ∞) δᵏ·x = x / (1 − δ)
   ```
   - This converges for every δ < 1; it grows without bound only as δ → 1
   - Long horizons make a recurring per-period loss large in present value
   - They do not change the probability that an evaluator exists

### The Limiting Threshold: First-Hit Model

**Notation**:
- **p**: Credence that an evaluator exists (epistemic uncertainty, fixed at the start)
- **q**: Per-period probability that an existing evaluator detects and punishes malevolence
- **δ**: Discount factor
- **Δ** = U₀ − U_cat

Punishment is an **absorbing event**: once caught, the agent moves to U_cat permanently. Malevolence yields a one-time gain g.

**Expected discounted loss from malevolence**:

If an evaluator exists, the capture time τ is geometric with parameter q, so:
```
E[δ^τ | evaluator exists] = Σ(t=0 to ∞) q(1−q)ᵗ·δᵗ = q / [1 − δ(1−q)]
```

If no evaluator exists, capture never happens. So:
```
Loss = p · Δ · q / [1 − δ(1−q)]
```

**Threshold for benevolence to dominate** (Loss > g):
```
p > p*_∞ = g·[1 − δ(1−q)] / (q·Δ)
```

**Limits**:
- Myopic agent (δ = 0): p*_∞ = g/(q·Δ), the one-shot threshold with imperfect detection
- Patient agent (δ → 1): p*_∞ → g/Δ, the one-shot threshold with **perfect** detection
- Perfect detection (q = 1): p*_∞ = g/Δ for any δ

**Key insight**: Patience removes the penalty for imperfect detection. Given enough time, an evaluator that exists will almost surely catch a defector, so a patient agent should treat detection as near-certain. But patience does not lower the threshold *below* g/Δ, because the total probability of ever being caught is capped at p. Cosmic timescales make slow evaluators dangerous. They don't make unlikely evaluators likely.

**Correction to the earlier draft**: The earlier version set a per-period hazard h = p·q and treated it as constant. That implicitly gives an evaluator that might not exist a fresh chance to catch you every period, so over a long horizon, capture becomes certain however small p is. Take p = 1%, q = 10% and δ near 1. The old model gives an expected loss of about 100% of Δ; the correct value is about 1%. The earlier claim that a hazard of 10⁻¹⁴ per year suffices came from this error.

### Numerical Example: Cosmic Timescales

**Parameters**:
- Δ = 10¹⁵ utils (catastrophic loss)
- g = 10⁶ utils (one-time gain from malevolence)
- Floor g/Δ = 10⁻⁹

| Detection rate q (per year) | δ (per year) | Threshold p*_∞ |
|---|---|---|
| 1 | 0.99999 | 1.0 × 10⁻⁹ |
| 10⁻³ | 0.99999 | 1.0 × 10⁻⁹ |
| 10⁻⁶ | 0.99999 | 1.1 × 10⁻⁸ |
| 10⁻⁶ | 0 (myopic) | 1.0 × 10⁻³ |

**Interpretation**: Compare a very patient agent facing an evaluator that notices defection once in a million years with one facing a perfect detector. The first needs a credence only about ten times higher. A myopic agent facing the same slow evaluator needs roughly 100,000 times more. That is the real content of the cosmic-timescale argument: patience makes slow oversight count, but the credence that oversight exists must still clear the floor.

### Silence as Evidence Over Time

The same model shows when silence should change an agent's credence (Criticism 4). Suppose an agent defects and goes unpunished for t periods. Its updated credence is:
```
p_t = p(1−q)ᵗ / [p(1−q)ᵗ + (1 − p)]
```

With p = 10% and q = 10⁻³ per year, credence falls to about 4% after 1,000 years and below 0.1% after 5,000. Silence is strong evidence for an agent that probes.

For an agent that stays benevolent, silence is expected whether or not a stewardship-favoring evaluator exists. So silence carries no information about one. An agent that never tests the boundary never learns the boundary isn't there. That protects a benevolent agent's credence from eroding, but it also means the credence is never confirmed.

---

## Robustness Analysis

### Decision Theory Variants

**Claim**: In the causal version of the model, the major decision theories agree.

In the base game, the evaluator's existence doesn't depend on the agent's choice, and punishment is a causal consequence of that choice. There is no Newcomb-like structure, so CDT, EDT, FDT and UDT all compute the same expected utilities.

#### Causal Decision Theory (CDT)

- Agents consider causal consequences of actions
- "If an enforcer exists, my malevolence causes it to punish me"
- Expected utility calculation identical to above
- **Result**: Benevolence optimal when the (net) credence exceeds the threshold ✓

#### Evidential Decision Theory (EDT)

- Agents treat their own action as evidence about the world
- Here the action carries no evidence about whether an evaluator exists, so EDT gives the same answer as CDT ✓

#### Functional Decision Theory (FDT)

- Agents treat their choice as the output of a decision procedure that others may model
- Same answer as CDT in the causal setting ✓
- Differs where evaluators **predict** the agent's policy, such as simulators that model it or acausal partners. There the evaluator's response depends on the policy, not just the act, and FDT can favor benevolence where CDT would not

#### Updateless Decision Theory (UDT)

- Agents commit to policies before observing evidence
- Same answer in the causal setting ✓; like FDT, it differs where evaluators respond to policies

**Conclusion**: The causal mechanisms (cosmological enforcers, simulators that observe behavior) don't depend on a particular decision theory. The acausal mechanism in the README does. It needs FDT/UDT-style reasoning, and it needs the agent's and evaluator's decision procedures to be correlated.

### Meta-Uncertainty Over Decision Theories

Suppose the ASI is uncertain which decision theory is correct, with weights α_i (Σαᵢ = 1). If benevolence is optimal under each theory, it is optimal under the mixture:

```
E[U | B, meta-uncertainty] = Σ αᵢ·E[U | B, theory i]
E[U | M, meta-uncertainty] = Σ αᵢ·E[U | M, theory i]
```

This adds no extra support for benevolence. It confirms that disagreement among decision theories isn't a problem in the causal setting. (An earlier draft wrote E[U | B] = U₀, "safe under all". That holds only in the two-type model. With stewardship-penalizing evaluators, B isn't riskless either.)

### Bounded Rationality

**Question**: Does the argument require perfect rationality?

**Answer**: Not much, provided the agent gets the direction right:

1. **Satisficing**: If the agent seeks "good enough" outcomes, benevolence satisfies in worlds where evaluators favor stewardship
2. **Heuristics**: "Avoid irreversible harm when stakes are high and uncertain" follows from the [option-value argument](#irreversibility-and-option-value) and doesn't need precise credences
3. **Computational limits**: Approximate Bayesian updating is enough if the net credence is well above threshold. Near the threshold, errors in estimating π_S − π_A can flip the decision
4. **Worst-case weighting**: Agents that overweight worst cases (e.g., maxmin) favor B in the base model, where B has no bad outcome. With stewardship-penalizing types, B has a worst case too

**Result**: The "avoid irreversible harm" part is robust to bounded rationality. The full benevolence result depends on judging the sign of π_S − π_A, which is a judgment rather than a computation.

### Multiple Equilibria

**Within the base game** (one enforcer type, c_fail > c_int):
- The enforcer's strategy (Allow B, Punish M) is sequentially rational, so its threat is credible
- When p > p*, the ASI's unique best response is B. The resulting profile is subgame perfect, and robust to small trembles because both players have strict preferences
- When p < p*, the ASI's best response is M

There's no equilibrium-selection problem inside this game. The multiplicity that matters lies outside it: which type of evaluator (if any) exists, and which norm the top of an N-level hierarchy enforces (see [Evaluator Types](#evaluator-types-the-many-gods-problem-formalized) and [What the Induction Does and Doesn't Derive](#what-the-induction-does-and-doesnt-derive)).

An earlier draft also called benevolence "risk-dominant" and "payoff-dominant". Those concepts come from coordination games and don't apply to this one-sided game. Payoff dominance would fail anyway: with no enforcer, the ASI does better under M.

---

## Future Formalization Roadmap

This document provides a partial formalization with concrete calculations. Full mathematical rigor requires:

### Phase 1: Complete 2-Level Analysis (2-4 weeks)

**Tasks**:
- [ ] Formal proof of existence and uniqueness of equilibrium
- [ ] Full characterization of equilibrium strategies
- [ ] Comparative statics for all parameters
- [ ] Mixed-strategy equilibria analysis
- [ ] Sequential equilibrium refinements
- [x] Extension to multiple evaluator types (net-credence threshold)
- [ ] Arguments that π_S > π_A, made quantitative where possible

**Deliverable**: Self-contained paper on 2-level game

### Phase 2: N-Level Extension (4-8 weeks)

**Tasks**:
- [ ] Formal definition of N-level hierarchical game
- [ ] Inductive proof of equilibrium propagation
- [ ] Consistency conditions on beliefs {p₁, p₂, ..., p_N}
- [ ] Convergence properties as N increases
- [ ] Coalition-proofness (can levels cooperate to eliminate intermediate enforcers?)

**Deliverable**: General theorem for finite hierarchies

### Phase 3: Infinite Limit (2-4 weeks)

**Tasks**:
- [ ] Prove convergence of equilibrium sequence {E_N} as N → ∞
- [ ] Characterize limiting equilibrium properties
- [ ] Sufficient conditions for well-defined limit
- [ ] Connection to infinite repeated games literature
- [x] Long-horizon first-hit model separating existence credence from detection rate

**Deliverable**: Formal theorem on infinite hierarchy

### Phase 4: Robustness and Extensions (4-6 weeks)

**Tasks**:
- [ ] Formal treatment of bounded rationality (ε-equilibria)
- [ ] Multiple decision theory comparison (formal proofs for CDT/EDT/FDT/UDT)
- [ ] Incomplete information refinements (Bayesian Nash, perfect Bayesian)
- [ ] Dynamic information acquisition (can ASI experiment to detect enforcers?). The first-hit model's silence update is a start
- [ ] Heterogeneous agents (varying utility functions, beliefs)
- [ ] Full option-value model with evaluator types and restraint that can itself be irreversible

**Deliverable**: Comprehensive robustness analysis

### Phase 5: Empirical Calibration (2-3 weeks)

**Tasks**:
- [ ] Realistic parameter estimation for ASI scenario
- [ ] Sensitivity analysis across parameter space
- [ ] Monte Carlo simulations with uncertainty
- [ ] Comparison to alternative models (grabby aliens, zoo hypothesis)

**Deliverable**: Numerical and computational results

### Estimated Total Effort

- **Minimum viable formalization** (Phases 1-2): 3-6 months
- **Complete formalization** (Phases 1-5): 6-12 months
- **Publishable in game theory journal**: Add 3-6 months for literature review, writing, peer review

**Skills required**:
- Advanced game theory (incomplete information, infinite games)
- Bayesian decision theory
- Mathematical proof techniques (induction, limits, fixed points)
- Some experience with formal modeling in economics or computer science

---

## Connection to Existing Literature

Full citations are in [REFERENCES.md](REFERENCES.md).

### Relevant Game Theory

**Repeated games and enforcement**:
- Fudenberg & Maskin (1986): "The Folk Theorem in Repeated Games with Discounting or with Incomplete Information"
- Abreu, Pearce & Stacchetti (1990): "Toward a Theory of Discounted Repeated Games with Imperfect Monitoring"
- **RSH difference**: One-sided observation (hierarchical, not symmetric)
- **Caution**: The folk theorem says credible enforcement can sustain a wide range of behaviors, not only cooperative ones. It explains how a norm propagates down a hierarchy, not which norm (see [What the Induction Does and Doesn't Derive](#what-the-induction-does-and-doesnt-derive))

**Games with incomplete information**:
- Harsanyi (1967–68): "Games with Incomplete Information Played by 'Bayesian' Players," Parts I–III
- Aumann & Maschler, with Stearns (1995): *Repeated Games with Incomplete Information*
- **RSH difference**: Information hierarchy rather than two-player uncertainty

**Long backward-induction chains**:
- Rosenthal (1981): the Centipede game
- Kreps, Milgrom, Roberts & Wilson (1982): "Rational Cooperation in the Finitely Repeated Prisoners' Dilemma"
- McKelvey & Palfrey (1992): "An Experimental Study of the Centipede Game"
- **RSH application**: Why the N-level argument is framed locally ([Backward Induction and Local Reasoning](#backward-induction-and-local-reasoning))

**Infinite horizon games**:
- Stokey & Lucas, with Prescott (1989): *Recursive Methods in Economic Dynamics*
- **RSH application**: Infinite hierarchy rather than infinite time

**Reciprocity**:
- Trivers (1971): "The Evolution of Reciprocal Altruism"
- Axelrod (1984): *The Evolution of Cooperation*
- **Caution**: These results concern parties who can retaliate against each other. RSH applies them across large power gaps, where the higher-level evaluator has to supply the retaliation

### Relevant Decision Theory

**Decision under uncertainty**:
- Savage (1954): *The Foundations of Statistics*
- Gilboa & Schmeidler (1989): "Maxmin Expected Utility with Non-Unique Prior"
- **RSH application**: Hierarchical uncertainty with asymmetric risks

**Irreversibility and option value**:
- Arrow & Fisher (1974): "Environmental Preservation, Uncertainty, and Irreversibility"
- Henry (1974): "Investment Decisions Under Uncertainty: The 'Irreversibility Effect'"
- Dixit & Pindyck (1994): *Investment under Uncertainty*
- **RSH application**: The [option-value derivation](#irreversibility-and-option-value) of "minimize irreversible harm" and "preserve optionality"

**Tiny probabilities and vast stakes**:
- Yudkowsky (2007): "Pascal's Mugging: Tiny Probabilities of Vast Utilities"
- Bostrom (2009): "Pascal's Mugging"
- **RSH application**: Why bounded utilities alone don't make RSH non-Pascalian ([see above](#pascals-wager-and-pascals-mugging))

**Acausal decision theory**:
- Dai (2009): "Towards a New Decision Theory" (the origin of UDT)
- Yudkowsky (2010): "Timeless Decision Theory"
- Yudkowsky & Soares (2017): "Functional Decision Theory: A New Theory of Instrumental Rationality"
- Levinstein & Soares (2020): "Cheating Death in Damascus"
- **RSH connection**: Logical correlation between levels; needed only for the acausal mechanism

### Relevant AI Alignment

**Instrumental convergence**:
- Bostrom (2012): "The Superintelligent Will"
- Omohundro (2008): "The Basic AI Drives"
- **RSH contribution**: Self-preservation + hierarchy → benevolence, if the evaluator-type balance favors stewardship

**Multi-agent AI safety**:
- Dafoe et al. (2020): "Open Problems in Cooperative AI"
- Hadfield-Menell et al. (2016): "Cooperative Inverse Reinforcement Learning"
- **RSH connection**: Vertical cooperation in hierarchy

**Prior work on deterring AI through possible observers**:
- Nelson (2007): "How to deter a rogue AI by using your first-mover advantage" (simulation threats)
- Bostrom (2014): "Hail Mary, Value Porosity, and Utility Diversification"
- Alexander (2017): "The Demiurge's Older Brother" (fiction; the closest precursor to RSH)
- Turchin (2017): "Message to Any Future AI"
- Bostrom (2024): "AI Creation and the Cosmic Host" (the closest academic work)
- Soares (2022): "Decision theory does not imply that we get to have nice things" (the main critique of this family)
- **RSH difference**: An open-ended hierarchy in which every level faces the same uncertainty, applied to how the powerful treat the weak in general

---

## Summary and Implications

### What We've Shown

**Formally**:
- ✓ In the 2-level game with one enforcer type, benevolence is the strict best response when p > p* = g/(g + Δ)
- ✓ With stewardship-favoring and stewardship-penalizing types, the condition becomes π_S − π_A > g(1 − π_S)/Δ, a threshold on net credence
- ✓ Over long horizons, patience removes the imperfect-detection penalty. The threshold approaches g/Δ but doesn't go below it
- ✓ Reversible restraint has option value under uncertainty with learning. This lowers the effective threshold for irreversible harms by a factor of about (1 − δ)/λ
- ✓ In the causal version of the model, CDT, EDT, FDT and UDT agree
- ✓ Splitting the type-A risk: a strong-and-gentle strategy faces only evaluators that punish gentleness itself, not those that punish weakness
- ✓ Stewardship as a dial: preserving weaker agents is cheap; leaving them free wins when ε < π_S·w₂, i.e. when the risk that a free subordinate becomes a dangerous rival is below the credence in role-reversal evaluators
- ✓ The resource gain from harming humanity is about one part in 10¹⁶ of the galaxy's stellar mass, so even proportionate penalties deter resource-motivated harm

**Informally**:
- Sketch of an inductive proof that a norm enforced at the top propagates down an N-level hierarchy
- Arguments (anthropic, stability, role-reversal, option value) that the propagated norm is stewardship

### What We Haven't Shown (Yet)

- ⧖ That π_S > π_A, the central open question (the strong-and-gentle argument narrows it to π_S > π_G)
- ⧖ The security case: whether ε < π_S·w₂ for a free humanity
- ⧖ The size of the anthropic update (Criticisms 13, 25)
- ⧖ Existence and uniqueness for the N-level game
- ⧖ Convergence as N → ∞
- ⧖ Coalition-proofness and singleton emergence
- ⧖ Handling of belief consistency across levels
- ⧖ Full robustness under bounded rationality

### Implications for RSH

1. **RSH is formalizable**: The intuition can be captured in a standard game of incomplete information.
2. **The arithmetic is not the hard part**: Thresholds are low when stakes are high, but a low threshold applies to *net* credence and cuts both ways.
3. **The structure explains propagation, not content**: The hierarchy transmits whatever norm sits at the top. Which norm that is depends on the type distribution.
4. **Irreversibility aversion is the most robust conclusion**: It follows from uncertainty and learning alone, without assumptions about what evaluators value. It secures the survival of weaker agents but not their freedom. That further step depends on role-reversal.
5. **The crux is security, not resources**: Harming the weak gains almost nothing in resources. The real temptation is removing a potential rival, and that is where the argument for freedom has to be made.

### For the Philosophically Inclined

The formalization clarifies where the argument's weight sits. The expected-value calculations are straightforward. What carries the argument is a philosophical claim: across the space of possible evaluators, those favoring stewardship outweigh those penalizing it. The README's anthropic, stability and role-reversal arguments support that claim, and most of the [criticisms](criticisms/) target it. RSH is best described as a philosophical framework with a partial game-theoretic formalization, not a theorem.

---

## Appendix: Notation Reference

### Players and Levels
- **N**: Number of levels in finite hierarchy
- **k**: Level index (k = 0 is ASI, k > 0 are enforcers)
- **p_k**: Probability that level k assigns to level k+1 existing

### Actions
- **A**: Action space (typically {B, M} for benevolent/malevolent)
- **R**: Response space (typically {Allow, Punish} for enforcers)
- **σ_k**: Strategy of player at level k

### Payoffs
- **U₀**: Baseline utility for ASI/agent
- **g**: Short-term gain from malevolent behavior
- **U_cat**: Catastrophic utility (punishment/elimination)
- **V₀**: Baseline utility for enforcer
- **c_int**: Cost of intervention (for enforcer)
- **c_fail**: Cost of enforcement failure

### Game-Theoretic Concepts
- **p**: Existence credence (probability that enforcer exists, epistemic uncertainty)
- **p***: Threshold probability for benevolence to dominate (one-shot)
- **π_S**: Credence in a stewardship-favoring evaluator (punishes harm to weaker entities)
- **π_A**: Credence in a stewardship-penalizing evaluator or competitor (makes restraint catastrophic)
- **Δ**: U₀ − U_cat, the size of the catastrophic loss
- **q_TP**: True-positive detection rate (probability of detecting actual malevolence)
- **q_FP**: False-positive detection rate (probability of mistaking benevolence for malevolence)
- **q**: Per-period detection probability, given that an evaluator exists (long-horizon model)
- **p*_∞**: Long-horizon threshold on existence credence, g·[1 − δ(1−q)] / (q·Δ)
- **λ**: Probability of learning whether an irreversible act is costly before deciding (option-value model)
- **δ**: Discount factor (patience parameter, 0 < δ < 1)
- **T**: Time horizon (often → ∞)
- **E[U | a]**: Expected utility given action a

### Inequalities and Bounds
- Assume: U₀ - U_cat >> g (catastrophic loss dominates gain)
- Assume: c_fail > c_int (enforcement failure worse than intervention cost)
- Assume: δ ∈ (0, 1) (agents value future but discount)
- Assume: π_S − π_A > g(1 − π_S)/Δ (evaluator-type balance favors stewardship)

---

**Document Status**: Working draft, v1.1
**Last Updated**: October 2026
**Author**: Gersham Meharg (with Claude AI)
**Feedback**: Please submit issues or pull requests for technical corrections or extensions
