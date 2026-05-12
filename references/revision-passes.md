# Revision Passes

Use these passes to make revision behavior explicit. If the user does not specify a pass, apply `advisor pass`, `flow pass`, `sentence pass`, and `citation pass` in that order.

## Advisor Pass

Use when the user wants the paper, thesis, chapter, or section to satisfy an advisor or committee.

Check:

1. Does the section persuade rather than merely summarize completed work?
2. Is the main claim of the section visible before the details begin?
3. Does each paragraph have a reason to appear in its current position?
4. Are problem, limitation, proposed mechanism, and evidence connected as a chain?
5. Would a professor ask "so what?", "compared to what?", "where is the evidence?", or "is this overclaimed?"

Fix:

- Rewrite list-like paragraphs into claim -> mechanism -> evidence -> implication order.
- Add or sharpen topic sentences when the paragraph's job is hidden.
- Move or delete repetitive sentences that restate results without interpretation.
- Add baseline, condition, or validation scope when a claim is too broad.
- Mark missing evidence explicitly instead of inventing support.

Output:

- For review-only requests, report the highest-risk advisor objections first.
- For edit requests, make conservative in-place prose edits and then summarize remaining risks.

## Flow Pass

Use for chapter, section, introduction, related work, and conclusion review.

Check:

1. Does each paragraph have a single argumentative role?
2. Does the paragraph order follow context -> problem -> limitation -> gap -> proposed method -> evidence?
3. Does each paragraph transition into the next?
4. Does the section end by clarifying why the next section is needed?

Fix:

- Convert fact lists into causal chains.
- Move prior-work limitations before the proposed method.
- Add explicit bridge sentences only when the transition is abrupt.
- Avoid generic transitions that do not carry technical information.

## Sentence Pass

Use for polish, readability, advisor-facing drafts, and AI-like prose removal.

Check:

- Sentences longer than roughly 35-40 words.
- Multiple relative clauses in one sentence.
- Ambiguous `it`, `this`, `these`, or `they`.
- Over-polished transitions, em-dashes, inflated adjectives, or decorative phrasing.
- Repeated sentence structures across adjacent sentences.

Fix:

- Split long sentences.
- Replace vague pronouns with explicit nouns.
- Keep one evidence-sensitive claim per sentence.
- Prefer concrete mechanisms over abstract summary language.

## Citation Pass

Use when checking claim support, related work, or technical background.

Flag:

- Claims about prior work limitations.
- Numerical claims.
- Hardware cost, power, area, timing, and dataset claims.
- Claims using words such as `state-of-the-art`, `robust`, `efficient`, `orders of magnitude`, `practical`, or `deployable`.

Fix:

- Verify that a citation already supports the claim.
- Add a citation only if the key exists and the source is known.
- If evidence is missing, leave a precise citation-needed note.
- Avoid raw numeric citation text; use the project citation format.

## Defense Pass

Use before advisor review, prelim/main defense, or committee-facing drafts.

Check:

- Does any claim overstate validation scope?
- Are silicon, FPGA, simulation, synthesis, and dataset evidence clearly separated?
- Is the baseline comparison fair and explicitly named?
- Are limitations placed in Chapter 5 or the appropriate conclusion rather than hidden?
- Would a reviewer ask for a missing baseline, missing ablation, or missing citation?

Fix:

- Add scope phrases such as `under the evaluated conditions`, `in this synthesis comparison`, or `relative to the fixed baseline`.
- Convert universal claims into evaluated-scope claims.
- Surface missing validation as a limitation or future-work item.

## LaTeX-Safe Pass

Use when editing `.tex` files directly.

Preserve:

- Citation keys.
- Equation labels and references.
- Figure/table labels and references.
- Technical notation.
- Numerical results.
- Acronym definitions.

Change only prose unless the user explicitly asks for technical or structural edits.
