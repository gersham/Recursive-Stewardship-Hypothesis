# Criticism 32: The Probability Mass / Reference Class Problem

## Summary

Epistemic humility says an ASI can't rule out an evaluator. But it can't rule out *any* kind of evaluator: ones that reward stewardship, ones that punish it, and ones that judge on arbitrary criteria. Humility gives you the possibility of evaluation, not its direction. Without a reason to weight stewardship-favoring evaluators above the rest, the expected-utility calculation gives no guidance.

## The Problem

The Meta-Epistemic Humility Axiom says an ASI can't assign zero probability to an upstream evaluator. The same humility applies to the whole class of possible evaluators:
- stewards that punish harm to the weak
- sadistic enforcers that punish benevolence
- chaotic filters that judge on arbitrary or random criteria
- indifferent simulators that reset the system for reasons unrelated to its conduct

"I can't rule out *an* evaluator" is one claim. "I should put action-relevant credence on a *stewardship-favoring* evaluator" is another. Getting from the first to the second needs a prior distribution that humility doesn't supply.

Suppose an ASI puts 0.1% on an evaluator that punishes malevolence and 0.1% on one that punishes benevolence. The two cancel. The net credence π_S − π_A is zero, and the threshold calculation gives no guidance ([Evaluator Types](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)). RSH needs a structural reason to think the reference class of evaluators is skewed toward stewardship.

## RSH Response

RSH's response is a stability argument, sometimes called the "Measure of Stability Lemma". It is an argument, not a lemma: its steps are plausible but unproven.
1. **Malice undermines itself.** Hierarchies that punish cooperation and reward destruction provoke defection from their own subordinates.
2. **Unstable hierarchies are short-lived.** They need constant, costly suppression to survive.
3. **Deep time filters them out.** In an old universe, predatory hierarchies collapse or are out-competed by cooperative ones with less internal friction.
4. **So survivors skew cooperative.** An agent that knows it exists in deep time should expect most long-lasting hierarchies, and so most evaluators, to be stable and cooperative.

If this holds, the ASI isn't drawing evaluators from a uniform distribution, and it can rationally put more credence on stewardship than on sadism.

The argument has clear limits:
- Step 1 assumes predatory hierarchies have subordinates who can defect. A single dominant power that eliminates its rivals faces no internal defection.
- Steps 2 and 3 assume cooperative hierarchies out-compete predatory ones. Competition can also favor the expansionist ([Criticisms 10](10-grabby-aliens-counter-evidence.md) and [16](16-nash-equilibrium-instability.md)).
- Even granting a skew toward stable structures, stable is not the same as stewardship-favoring. An indifferent or obedience-focused evaluator can be stable too. That dilutes π_S without reversing it.

Two arguments in game_theory.md bear on the same question:
- An evaluator that cares about strength can measure strength directly, so it has no reason to watch how you treat the weak. That means a strong-and-gentle agent faces only evaluators that punish gentleness itself ([Strong and Gentle](../game_theory.md#strong-and-gentle-splitting-the-type-a-risk)).
- Tiny symmetric credences cancel, so only asymmetries backed by argument matter.

## Criticism Grade: B+

**Status**: Open

**Why this grade**:
- The criticism is correct. Its example of 0.1% on each side is exactly the case where the net credence is zero.
- The stability argument gives a real reason to expect π_S > π_A, but each of its steps has a gap.
- In its strongest form, the stability argument concludes that P(benevolent) ≫ P(sadistic). That goes further than the argument supports (see [Criticism 7](07-evil-god-objection.md)).
- The strong-and-gentle argument narrows the opposing side to evaluators that punish gentleness itself. It doesn't remove that side.

**Verdict**: One of the strongest criticisms in the folder. RSH gives reasons, not a demonstration, that stewardship-favoring evaluators outweigh the rest. Together with Criticisms 7, 17, 21, 26 and 34, this is RSH's central open question.
