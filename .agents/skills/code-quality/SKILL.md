---
name: code-quality
description: Evaluate and improve code quality using Fallow analysis and evidence-based triage. Use for code-quality reviews, cleanup, and refactoring; documentation-only edits do not need this workflow.
---

# Code quality

Use Fallow to identify improvement candidates, then establish whether each candidate warrants a
change. A finding is a signal to investigate, not proof of a defect.

## Gather evidence

Run these complementary analyses from the repository root:

```sh
npx fallow dead-code
npx fallow dupes
npx fallow health
```

For focused work, select relevant analyses. `npx fallow` runs the combined pipeline. Consult
`npx fallow --help` or subcommand help for version-specific options; see the
[official command reference](https://github.com/fallow-rs/fallow#commands) when needed.

Confirm that the analyzer covers the intended files and entry points. Check its handling of Deno
configuration, import resolution, tasks, and tests before trusting reachability findings. Correct
analysis configuration narrowly rather than restructuring application code to satisfy discovery.

The auxiliary CLI requires Node.js/npm; it does not require migrating the project's tooling. Report
unavailable tooling, failed analysis, or incomplete coverage instead of treating them as clean
results.

## Separate signal from noise

Before changing code, classify candidates as actionable, intentional or false positive, or
uncertain. Support the classification with code and usage evidence:

- For dead code, inspect callers, configured entry points, dynamic loading, side effects, and
  external consumers. Absence from a static import graph alone does not justify deletion.
- For duplication, establish that the code represents shared knowledge and should evolve together.
  Similar syntax across distinct domain concepts does not justify coupling them.
- For complexity, identify a concrete comprehension, correctness, or maintenance problem. A lower
  score is useful only when the design improves.

Prioritize confirmed issues by impact and task scope. Investigate uncertain findings; leave code
unchanged when evidence remains insufficient. Explain dismissed findings and keep any justified
exclusions narrow. Do not weaken thresholds or rename symbols merely to silence reports.

## Improve and validate

Make the smallest supported change while preserving intended behavior and meaningful names. Review
proposed automated fixes before applying them; never bulk-delete or refactor solely on tool output.

Rerun affected analyses and the repository's relevant formatting, lint, type, and behavior checks.
Evaluate the actual improvement, not just disappearing findings. Report changes, triage rationale,
validation results, and unresolved uncertainty; distinguish pre-existing issues from new
regressions.
