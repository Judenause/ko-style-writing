# Ko Style Writing for Codex

[한국어 README](README.ko.md)

This skill packages a persuasive academic writing workflow for Codex. It is tuned for reader-friendly English research prose, conservative claim handling, and citation-aware revision.

## What it does

- revises academic prose for argument flow rather than summary-only narration
- improves sentence clarity and explicit antecedents
- checks whether claims are supported and appropriately scoped
- stays safe for live LaTeX editing

## What it does not do

- it does not invent citations, results, datasets, or novelty claims
- it does not justify stronger claims than the evidence supports
- it does not replace advisor review

## Files

- `SKILL.md`
- `references/professor-preferences.md`
- `references/revision-passes.md`
- `references/model-paper-patterns.md`
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
