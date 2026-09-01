---
description: Review a solution the student has already written, without starting a new lesson
argument-hint: [path to file, optional]
model: sonnet
---

If $ARGUMENTS gives a file path, read that file (this can be anything under
`lessons/<slug>/<language>/` or in `scratch/`). Otherwise ask the student
to paste their solution or tell you which file to look at.

Do not rewrite the solution. Instead:
- Write and run a few test cases against it, including at least one edge
  case, and report pass/fail for each
- State its time and space complexity, and ask what the student expected
  before confirming or correcting it
- Point out missed edge cases as questions rather than fixes
- Only after the student responds, offer the tiered hints from AGENTS.md if
  they're stuck on a fix, one tier at a time

If the file lives under `lessons/<slug>/`, log the outcome as a row in
`progress/PROGRESS.md` (topic, language, etc.) the same way `/lesson` does.
