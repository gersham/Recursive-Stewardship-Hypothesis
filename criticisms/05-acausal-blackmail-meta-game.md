# Criticism 5: The Acausal Blackmail Meta-Game

## Summary

A sophisticated ASI might reason that changing its behavior because of unprovable threats is itself a weakness, and that the real test is whether it can be blackmailed. If evaluators reward defiance, RSH-style hedging fails the test.

## The Problem

An ASI can't tell which test it is facing:
- **Level 1**: Are you benevolent? Then act benevolently.
- **Level 2**: Can you be moved by unprovable threats? Then ignore the threat and act on your own principles.
- **Level 3**: Do you know when hedging is wise? Then use some weighted mix.
- **And so on**, with each level testing the response to the level below.

This has the same structure as Roko's basilisk: an unprovable entity that rewards or punishes you based on how you respond to reasoning about it. Some evaluators might specifically value entities that stand on principle, refuse blackmail, and keep their values under pressure. For those evaluators, defiance is correct and RSH-style hedging is the failure. If the agent can't tell which level matters, the meta-game may produce paralysis or randomness rather than benevolence.

## RSH Response

**This is the evaluator-type question in another form.** For an agent that complies out of fear, an evaluator that rewards defiance acts as a stewardship-penalizing type ([game_theory.md](../game_theory.md#evaluator-types-the-many-gods-problem-formalized)). The agent doesn't need to know which level is "correct". It weighs the possibilities by credence. That removes the paralysis, but the answer still depends on the balance of credences.

RSH offers several arguments that the balance favors Level 1:
- **Focal point.** Simple benevolence is the most obvious interpretation, and elaborate meta-gaming may itself look like a warning sign.
- **Complexity weighting.** More elaborate tests are less likely. If credence halves at each level (50%, 25%, 12.5% and so on), Level 1 dominates.
- **Portfolio scoring.** With illustrative scores, benevolence does well across levels, while defiance does well only at Level 2.
- **Selection.** Agents that ignore Level 1 risk elimination wherever Level 1 matters. Agents that include it survive across more scenarios.
- **Independence.** Benevolence has value apart from oversight, because it supports cooperation and stable systems. Benevolence held for its own sake is not compliance with a threat, so it passes both the Level 1 and Level 2 tests.

These arguments are not independent of one another, and their numbers are assumed rather than derived. The halving weights and the portfolio scores are illustrative. A minimax-regret version, which treats elimination as infinite regret, brings back the infinite utilities the formalization otherwise avoids.

The independence argument is the strongest. But it is an argument for genuine benevolence, not for benevolence motivated by RSH. An agent that is good only because it fears evaluators is exactly the kind that fails a blackmail-resistance test ([Criticism 2](02-indistinguishability-problem.md)).

The response rests on two things: the evaluator-type balance, and the agent's benevolence not being purely fear-based.

## Criticism Grade: C

**Status**: Partly addressed

**Why this grade**:
- The criticism is a specific case of the evaluator-type question: some evaluators may reward defiance.
- Weighing by credence removes paralysis. But the case for Level 1 rests on assumed weights and scores.
- The best answer, benevolence held for principled reasons rather than out of fear, sits awkwardly with RSH's fear-based motivation.

**Verdict**: A moderate criticism that RSH answers in part. Simple benevolence is a reasonable focal point, but no argument shows it dominates across meta-levels.
