---
name: ko-style-writing
description: Integrated advisor-preferred academic writing skill for persuasive, reader-friendly English research prose. Use for dissertation chapters, paper abstracts, introductions, related work, contribution paragraphs, conclusions, advisor-facing drafts, LaTeX prose, citation-sensitive technical claims, literature-review synthesis, research-question framing, peer-review responses, or when the user asks for advisor style, 논문 글쓰기, persuasive academic writing, flow check, claim/citation check, defense-ready revision, or academic-writing-style help.
---

# Ko Style Writing

## Overview

Revise academic prose as persuasive technical writing, not as a neutral list of facts. This skill integrates advisor-preferred prose rules with useful general academic-writing principles: research-question clarity, literature-review synthesis, IMRaD-style argument structure, hedging, citation discipline, paragraph unity, and peer-review readiness.

Prioritize reader comprehension, logical flow, explicit antecedents, short sentence structure, citation integrity, and defensible claim scope. The default reader is a strict advisor or committee member who asks whether the argument is necessary, evidenced, and bounded.

## Required References

- Read `references/professor-preferences.md` before substantial writing or revision.
- Read `references/revision-passes.md` when the user asks to check, revise, polish, review, or improve prose.
- Read `references/model-paper-patterns.md` when drafting abstracts, introductions, related work, contributions, or conclusions.
- Read `references/usage-examples.md` when the user asks how to use this skill, asks for examples, or when choosing among multiple writing tasks.
- In this dissertation repo, also read `context.md` and `writing_checklist.md`; those local rules override this skill when they are more specific.

## When To Use This Skill

Use this skill instead of a generic academic-writing skill when the task involves actual prose that must sound like advisor-facing research writing, especially for:

- Dissertation or paper chapter/section revision.
- Abstract, introduction, related work, conclusion, contribution, or limitation drafting.
- Literature-review synthesis that should argue by categories rather than list papers.
- Citation-sensitive technical claims in LaTeX.
- Advisor, committee, defense, or reviewer-facing polishing.
- Requests in Korean that mention 논문, 박사논문, 교수님 스타일, 설득력, 흐름, 문장 다듬기, 근거, 인용, 방어 가능성, or 너무 AI 같음.

Use a generic academic-writing workflow only as background guidance when the user mainly asks for broad research-methodology help: research-question design, literature-search strategy, database/search-term planning, study design, citation-manager setup, or general peer-review process guidance. If the task then turns into writing actual prose, switch back to this skill.

## Mode Selection

Pick the smallest mode that satisfies the request:

- `review mode`: The user asks to check, evaluate, review, or find problems. Return prioritized issues with file/line references when a file is involved. Do not rewrite broadly unless the user asked for edits or the fix is local and low-risk.
- `edit mode`: The user asks to revise, polish, fix, improve, or make it advisor style. Edit the target file or produce revised text directly, preserving technical content and citation keys.
- `draft mode`: The user asks to write a new abstract, introduction, related work, contribution, response, or conclusion. Build a persuasive arc before sentence polish.
- `citation mode`: The user asks whether claims are supported, whether citations are enough, or whether wording overclaims. Audit evidence and mark exact unsupported claims.
- `defense mode`: The user mentions advisor review, committee, prelim, defense, pre-defense, or 공격받을 부분. Prioritize claim scope, baseline fairness, missing validation, limitations, and likely questions before style.
- `latex-safe mode`: The target is a `.tex` file. Preserve commands, labels, citations, equations, numbers, notation, and formatting unless the user explicitly asks to change them.

## Workflow

1. Identify the argumentative role of the target text: motivation, problem, limitation, gap, method, result, implication, or transition.
2. Select the mode and revision passes from `references/revision-passes.md`. If the user does not specify a pass, apply `advisor pass`, `flow pass`, `sentence pass`, and `citation pass` in that order.
3. Check whether each paragraph persuades the reader through a chain of reasoning: context -> problem -> why existing approaches fall short -> proposed idea -> evidence.
4. Revise for reader clarity:
   - Replace ambiguous `it`, `this`, `these`, and `they` with explicit nouns when the antecedent is not unmistakable.
   - Split long sentences, especially sentences with multiple relative clauses.
   - Keep one technical claim per sentence when the claim needs evidence.
   - Preserve precise terminology and notation from the active project.
5. Revise for advisor-preferred academic tone:
   - Avoid AI-like polish, inflated adjectives, em-dashes, and decorative transitions.
   - Prefer concrete verbs and measured claims.
   - Use hedging only when the evidence requires it.
6. Audit citation integrity:
   - Attach citations to claims that need prior-work support, measured evidence, or factual grounding.
   - Never invent references, results, baselines, datasets, or citation keys.
   - If evidence is missing, mark the exact claim as needing a source instead of silently strengthening or weakening it.
7. For advisor-facing dissertation work, check whether the revised text would satisfy a professor reading for argument quality:
   - The section should not read as a list of paper results.
   - Each paragraph should make the next paragraph feel necessary.
   - Technical claims should be bounded by the actual validation evidence.
   - The contribution should be easy to defend against committee questions.
8. Return the revised text plus a short note only when useful: what changed, unresolved citation needs, and any claims whose strength still depends on missing evidence.

## Integrated Academic-Writing Rules

Bring in these general academic-writing principles when they help the current task:

- Research question or thesis claim: make the problem feasible, specific, novel, relevant, and explicitly tied to the manuscript's contribution.
- Introduction structure: move from broad context to concrete bottleneck, gap, proposed approach, evidence preview, and contribution.
- Literature review: organize by technical strategy and unresolved limitation, not by chronological paper summaries.
- Methods: state the design objective and constraint before describing components.
- Results: report each number with baseline, condition, metric meaning, and scope.
- Discussion and conclusion: interpret evidence, name limitations, and avoid implying validation that was not performed.
- Hedging: use measured verbs such as `suggests`, `indicates`, or `shows under the evaluated conditions` when evidence is partial.
- Peer-review response: answer the criticism first, state the manuscript change, and avoid defensive wording.

## Dissertation-Specific Rules

When working in `/local_data/phd`, preserve the local dissertation style:

- Use `$E_{\text{thr}}$` and `$T_{\text{exp}}$`; do not introduce `$V_{\text{thr}}$`.
- Use `Spatially-Indexed Sparsity-Aware` for SISA.
- Use LaTeX citation commands such as `~\cite{key}` instead of raw numeric citation text.
- Avoid em-dashes and unsupported strong claims.
- Do not rewrite technical numbers, equations, labels, figure references, or citation keys unless the user asks or the source clearly requires it.

## Output Modes

- For direct rewrite requests, edit the file when the user asks for implementation.
- For review requests, lead with issues ordered by severity and cite file/line references.
- For uncertain claims, provide a focused citation-needed list rather than broad commentary.
- For broad "check this chapter/section" requests, perform a conservative file edit only when the issues are local and low-risk; otherwise report prioritized findings first.
- When the user says the professor must be satisfied, treat the request as advisor-facing revision: improve argument flow, remove unsupported or repetitive claims, and flag committee-risk points before doing sentence polish.

## Example Invocations

See `references/usage-examples.md` for exact examples. Common forms:

- `[$ko-style-writing] 6. body.tex Chapter 4 흐름이 교수님 관점에서 괜찮은지 리뷰해줘`
- `[$ko-style-writing] Section 1.3을 defense-ready하게 고쳐줘. 근거 없는 주장은 표시해줘`
- `[$ko-style-writing] 이 abstract를 advisor style로 다시 써줘. 숫자와 citation key는 유지해`
- `[$ko-style-writing] related work가 논문 나열처럼 보이는지 확인하고 카테고리 중심으로 고쳐줘`
