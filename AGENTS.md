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
