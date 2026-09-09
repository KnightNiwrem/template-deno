# Project instructions

- Follow software engineering principles: keep responsibilities cohesive, dependencies explicit, and
  interfaces small. Prefer simple designs over speculative abstractions; share code when it
  represents shared knowledge, not merely similar syntax.
- Always use meaningful names that accurately express domain concepts, responsibilities, and
  behavior. Human readability is a top priority. Names also carry semantics that LLMs use to infer
  intent and relationships, so treat them as contracts. Use consistent vocabulary, include units or
  state when relevant, and rename identifiers when their meaning changes.
- Make types, invariants, side effects, and error handling explicit. Validate external input at
  boundaries; do not hide problems with unchecked assertions or suppressions.
- Keep changes scoped to the task and preserve unrelated work. Test observable behavior and relevant
  edge cases, and update documentation when behavior or workflows change.
- Follow repository configuration and existing conventions for Deno tooling, formatting, linting,
  and type checking. Run checks appropriate to the change and report failures or checks not run.
- For code-quality reviews and refactoring, use the
  [code-quality skill](.agents/skills/code-quality/SKILL.md).

## Content placement

Select content by the file's readers and purpose. Before adding prose or comments, identify who
reads the file and what they need to understand, decide, or do. Include only information that serves
those needs.

- README: Help users understand the project, its current capabilities, and how to use it; help
  contributors get started. Future-facing content should be limited to concise descriptions of
  intended capabilities or improvements useful to those readers. Keep implementation plans, task
  breakdowns, and agent execution instructions elsewhere.
- Code and comments: Communicate current intent, behavior, contracts, and constraints. Explain
  relevant design choices through their present rationale. Keep experiment logs, abandoned
  approaches, and change narratives elsewhere unless the historical detail is essential to
  understanding the current code.
- AGENTS.md: Include durable instructions an agent needs in every fresh session within its scope.
  Put instructions needed only for particular tasks or workflows in skills; retain only the minimal
  routing guidance needed to find and invoke them.
- PRs, commits, and decision records: Preserve relevant change context, alternatives considered, and
  decision history.

Before finishing, review added prose and comments against the destination's purpose. Remove content
that merely recounts the change conversation or reassures its participants. When past work reveals a
current constraint, explain the constraint directly.
