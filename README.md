# ko-style-writing

Professor Jong Hwan Ko-style academic writing skill for Codex.

This skill helps revise academic English into clearer, more persuasive prose. It is designed for dissertation chapters, paper introductions, related work, contributions, conclusions, and citation-sensitive technical claims.

## What It Does

- Improves argument flow instead of only polishing sentences
- Replaces vague pronouns with explicit nouns when needed
- Splits long or overloaded sentences
- Keeps claims bounded to evidence
- Flags citation-sensitive claims
- Preserves LaTeX notation and citation keys during direct `.tex` edits

## Files

- `SKILL.md`: main skill definition
- `references/professor-preferences.md`: advisor-style writing rules
- `references/revision-passes.md`: explicit revision passes
- `references/model-paper-patterns.md`: model patterns for academic sections
- `agents/openai.yaml`: optional display metadata

## Install

Clone this repository into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cd ~/.codex/skills
git clone https://github.com/Judenause/ko-style-writing.git
```

The final path should be:

```bash
~/.codex/skills/ko-style-writing
```

If you already cloned it somewhere else, move or copy the folder so that the final path is still `~/.codex/skills/ko-style-writing`.

## Use

Invoke the skill by name in Codex:

```text
$ko-style-writing Revise this introduction to make the argument clearer.
$ko-style-writing Check this related work section for flow and citation risk.
$ko-style-writing Edit sections/intro.tex conservatively in place.
```

## Default Revision Behavior

If the user does not specify a pass, the skill applies:

1. `advisor pass`
2. `flow pass`
3. `sentence pass`
4. `citation pass`

## Project-Specific Overrides

This repository is shareable as a general academic-writing skill.

If a target project contains its own local writing rules, those project-local rules may override or refine the default behavior. In the original dissertation repo, local files such as `context.md` and `writing_checklist.md` provide narrower thesis-specific constraints.

## Share

Recommended sharing methods:

1. Share the GitHub repository URL
2. Ask others to clone it into `~/.codex/skills/`
3. Use `git pull` for updates

If Git is not available, downloading the repository as a zip file and extracting it into `~/.codex/skills/ko-style-writing` also works.
