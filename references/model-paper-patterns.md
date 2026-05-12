# Model Paper Patterns

These patterns are derived from the supplied Professor Ko lab papers:

- `ASPDAC_2026_PAWR_final.pdf`
- `DATE_2025___Low_Rank.pdf`
- `ISLPED_2026_FREEMAP.pdf`
- `ISLPED2023___PAIRS.pdf`

Use the patterns as structural guidance. Do not copy wording from the papers.

## Abstract Pattern

Use a compact persuasive arc:

1. Field context and why the platform matters.
2. Specific technical obstacle.
3. Limitation of prior approaches.
4. Proposed technique with one or two named mechanisms.
5. Quantitative evidence with comparison target.
6. Final implication in terms of efficiency, reliability, accuracy, or deployability.

Good abstracts do not merely announce the method. They explain the obstacle that makes the method necessary.

## Introduction Pattern

A strong introduction often follows this sequence:

1. Broad trend: demand for efficient hardware, deployment, reliability, or compression.
2. Platform promise: why IMC/PIM/ReRAM/event sensing is attractive.
3. Concrete bottleneck: dataflow inconsistency, array underutilization, idle rows, peripheral overhead, noise, or reliability degradation.
4. Prior-work grouping: correction/retraining/remapping/pruning/mapping, etc.
5. Limitation of each group in terms of hardware overhead, dataflow mismatch, accuracy loss, or deployment practicality.
6. Gap statement: the missing combination that prior work does not provide.
7. Proposed approach: named method and the key mechanism.
8. Evidence preview: measured improvements and comparison baselines.
9. Contribution bullets: each bullet maps to one problem or evidence item.

## Related Work Pattern

Classify prior work by design strategy, not by paper-by-paper chronology.

For each category:

- State what the category solves.
- State the remaining limitation.
- Connect the limitation to the proposed gap.

Avoid ending related work with a weak summary. End by making the reader see why the proposed design point is unoccupied.

## Method Pattern

Before describing components, state the design objective and constraint.

Then introduce each component with:

1. What problem this component solves.
2. How it solves the problem.
3. Why the design avoids the prior limitation.
4. What cost or tradeoff remains.

This structure is more persuasive than describing blocks in diagram order.

## Results Pattern

Report results as evidence for claims:

- Pair each number with the baseline and condition.
- Explain why the metric matters.
- Separate accuracy/reliability evidence from hardware-cost evidence.
- Avoid vague words such as `significant` unless the magnitude is stated.

## Contribution Bullet Pattern

Use contribution bullets to make the argument easy to audit:

- Identify a neglected or unresolved problem.
- Present a method or architecture that addresses it.
- Report the validation evidence and comparison scope.

Each bullet should carry one clear contribution. Do not mix problem discovery, mechanism, and multiple result types in one long bullet.
