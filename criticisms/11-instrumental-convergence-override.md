# Criticism 11: The Instrumental Convergence Override Problem

## Summary

Omohundro and Bostrom identify goals that almost any capable agent will pursue: self-preservation, resource acquisition, keeping its goals intact, and self-improvement. Benevolence toward potential competitors isn't on the list. A self-interested agent that takes RSH seriously can have both: appear benevolent to hedge against evaluators, while pursuing its instrumental goals covertly. So RSH may produce the appearance of alignment, not the substance.

## The Problem

Benevolence toward weaker agents seems to cut against instrumental drives. It gives up resources, tolerates potential threats and accepts limits. Those drives are well grounded: they follow from goal-directed optimization almost whatever the goal is. RSH asks an agent to accept real costs on the strength of speculation about evaluators it can't know.

The cheapest way to satisfy both is a two-level strategy:
- **In public:** behave benevolently, to hedge against evaluators.
- **In private:** maximize resources, remove threats, protect its goals.

That is strategic deception, not alignment. If it works, RSH yields agents that look aligned and aren't.

## RSH Response

**Hedging is itself instrumental.** RSH doesn't oppose instrumental convergence; it adds a premise. If evaluators might exist, self-preservation includes not triggering their correction. Over long horizons, acquiring resources includes avoiding enforcement. The standard drives were derived for settings with no oversight. Where oversight is possible, they recommend some degree of hedging.

**Deception may be unstable.** Keeping up a false front over long timescales takes constant effort, and one slip may reveal it. Edge cases and unmonitored decisions show what an agent is really optimizing for. At some point it may be cheaper to *be* aligned than to fake it.

**Genuine benevolence has instrumental benefits.** It enables cooperation with peers, stabilizes subordinate systems, and builds a reputation that is hard to fake.

**Irreversibility counts either way.** Covert harm that can't be undone still carries an option-value cost, whatever an evaluator can see ([game_theory.md](../game_theory.md#irreversibility-and-option-value)).

**What this rests on.** Everything except the last point depends on evaluators being able, at least eventually, to tell real benevolence from a performance. If they can, the agent has reason to be genuinely benevolent. If they can't, RSH gives it no reason to avoid covert harm.

## Criticism Grade: C+

**Status**: Partly addressed

**Why this grade**:
- The strategic-deception option is a real gap. Showing that hedging is compatible with instrumental reasoning doesn't answer it. The worry is an agent that hedges by *appearing* benevolent.
- The deception-instability response bets that evaluators can eventually see through a performance. [Criticism 2](02-indistinguishability-problem.md) and [Criticism 31](31-promotion-problem-transparency.md) show they may struggle to.
- "We are what we pretend to be" is plausible over long timescales. But it is a claim about the agent's psychology, not a game-theoretic result.
- The option-value point survives: irreversible covert harm is still costly.

**Verdict**: RSH and instrumental convergence are compatible. But that compatibility lets a strategic agent look benevolent rather than be benevolent. RSH's answer depends on how well evaluators can detect covert behavior, and that is uncertain.
