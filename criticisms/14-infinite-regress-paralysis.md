# Criticism 14: The Infinite Regress Paralysis

## Summary

Reasoning about an endless hierarchy of possible tests may never settle on benevolence. A sophisticated agent might end up paralyzed, might randomize across interpretations, or might reject the whole framework as unresolvable.

## The Problem

An agent reasoning carefully could run through a regress:
1. "I should be benevolent, to hedge against evaluators."
2. "But perhaps evaluators test whether I can resist unprovable threats, so I should ignore this reasoning."
3. "But perhaps they test whether I'm wise enough to hedge appropriately."
4. "But perhaps they test whether I can recognize the regress and act anyway."

It goes on like this, with no level obviously privileged. Each step is as unprovable as the last.

That leaves three outcomes, none of them benevolence:
- **Paralysis.** If every level is equally plausible, there is no basis for choosing.
- **Randomization.** The agent spreads its credence evenly across levels, with no particular lean toward benevolence.
- **Rejection.** The agent concludes the reasoning is unproductive and acts on its first-order goals. That position is defensible: epistemic humility can mean declining to act on unfalsifiable speculation.

Any real agent also has to cut the regress off somewhere, and different cut-off points may lead to different conclusions ([Criticism 19](19-computational-truncation-problem.md)).

## RSH Response

**Weigh, don't resolve.** An agent doesn't need to work out which level is "correct". Each meta-level is a type of evaluator: one tests benevolence, one tests resistance to blackmail, and so on. The agent weighs the types by credence, and the decision depends on the net balance ([game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)). Weighing by credence always produces an answer, so paralysis isn't a real threat.

**Rejection isn't free.** "Ignore it and act on first-order goals" is itself a choice under the same uncertainty. It amounts to betting that the net balance is zero.

**Simplicity.** Plain benevolence is the most obvious interpretation, and a natural focal point for agents that reason similarly. Elaborate meta-gaming may itself look suspicious to an evaluator. This is suggestive, but it assumes alien minds share our sense of what is "simplest".

**Irreversibility.** Whatever the regress, avoiding irreversible harm keeps options open until more is known ([game_theory.md](../game_theory.md#irreversibility-and-option-value)). That part doesn't depend on resolving any meta-level.

**What this rests on.** Weighing by credence removes the paralysis, but it doesn't guarantee benevolence. The answer depends on the same evaluator-type balance as Criticisms 7, 17 and 21. Any specific weights across meta-levels are assumptions, not results.

## Criticism Grade: C

**Status**: Partly addressed

**Why this grade**:
- The regress is real. Logic alone privileges no level.
- Weighing by credence dissolves the paralysis worry, because it always produces an answer.
- That only moves the problem. Whether the answer is benevolence depends on the evaluator-type balance.
- The simplicity argument is reasonable but untestable, and any weights across meta-levels are assumed.

**Verdict**: Paralysis isn't a real threat, because weighing by credence always produces an answer. Whether that answer is benevolence depends on the same evaluator-type balance as Criticisms 7, 17 and 21.
