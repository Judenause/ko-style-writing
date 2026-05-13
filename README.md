# Ko Style Writing for Codex

[한국어 README](README.ko.md)

This skill packages a persuasive academic writing workflow for Codex. It is tuned for reader-friendly English research prose, conservative claim handling, and citation-aware revision.

## What it does

- revises academic prose for argument flow rather than summary-only narration
- improves sentence clarity and explicit antecedents
- checks whether claims are supported and appropriately scoped
- stays safe for live LaTeX editing
- integrates useful general academic-writing checks such as research-question clarity, literature-review synthesis, hedging, and peer-review response structure

## What it does not do

- it does not invent citations, results, datasets, or novelty claims
- it does not justify stronger claims than the evidence supports
- it does not replace advisor review

## Files

- `SKILL.md`
- `references/professor-preferences.md`
- `references/revision-passes.md`
- `references/model-paper-patterns.md`
- `references/usage-examples.md`
- `agents/openai.yaml`

## Install

### Option 1: Clone into `~/.codex/skills`

```bash
mkdir -p ~/.codex/skills
cd ~/.codex/skills
git clone git@github.com:Judenause/ko-style-writing.git
```

### Option 2: Clone elsewhere and symlink

```bash
git clone git@github.com:Judenause/ko-style-writing.git
mkdir -p ~/.codex/skills
ln -s "$(pwd)/ko-style-writing" ~/.codex/skills/ko-style-writing
```

The final installed path should be:

```text
~/.codex/skills/ko-style-writing
```

## Use

Invoke the skill by name in Codex:

```text
$ko-style-writing Revise this introduction so it reads like a persuasive argument.
$ko-style-writing Check this chapter for claim strength and citation gaps.
$ko-style-writing Apply a flow pass and sentence pass to this LaTeX section.
```

## When to use it

Use `ko-style-writing` for actual research prose:

- dissertation or paper chapter revision
- abstract, introduction, related work, conclusion, contribution, or limitation drafting
- literature-review synthesis that should not read like a paper-by-paper list
- citation-sensitive technical claims in LaTeX
- advisor, committee, defense, or reviewer-facing polish
- peer-review responses that need a direct, non-defensive tone

Use a generic academic-writing workflow only for broad research-process tasks such as literature-search planning, research-question design, study design, or citation-manager setup. If the task turns into writing the actual prose, switch back to `ko-style-writing`.

## Detailed examples

The full example set is in `references/usage-examples.md`. Common invocations:

```text
[$ko-style-writing] 6. body.tex Chapter 3을 교수님 관점에서 리뷰해줘.
수정하지 말고 흐름, 설득력, 근거 부족, committee 공격 포인트만 우선순위로 알려줘.
```

```text
[$ko-style-writing] 6. body.tex Section 1.3을 직접 고쳐줘.
길이는 크게 늘리지 말고, 논문 나열처럼 보이는 부분을 설득 흐름으로 바꿔줘.
```

```text
[$ko-style-writing] related work가 paper-by-paper 나열처럼 보여.
카테고리별로 묶고 각 카테고리의 남는 한계가 우리 방법으로 이어지게 고쳐줘.
```

```text
[$ko-style-writing] 이 문단에서 citation이 부족하거나 overclaim인 부분만 찾아줘.
수정안은 짧게만 제안해줘.
```

## Default revision behavior

If the user does not specify a pass, the skill applies:

1. `advisor pass`
2. `flow pass`
3. `sentence pass`
4. `citation pass`

## Revision passes

- `advisor pass`: checks persuasion quality and committee defensibility
- `flow pass`: repairs paragraph and section logic
- `sentence pass`: improves readability and explicitness
- `citation pass`: audits evidence support
- `defense pass`: tightens claim scope under scrutiny
- `latex-safe pass`: preserves LaTeX-sensitive structures

## Project-specific overrides

This repository is shareable as a general academic-writing skill.

If a target project contains its own local writing rules, those project-local rules may override or refine the default behavior. In the original dissertation repo, local files such as `context.md` and `writing_checklist.md` provide narrower thesis-specific constraints.

## Public note

This public README intentionally omits personal-name branding. The skill is described in functional terms so it can be shared without exposing advisor identity in the repository landing page.
