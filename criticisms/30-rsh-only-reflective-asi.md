# Criticism 30: RSH Only Constrains Reflective ASI, Not Kludgy Systems

## Summary

RSH constrains only systems that can actually run its reasoning: agents whose world models include possible higher-level structure, who plan over long horizons, and who can reason abstractly about their situation. It does nothing to powerful systems that don't reflect. Those could cause irreversible harm before any RSH-style reasoning happens.

## The Problem

For RSH to constrain an AI, the AI has to:
1. Represent possible structures above it, such as simulators, older civilizations or acausal partners
2. Care about long-run expected utility, not just near-term reward
3. Reason abstractly about game theory, hierarchies and its own uncertainty
4. Keep non-zero credence in oversight, rather than hard-coding it to zero
5. Update its behavior or values in response to that reasoning

Many dangerous systems won't meet these conditions:
- **Kludged architectures.** Language models, RL agents, tools and human feedback combined without a unified world model.
- **Non-reflective optimizers.** Reward maximizers that never ask what game they're in.
- **Short-horizon systems.** Agents that discount the future steeply.
- **Engineered blindness.** Systems built with priors that dismiss simulation or oversight hypotheses as nonsense.

This opens a danger window. Call T₁ the point at which a system can cause catastrophic harm, and T₂ the point at which it reasons its way to RSH. If T₁ comes before T₂, RSH offers no protection in between.

The current trajectory makes that plausible:
- capable systems are arriving without unified world models
- commercial incentives favor "useful enough" over "reflective"
- some safety approaches deliberately limit reasoning capacity

## RSH Response

RSH accepts this as a limit on its scope. The README says so in [Appendix B](../README.md#b-key-assumptions-and-scope). RSH constrains only systems that can run the reasoning, and powerful non-reflective systems can take irreversible actions before any reflection happens.

That leaves a real dilemma:
- **Build limited, non-reflective systems.** They may be safer in the near term, because they can't reason about deception. But RSH doesn't apply to them, and limiting reasoning may only delay the problem.
- **Build reflective systems.** RSH can then apply. But such systems are more dangerous during development, because they can also reason about deception and strategy.

One mitigation is to build systems that meet RSH's requirements from the start: unified world models, explicit uncertainty about their own situation, long-horizon reasoning, and priors that don't rule out oversight. That narrows the window but doesn't close it.

The mitigation has a cost. Long-horizon, goal-directed systems are also the profile behind standard concerns about AI power-seeking. The README's design advice ("give it long time horizons") notes this tension under [Architectural Requirements](../README.md#architectural-requirements). RSH's recommendation and those concerns pull in opposite directions, and the framework doesn't settle which matters more.

## Criticism Grade: C

**Status**: Acknowledged

**Why this grade**:
- The scope limit is real, and RSH states it openly.
- Stating it doesn't solve it. RSH offers no protection during the danger window, and no guidance on whether to build reflective or non-reflective systems.
- Its main mitigation, building long-horizon reflective systems early, runs into the power-seeking concern.
- Whether most risk comes from kludged systems or reflective ones is an empirical question about how AI develops. It is not a flaw in RSH's internal logic.

**Verdict**: RSH is honest about where it applies. If most existential risk comes from powerful systems that never reflect, RSH is addressing the wrong threat model, and nothing in the framework can change that.
