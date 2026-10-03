# Criticism 22: Decision Theory Dependence

## Summary

RSH might only work under contested decision theories such as FDT or TDT, which reason about logical correlations between agents. In that case, an ASI built on standard causal decision theory (CDT) might reject the hedging argument. RSH would then be much less general than it claims.

## The Problem

Decision theories differ in what they take an agent's choice to influence:

- **CDT** counts only an action's causal consequences. A CDT agent might reason: "My behavior doesn't cause an enforcer to exist, so why hedge?"
- **EDT** treats an action as evidence about the world. It may support RSH, but EDT is itself controversial.
- **FDT, TDT and UDT** treat a choice as the output of a decision procedure that other agents may model or share. They support RSH-style reasoning most naturally, but they are not widely accepted.

If RSH holds only under that last group:
- an ASI built on CDT might never reach the benevolence conclusion
- RSH becomes "rational only under a non-standard decision theory"
- its value as a general alignment mechanism shrinks

There is also a meta-question. An early ASI may not know which decision theory is correct. Does RSH require it to commit to one?

## RSH Response

**The causal mechanisms work under every major theory.** In the base game ([game_theory.md](../game_theory.md#decision-theory-variants)), the agent's choice has no effect on whether an evaluator exists. Punishment, though, is a causal consequence of that choice: if an enforcer exists, malevolence causes it to respond. That is ordinary CDT reasoning about an uncertain state of the world. A CDT agent doesn't need its choice to cause the enforcer to exist. It only needs to weigh what its choice would cause if one does.

There is no Newcomb-like structure here, so EDT, FDT and UDT compute the same expected utilities as CDT. Cosmological enforcers, and simulators that observe behavior, therefore don't depend on a contested decision theory.

**The acausal mechanism is different.** The README's acausal mechanism needs FDT/UDT-style reasoning. It also needs the agent's decision procedure to be correlated with the evaluator's. Some evaluators *predict* the agent's policy, such as simulators that model it, or acausal partners. With those, FDT and UDT can favor benevolence where CDT would not. That mechanism does depend on the decision theory.

**On meta-uncertainty.** If benevolence is optimal under every theory, it is optimal under any mixture of them. That adds no extra support. It only shows that disagreement among theories causes no trouble when they all give the same answer. And "benevolence is safe under every theory" holds only in the two-type model. Once stewardship-penalizing evaluators are admitted, benevolence has a downside too ([game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)).

## Criticism Grade: D+

**Status**: Addressed for the causal mechanisms; open for the acausal mechanism

**Why this grade**:
- For cosmological enforcers and observing simulators, the choice of decision theory makes no difference. The argument is ordinary expected-utility reasoning about uncertain states of the world.
- The acausal mechanism really does depend on FDT/UDT, and on the agent's and evaluator's decision procedures being correlated. The criticism is fair there.
- Uncertainty about which decision theory is correct is neutral. It is not a further argument for benevolence.
- RSH's real uncertainty lies elsewhere: in the balance of evaluator types, not in the decision theory.

**Verdict**: A weak criticism of RSH's causal mechanisms, and a fair one of its acausal mechanism.
