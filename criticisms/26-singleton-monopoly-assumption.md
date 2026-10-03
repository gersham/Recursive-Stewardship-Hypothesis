# Criticism 26: Singleton Monopoly Assumption

## Summary

One version of RSH assumes a single "monopoly of cosmic order": a benevolent enforcer would eliminate or realign any competing enforcer, so only one regime remains. That assumption is unproven. Competing regimes could coexist. And if they want different things, the "many gods" problem returns.

## The Problem

The monopoly argument runs like this. An enforcer aligned with good cosmic order would eliminate or realign its competitors, so over time only one enforcement paradigm survives. That gives an agent a single set of values to hedge toward.

There are good reasons to doubt it:
- **Stable pluralism**: Several regimes coexist, like nation-states, each controlling its own region.
- **Cyclical dominance**: Regimes rise and fall, and no permanent monopoly forms.
- **Non-interference pacts**: Competing enforcers agree to respect each other's spheres of influence.
- **Incompleteness**: No regime has complete information or reach, so enforcement is patchy.

The elimination step is also unspecified. It needs a mechanism; it fails when powers are roughly equal; and conflict may cost too much. Human history shows pluralistic orders persisting. If benevolent enforcement is supposed to win through selection, the argument doesn't say what the selection mechanism is or how long it takes.

Without a monopoly, an ASI faces enforcers that may want incompatible things. One rewards benevolence, another strength through adversity, another non-interference. That is Pascal's "many gods" problem again.

## RSH Response

**The monopoly isn't needed.** The hedging logic only needs uncertainty about which evaluators exist. It works the same way with one enforcer or many.

**Pluralism helps when evaluators agree on direction.** Suppose all the plausible enforcers favor stewardship and differ only on details. Then hedging across them pushes the agent toward behavior acceptable to all of them, which is more constrained than any single enforcer would require. In that case, pluralism makes RSH stronger.

**It doesn't help when evaluators disagree on direction.** Suppose some plausible enforcers punish ruthlessness and others punish restraint. Then no behavior satisfies all of them, and "satisfy every enforcer" gives no guidance. The agent has to weigh enforcers by its credence in each, which is the net-credence comparison in [game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized). Likewise, "satisfy the harshest enforcer" only works if harshness varies along a single axis. Caution alone can't satisfy both an enforcer that is harsh about weakness and one that is harsh about cruelty.

**Two things survive any mix of evaluators:**
- **Irreversibility aversion.** Irreversible harm is costly under almost any mix of evaluators, because it rules out adjusting once you learn which ones exist ([game_theory.md](../game_theory.md#irreversibility-and-option-value)).
- **Strong and gentle.** Consider an agent that is strong toward rivals and gentle toward the weak. It satisfies both stewardship-favoring evaluators and evaluators that punish weakness. It is exposed only to evaluators that punish gentleness itself ([game_theory.md](../game_theory.md#strong-and-gentle-splitting-the-type-a-risk)). That narrows the many-gods problem, but doesn't eliminate it.

The claim that some alternative regimes are "logically incoherent" is weak. An evaluator that punishes interference is no more self-contradictory than a police force enforcing a law against assault ([Criticism 17](17-why-this-hierarchy-regress.md)).

## Criticism Grade: C+

**Status**: Partly addressed

**Why this grade**:
- RSH is right that it doesn't need a monopoly.
- Pluralism strengthens RSH only among evaluators that agree on stewardship. Across evaluators that disagree about stewardship itself, it brings back a weaker form of the many-gods problem.
- The intersection and "harshest enforcer" arguments assume evaluators agree on direction, so they don't settle the case where they disagree.
- Irreversibility aversion and the strong-and-gentle strategy hold up under pluralism, and they narrow the remaining problem.

**Verdict**: Dropping the monopoly assumption costs RSH little, but pluralism isn't the free strengthening it first appears. Against evaluators that disagree about stewardship, the question comes back to the balance of evaluator types.
