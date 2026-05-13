# Usage Examples

Use this reference when the user asks how to invoke the skill, when selecting the right mode, or when writing help text for future users.

## Quick Rule

Use `ko-style-writing` for actual research prose. Use a generic academic-writing workflow only for broad research-process advice. When both apply, start from `ko-style-writing` and borrow only the relevant general academic-writing checks.

## When To Use Which Writing Workflow

| User intent | Use | Why |
| --- | --- | --- |
| Revise a dissertation chapter or paper section | `ko-style-writing` | Needs advisor-style argument flow, LaTeX safety, and claim boundaries. |
| Check whether a section is persuasive | `ko-style-writing` review mode | The main risk is logic, synthesis, and committee objections. |
| Polish AI-like academic prose | `ko-style-writing` sentence pass | The user wants natural advisor-facing prose, not generic polish. |
| Verify whether claims need citations | `ko-style-writing` citation mode | Citation keys and evidence scope must not be invented. |
| Prepare for advisor or defense review | `ko-style-writing` defense mode | Prioritizes attack points, overclaiming, validation scope, and baseline fairness. |
| Plan a literature search strategy | Generic academic-writing workflow | This is research-process guidance rather than prose revision. |
| Design a research question from scratch | Generic academic-writing workflow, then `ko-style-writing` for final prose | First clarify the study shape, then write persuasively. |
| Write reviewer responses | `ko-style-writing` draft mode | The response must be direct, evidence-backed, and non-defensive. |

## Invocation Patterns

### Review A Chapter Without Editing

```text
[$ko-style-writing] 6. body.tex Chapter 3을 교수님 관점에서 리뷰해줘.
수정하지 말고 흐름, 설득력, 근거 부족, committee 공격 포인트만 우선순위로 알려줘.
```

Expected behavior:

- Read the target chapter and local thesis rules.
- Report the highest-risk logic and evidence problems first.
- Use file and line references when possible.
- Stop after the requested chapter unless the user asks to continue.

### Edit A Section In Place

```text
[$ko-style-writing] 6. body.tex Section 1.3을 직접 고쳐줘.
길이는 크게 늘리지 말고, 논문 나열처럼 보이는 부분을 설득 흐름으로 바꿔줘.
```

Expected behavior:

- Edit conservatively in the `.tex` file.
- Preserve citations, labels, equations, notation, and numbers.
- Convert list-like paragraphs into context -> problem -> limitation -> gap -> proposed approach.
- Verify with a lightweight diff or LaTeX-safe check, and run a build when the edit is broad enough to risk compilation.

### Abstract Or Introduction Draft

```text
[$ko-style-writing] 이 논문 abstract를 다시 써줘.
필수 내용은 유지하고, advisor style처럼 문제 -> 한계 -> 제안 -> 정량 결과 -> 의미 순서로 정리해줘.
```

Expected behavior:

- Use the model-paper abstract pattern.
- Avoid decorative wording and broad novelty claims.
- Keep evidence and comparison scope visible.
- Preserve supplied numbers and terms.

### Related Work Synthesis

```text
[$ko-style-writing] related work가 paper-by-paper 나열처럼 보여.
카테고리별로 묶고 각 카테고리의 남는 한계가 우리 방법으로 이어지게 고쳐줘.
```

Expected behavior:

- Organize prior work by design strategy or limitation.
- Explain what each category solves and what remains unsolved.
- Avoid citation stacking without synthesis.
- Do not invent papers or citation keys.

### Citation And Claim Audit

```text
[$ko-style-writing] 이 문단에서 citation이 부족하거나 overclaim인 부분만 찾아줘.
수정안은 짧게만 제안해줘.
```

Expected behavior:

- Flag exact claims that need evidence.
- Identify risky words such as `first`, `practical`, `robust`, `efficient`, or `demonstrates`.
- Suggest scope-bounded wording when evidence is partial.
- Do not add unknown citation keys.

### Defense-Ready Revision

```text
[$ko-style-writing] Chapter 5를 defense-ready하게 봐줘.
교수님이나 committee가 공격할만한 claim, future work scope, limitation 표현을 먼저 고쳐줘.
```

Expected behavior:

- Separate direct evidence from future work.
- Make validation scope explicit.
- Surface limitations without weakening the contribution unnecessarily.
- Keep future work narrow when the project rules define a narrow scope.

### Peer-Review Response

```text
[$ko-style-writing] reviewer comment에 대한 response를 써줘.
먼저 답을 하고, manuscript에서 무엇을 바꿨는지 말하고, 방어적으로 들리지 않게 해줘.
```

Expected behavior:

- Start with a direct answer to the reviewer.
- Describe the concrete manuscript change.
- Use evidence and scope, not emotional language.
- Avoid claiming changes that were not made.

## Output Expectations

For review-only tasks:

- Start with findings, ordered by severity.
- Include file and line references when local files are used.
- Separate evidence-backed findings from inference.

For edit tasks:

- Make the edit directly when the target file is available.
- Keep changes narrow and reversible.
- Summarize changed scope, remaining citation needs, and verification.

For draft tasks:

- Return polished prose first when the user asks for text.
- Add a short note only for claim boundaries, missing evidence, or optional alternatives.

For Korean requests:

- Answer in Korean unless the requested manuscript prose itself should be English.
- Preserve user-imposed formatting constraints such as one-chapter-at-a-time review or no hyphen characters.
