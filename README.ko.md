# Codex용 Ko Style Writing

[English README](README.md)

이 스킬은 Codex에서 설득력 있는 academic writing revision을 수행하기 위한 패키지입니다. 읽기 쉬운 영어 연구 문장, 보수적인 claim 처리, citation-aware revision에 초점을 둡니다.

## 하는 일

- 단순 요약이 아니라 argument flow 중심으로 academic prose를 다듬음
- 문장 명확성과 explicit antecedent를 개선함
- claim이 적절한 근거와 범위를 갖는지 점검함
- live LaTeX 편집에서도 비교적 안전하게 동작함
- research question 명확성, literature review synthesis, hedging, peer-review response 구조 같은 범용 academic-writing 기준을 필요한 만큼 통합함

## 하지 않는 일

- citation, result, dataset, novelty claim을 꾸며내지 않음
- 근거보다 강한 claim을 정당화하지 않음
- advisor review를 대체하지 않음

## 파일 구성

- `SKILL.md`
- `references/professor-preferences.md`
- `references/revision-passes.md`
- `references/model-paper-patterns.md`
- `references/usage-examples.md`
- `agents/openai.yaml`

## 설치 방법

### 방법 1: `~/.codex/skills` 아래로 clone

```bash
mkdir -p ~/.codex/skills
cd ~/.codex/skills
git clone git@github.com:Judenause/ko-style-writing.git
```

### 방법 2: 다른 위치에 clone 후 심볼릭 링크

```bash
git clone git@github.com:Judenause/ko-style-writing.git
mkdir -p ~/.codex/skills
ln -s "$(pwd)/ko-style-writing" ~/.codex/skills/ko-style-writing
```

최종 설치 경로는 다음이어야 합니다.

```text
~/.codex/skills/ko-style-writing
```

## 사용 예시

Codex에서 아래처럼 호출하면 됩니다.

```text
$ko-style-writing Revise this introduction so it reads like a persuasive argument.
$ko-style-writing Check this chapter for claim strength and citation gaps.
$ko-style-writing Apply a flow pass and sentence pass to this LaTeX section.
```

## 언제 쓰면 좋은가

`ko-style-writing`은 실제 research prose를 다룰 때 씁니다.

- dissertation 또는 paper chapter revision
- abstract, introduction, related work, conclusion, contribution, limitation 작성
- 논문별 나열이 아니라 category 중심으로 묶어야 하는 literature-review synthesis
- LaTeX 안의 citation-sensitive technical claim 점검
- advisor, committee, defense, reviewer-facing polish
- direct하면서 방어적으로 들리지 않는 peer-review response 작성

generic academic-writing workflow는 literature-search planning, research-question design, study design, citation-manager setup처럼 넓은 연구 프로세스 조언에만 쓰는 편이 좋습니다. 실제 문장을 쓰거나 고치는 순간에는 다시 `ko-style-writing`을 쓰면 됩니다.

## 자세한 호출 예시

전체 예시는 `references/usage-examples.md`에 있습니다. 자주 쓰는 형태는 아래와 같습니다.

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

## 기본 revision 동작

사용자가 pass를 따로 지정하지 않으면 다음 순서로 적용합니다.

1. `advisor pass`
2. `flow pass`
3. `sentence pass`
4. `citation pass`

## Revision passes

- `advisor pass`: 설득력과 committee defensibility 점검
- `flow pass`: 문단과 섹션 논리 보수
- `sentence pass`: 가독성과 명시성 개선
- `citation pass`: 근거와 citation 지원 점검
- `defense pass`: 심사 상황에서 claim 범위 조정
- `latex-safe pass`: LaTeX 민감 구조 보존

## 프로젝트별 override

이 저장소는 일반 academic-writing skill로 공유할 수 있도록 구성되어 있습니다.

대상 프로젝트에 로컬 writing rule이 따로 있으면, 그 프로젝트 규칙이 기본 동작을 override하거나 더 좁게 제한할 수 있습니다. 원래 dissertation 저장소에서는 `context.md`, `writing_checklist.md` 같은 파일이 더 구체적인 thesis 규칙을 제공합니다.

## 공개용 메모

이 공개용 README는 의도적으로 교수님 실명 브랜딩을 포함하지 않습니다. 저장소 랜딩 페이지에서 advisor identity를 노출하지 않도록 기능 중심으로 설명합니다.
