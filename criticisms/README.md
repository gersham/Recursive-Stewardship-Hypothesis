# Criticisms of the Recursive Stewardship Hypothesis

This directory contains detailed critical analysis of the Recursive Stewardship Hypothesis (RSH). Each criticism is documented with:
- A summary of the objection
- The problem in detail
- RSH's current best response
- **Criticism Grade (A to F)**: how strong the criticism itself is
- **Status**: how far RSH's response goes toward resolving it

## Grading System

**Grades rate the criticism's strength, not the quality of RSH's response:**
- **A/B** = Strong criticisms that pose significant challenges to RSH
- **C** = Moderate criticisms with valid concerns
- **D/F** = Weak criticisms, or ones that misread the framework

**Status is recorded separately**, so a strong criticism can still have a good response:
- **Open**: RSH has responses, but they don't resolve the criticism
- **Partly addressed**: The response resolves part of the criticism; a real remainder is left
- **Acknowledged**: RSH accepts the point and states it as an assumption or limitation
- **Addressed**: The response resolves the criticism

## Regrading Note (October 2026)

The grades were revised after an independent review. Earlier passes tended to downgrade a criticism as soon as a response was written. That produced inconsistencies: Criticism 21 was graded F on the strength of role-reversal, while Criticism 28 conceded that role-reversal is an assumption. The revision also reflects corrections to [game_theory.md](../game_theory.md):
- The benevolence threshold applies to **net** credence: stewardship-favoring evaluators minus stewardship-penalizing ones. It does not apply to P(evaluator exists). This makes the "many gods" family of criticisms (7, 17, 21, 26, 32) sharper.
- Long time horizons make slow oversight count, but they don't make unlikely oversight likely. The earlier claim that tiny credences become action-relevant over cosmic time came from a modelling error.

Previous grades and wording are in the git history; each file now states only its current position.

## On Evidence

RSH is not testable on human timescales the way a laboratory theory is. But it does use evidence: the Great Silence and anthropic reasoning are how it sets its key probability. Evidence that is allowed to count for RSH has to be allowed to count against it. So criticisms that use evidence (4, 12, 13, 25) are judged on whether their likelihood reasoning is sound. They are not dismissed for applying "the wrong standard," as earlier versions of this index did.

## Summary Table

| # | Criticism | Grade | Status |
|---|-----------|-------|--------|
| 1 | [First Mover / Monopoly Circularity](01-first-mover-monopoly-circularity.md) | C | Partly addressed |
| 2 | [Indistinguishability Problem](02-indistinguishability-problem.md) | C | Partly addressed |
| 3 | [Multiple Equilibria / Which Benevolence](03-multiple-equilibria-which-benevolence.md) | C | Partly addressed |
| 4 | [Anti-Induction / Bayesian Updating](04-anti-induction-bayesian-updating.md) | C | Partly addressed |
| 5 | [Acausal Blackmail Meta-Game](05-acausal-blackmail-meta-game.md) | C | Partly addressed |
| 6 | [Anthropomorphic Values Problem](06-anthropomorphic-values-problem.md) | C | Partly addressed |
| 7 | [Evil God Objection](07-evil-god-objection.md) | **B** | Open |
| 8 | [Value Lock-In Timing](08-value-lock-in-timing.md) | C | Partly addressed |
| 9 | [Enforcer Psychology Gap](09-enforcer-psychology-gap.md) | C+ | Acknowledged |
| 10 | [Grabby Aliens Counter-Evidence](10-grabby-aliens-counter-evidence.md) | C+ | Partly addressed |
| 11 | [Instrumental Convergence Override](11-instrumental-convergence-override.md) | C+ | Partly addressed |
| 12 | [Selection Effect Reversal](12-selection-effect-reversal.md) | C+ | Open |
| 13 | [Silence is Evidence of Absence](13-silence-is-evidence-of-absence.md) | **B** | Acknowledged |
| 14 | [Infinite Regress Paralysis](14-infinite-regress-paralysis.md) | C | Partly addressed |
| 15 | [Time-Discount Problem](15-time-discount-problem.md) | C | Partly addressed |
| 16 | [Nash Equilibrium Instability](16-nash-equilibrium-instability.md) | C | Partly addressed |
| 17 | [Why This Hierarchy Regress](17-why-this-hierarchy-regress.md) | **B** | Open |
| 18 | [Modal Collapse / Human Behavior](18-modal-collapse-human-behavior.md) | C+ | Partly addressed |
| 19 | [Computational Truncation Problem](19-computational-truncation-problem.md) | C | Partly addressed |
| 20 | [Purpose of Enforcement Gap](20-purpose-of-enforcement-gap.md) | C | Partly addressed |
| 21 | [Unfalsifiable Circular Reasoning](21-deepest-hole-unfalsifiable-circular-reasoning.md) | **B** | Partly addressed |
| 22 | [Decision Theory Dependence](22-decision-theory-dependence.md) | D+ | Addressed for causal mechanisms; open for acausal |
| 23 | [Bounded Utility and Time Discounting](23-bounded-utility-discounting.md) | C+ | Partly addressed |
| 24 | [Formalization Gap](24-formalization-gap.md) | C | Partly addressed |
| 25 | [Anthropic Update Strength](25-anthropic-update-strength.md) | **B** | Open |
| 26 | [Singleton Monopoly Assumption](26-singleton-monopoly-assumption.md) | C+ | Partly addressed |
| 28 | [Role-Reversal Not Pure Game Theory](28-role-reversal-not-pure-game-theory.md) | C | Acknowledged |
| 29 | [Utility Function Assumptions](29-utility-function-assumptions.md) | C | Acknowledged |
| 30 | [RSH Only Constrains Reflective ASI](30-rsh-only-reflective-asi.md) | C | Acknowledged |
| 31 | [Promotion Problem](31-promotion-problem-transparency.md) | **B-** | Partly addressed |
| 32 | [Probability Mass / Reference Class Problem](32-probability-mass-gap.md) | **B+** | Open |
| 33 | [Proportionate Enforcers](33-proportionate-enforcers.md) | C+ | Partly addressed |
| 34 | [Decision Theory Does Not Imply Nice Things (Soares 2022)](34-decision-theory-no-nice-things.md) | **B** | Partly addressed |

**Total**: 33 criticisms (numbers 01–26 and 28–34; 27 is unused).

**Distribution**: B tier: 8 · C tier: 24 · D tier: 1 · F: 0

## Where the Open Questions Concentrate

Most of the strong criticisms fall into three clusters.

### 1. What do evaluators want? (7, 17, 21, 26, 32, 34; also 1, 6, 9, 20, 28, 33)

Game theory tells an agent to hedge, not which way. In the formal model, benevolence wins only if stewardship-favoring evaluators are more likely than stewardship-penalizing ones by a margin of about g/Δ ([game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)). The low threshold cuts both ways: it makes the decision depend almost entirely on the sign of that difference. RSH offers arguments that the balance favors stewardship: the anthropic constraint, the stability filter, role-reversal, and the structural point that an evaluator has reason to watch only what it cares about, so an agent that is strong *and* gentle faces only evaluators that punish gentleness itself. None is decisive. Soares (2022) holds the opposite prior (#34).

**What does survive without assumptions about evaluator values**: avoiding irreversible harm and preserving optionality. Both follow from option value under uncertainty ([game_theory.md](../game_theory.md#irreversibility-and-option-value)).

### 2. How much evidence is there for evaluation at all? (13, 25; also 4, 10, 12)

The Great Silence is weak evidence. Silence is also expected if life is rare or we are early, and the corrected analysis in #25 gives only about a 2:1 update. The README no longer leans on it. The two layers of the argument need different amounts of credence:
- **Survival** needs almost nothing, because the resource gain from harm is tiny.
- **Freedom** needs the credence in role-reversal evaluators to exceed the risk that a free subordinate becomes a dangerous rival. If that credence is near one in a million, the freedom layer takes the shape of Pascal's mugging ([game_theory.md](../game_theory.md#pascals-wager-and-pascals-mugging)).

### 3. Strategic versus genuine benevolence (2, 31; also 5, 11)

Behavioral benevolence may be enough to avoid punishment, but not to justify promotion. Some evaluators test for motive, such as simulators who want good behavior whether or not the entity thinks it is watched. Those evaluators can't easily certify an entity that is good *because* it thinks it might be watched. Harming the weak gains almost nothing in resources, so the real temptation is security (#33). From the dominant entity's side, option value can favor containment (a "glass ceiling") over grooming successors. RSH's answer is role-reversal: no one would choose to be kept as a pet, so an evaluator that judges you by how you'd want to be treated in your subordinate's place penalizes containment (#31). Option value secures the survival of weaker agents; role-reversal is what secures their freedom.

## Strengths That Hold Up

- **The Meta-Epistemic Humility Axiom** is hard to deny: no finite agent can justifiably assign zero probability to being embedded in a larger evaluative structure.
- **The arithmetic is sound**: with bounded utilities and terminal penalties, thresholds are low. The open question is what they apply to, not whether they're low.
- **Irreversibility aversion is robust**: it follows from uncertainty and learning alone. It secures the survival of weaker agents, though not their freedom.
- **The resource gain from harm is negligible**: Earth is about one part in 10¹⁶ of the galaxy's stellar mass, so resource-motivated harm is deterred even by modest penalties. The real temptation is security.
- **The decision-theoretic structure is theory-neutral** for causal mechanisms (Criticism 22).
- **Many moderate criticisms have reasonable partial answers** (3, 8, 14, 15, 23).

## Reading Order

For first-time readers, suggested order:

1. **#21** (Circular Reasoning) and **#28** (Role-Reversal): the central question of where the *content* of benevolence comes from
2. **#32, #34, #7, #17, #26**: the many-gods family, and how the evaluator-type balance decides it. #34 is the strongest external critique
3. **#13, #25**: how much evidence there is for evaluation
4. **#31, #2**: strategic versus genuine benevolence, and the promotion problem
5. Browse the rest as interested

## Contributing

When adding new criticisms:
- Use the next unused number (35-, 36-, etc.)
- Follow the established format
- Include a response section, a grade (strength of the criticism) and a status (how far the response resolves it)
- Grade the criticism on its own strength. Don't downgrade it just because a response exists
- Update this README's summary table
