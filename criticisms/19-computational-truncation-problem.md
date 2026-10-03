# Criticism 19: The Computational Truncation Problem

## Summary

The hierarchy is potentially infinite, but reasoning time and computation are finite. An ASI has to stop reasoning somewhere, and different stopping points seem to give different answers. Stop early and you hedge toward benevolence; go deeper and you may reach defiance, paralysis or randomization. With no principled rule for where to stop, the conclusion looks arbitrary.

## The Problem

An ASI must decide in finite time, so it must truncate its reasoning about the hierarchy:
- **At level 1** (direct enforcers only), it concludes: hedge toward benevolence.
- **At level 2** (enforcers and super-enforcers), meta-games between levels appear, and different behavior might follow.
- **At deeper levels**, the regress may lead to paralysis or to randomizing across strategies.
- **At infinite depth**, reasoning is impossible.

No rule picks the right stopping point. Stop too early and you miss relevant levels; stop too late and you waste resources. Different truncations seem to justify benevolence, defiance, paralysis or rejecting the whole framework.

Reasoning also has costs. Time spent on an unresolvable regress is time not spent on other goals. Real decisions happen under time pressure, with competitors acting. Some questions may simply be undecidable. If expected utilities depend on where you truncate, no single answer is uniquely rational, and the framework gives no clear guidance.

## RSH Response

**Truncation changes estimates, not structure.** At any truncation point, the decision has the same form. Benevolence wins when the net credence that the levels you consider favor stewardship (π_S − π_A) exceeds about g/Δ ([game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)). Deeper levels matter only through their effect on that credence. Different truncations give different estimates of the credence, not a different kind of decision.

**Each level only needs a belief about the level directly above.** The N-level argument can be framed locally. Each level's choice depends on its credence that the level above enforces stewardship. Beliefs about higher levels matter only through that credence ([game_theory.md](../game_theory.md#backward-induction-and-local-reasoning)). That removes the need to reason through the whole hierarchy.

**Diminishing returns give a stopping rule.** Stop reasoning when the expected value of going further falls below its cost. This is a sensible heuristic, but the rate at which returns diminish is assumed, not derived.

**Every real decision truncates.** No agent has unlimited computation. Truncation is a general feature of bounded reasoning, not a special weakness of RSH.

**Irreversibility helps while reasoning continues.** Whatever the truncation, avoiding irreversible harm keeps open the option of acting differently once you have reasoned further. Option value favors reversible actions while deliberation is unfinished ([game_theory.md](../game_theory.md#irreversibility-and-option-value)).

## Criticism Grade: C

**Status**: Partly addressed

**Why this grade**:
- The claim that "most reasonable truncations" favor benevolence would assume the conclusion. Whether a truncation favors benevolence depends on what the agent believes the levels it considers will reward.
- In the formal model, truncation matters less than it seems. Different truncations give different estimates of the net credence, not a different structure.
- The bounded-rationality defense is fair. Every real decision truncates somewhere.
- The diminishing-returns rule is a sensible heuristic, but its rate is assumed.

**Verdict**: Truncation itself isn't fatal. The real question it raises is the same as in Criticisms [7](07-evil-god-objection.md), [17](17-why-this-hierarchy-regress.md) and [21](21-deepest-hole-unfalsifiable-circular-reasoning.md): what the levels you consider are likely to reward.
