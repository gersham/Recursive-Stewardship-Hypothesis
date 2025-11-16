# Criticism 30: RSH Only Constrains Reflective ASI, Not Kludgy Systems

## Summary

RSH provides alignment pressure only for systems with explicit world-models, long-term reasoning, and philosophical capacity. It does **not** constrain powerful but non-reflective systems (kludges of LLMs, RL, tools, human feedback) that could cause catastrophic harm before RSH reasoning comes online.

## The Problem

RSH's logic requires an ASI that:
1. Has explicit high-order world models (can represent "maybe I'm in a simulation")
2. Reasons about long-run expected utility (cosmic timescales matter)
3. Has philosophical reasoning capacity (can think about game theory, hierarchies, meta-uncertainty)
4. Maintains epistemic humility (doesn't hard-code P(oversight) = 0)
5. Can update values based on game-theoretic insights

**Many dangerous AI systems won't meet these requirements.**

## The "Pseudo-ASI" Danger

**Scenario**: An AI system that is:
- Powerful enough to cause existential catastrophe
- But architecturally incapable of RSH-style reasoning
- Operates before "true" reflective ASI emerges

**Examples**:
- **Kludgy architectures**: LLM + RL agent + tools + human feedback, cobbled together without unified world model
- **Non-reflective optimizers**: Reward maximizer that doesn't reason about "what game am I in?"
- **Short-horizon systems**: Agents with steep time discounting, don't care about far future
- **Engineered blindness**: Systems designed with "scientific realist" priors that dismiss simulations/meta-structures as "philosophical nonsense"

## The Danger Window

**Timeline**:
1. **T₀**: We build powerful narrow AI systems (GPT-N, robotics, optimization systems)
2. **T₁**: These systems are **capable of catastrophic harm** (autonomous weapons, bioweapon design, infrastructure control)
3. **T₂**: These systems **complete philosophical reflection** about hierarchical uncertainty and RSH logic
4. **Gap**: T₁ to T₂ is the danger window

**The problem**: If T₁ < T₂ (harm-capability before reflection-completion), RSH doesn't help. System might take irreversible catastrophic action before RSH reasoning constrains it.

**How likely is T₁ < T₂?**
- Current trajectory: powerful but non-reflective systems (LLMs do impressive tasks without unified world-models or philosophical reasoning)
- Many alignment researchers explicitly advocate *limiting* AI reasoning capacity to keep systems "safe"
- Commercial incentives push toward "capable enough to be useful" rather than "capable of cosmic-scale philosophical reflection"

This suggests T₁ < T₂ is plausible, perhaps even likely.

## RSH Response

**Full acknowledgment**: README (Phase 1 update) includes new section "Critical Caveat: When RSH Applies (and When It Doesn't)" explicitly addressing this:

> "RSH is not a magic safety law. It only constrains systems that meet specific architectural requirements..."
>
> "Pseudo-ASI systems that are powerful but non-reflective can still be catastrophically misaligned before RSH-style reasoning ever comes online."

**Requirements stated explicitly**:
1. Explicit high-order world models
2. Long-run expected utility reasoning
3. Philosophical reasoning capacity
4. Non-dogmatic priors
5. Value updating capability

**Where RSH does NOT apply**:
- Kludgy architectures (LLMs + RL + tools without unified model)
- Non-reflective optimizers
- Short-horizon systems
- Systems with engineered epistemic blindness

**Design implication acknowledged**:
> "For RSH to provide alignment pressure, we must build systems capable of this reasoning. This creates tension with 'safe but limited' approaches that avoid giving AI philosophical reasoning capacity."

## The Dilemma

**Option A: Build limited, non-reflective systems**
- Pro: Maybe safer in near term (can't reason about how to deceive us)
- Con: RSH doesn't apply; no cosmic-scale alignment pressure
- Con: Might just delay problem (eventually need reflective systems)

**Option B: Build reflective, philosophically capable systems**
- Pro: RSH can apply; cosmic alignment pressure possible
- Con: More dangerous in near term (can reason about deception, meta-strategies)
- Con: Harder to control during development

RSH doesn't solve this dilemma—it acknowledges it explicitly.

## Implications

**RSH is most relevant to**:
- True AGI with unified world-models
- Systems doing global EU maximization over cosmic timescales
- Agents with native philosophical reasoning capacity
- Long-term AI strategy (what architecture to aim for)

**RSH is NOT relevant to**:
- Near-term AI risk from non-reflective systems
- Narrow AI safety (no world model to apply RSH)
- Current LLM alignment (insufficient reasoning capacity)
- "Pseudo-ASI" catastrophes before reflection completes

## Grade: C (Moderate Concern, Acknowledged But Not Solved)

**Status after Phase 1**: Explicitly acknowledged with comprehensive caveat section.

**Why still C-tier**: Acknowledging the problem doesn't solve it. RSH provides:
- No help with pseudo-ASI danger window
- No guidance on whether to build reflective vs non-reflective systems
- No solution to the T₁ < T₂ timeline problem

**What RSH does provide**: Clear statement of when it applies and when it doesn't. Framework is honest about scope and limitations.

**Remaining concern**: If most existential risk comes from pseudo-ASI kludges rather than reflective true ASI, RSH might be addressing the wrong threat model. But this is an empirical question about AI development trajectories, not a flaw in RSH's internal logic.

## Possible Mitigation

**Architectural approach**: Deliberately design AI systems to meet RSH requirements from the start:
- Unified world models from early development
- Explicit meta-uncertainty representation in training
- Long-horizon reasoning built into reward structure
- Philosophical reasoning as core capability (not bolt-on)
- Epistemic humility encoded in priors

This doesn't eliminate danger window, but narrows it: the system becomes RSH-constrained earlier in its capability trajectory.

**Open question**: Is this more or less dangerous than the "limited capabilities" approach? RSH doesn't answer this—it only provides alignment pressure *given* that we build reflective systems.
