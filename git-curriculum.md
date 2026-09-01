# Git Curriculum

Separate from the algorithms curriculum. This is about building real git
muscle memory, so every command here gets typed by the student in their
own terminal, never run for them. See `.claude/commands/git-lesson.md`.

## Local git

1. What version control actually solves (`01-why-git`)
2. Local basics: `init`, `status`, `add`, `commit` (`02-local-basics`)
3. Viewing history: `log`, `diff`, `show` (`03-history`)
4. Branching: `branch`, `switch` (`04-branching`)
5. Undoing things: `restore`, `reset`, `revert` (`05-undoing-things`)
6. `.gitignore` and housekeeping (`06-gitignore`)

## Remotes & GitHub

7. Working with remotes: `remote`, `fetch`, `pull`, `push` (`07-remotes`)
8. GitHub basics: repos, the `gh` CLI, cloning (`08-github-basics`)

## Integration strategies

9. Fast-forward merges: rebase, then integrate (`09-fast-forward-merge`)
10. Merge commits: true three-way merges (`10-merge-commits`)
11. Squash merging, briefly (`11-squash-merge`)
12. Resolving a real conflict (`12-conflicts`)

## Wrapping up

13. Forks and pull requests, conceptually (`13-forks-and-prs`)

## The Sacred Timeline analogy

Central teaching metaphor for topics 4 and 9-13, built around the Loki
Disney+ series (TVA, Sacred Timeline). `/git-lesson` should use this
consistently across those topics rather than one-off comparisons, tweaking
wording as needed but keeping the mapping intact.

**First time only:** the first time this analogy comes up (normally at
topic 4, branching), ask the student: "Have you seen the Loki series on
Disney+?" If yes, lean into specifics, they'll get the references. If no,
make a brief, warm, joking big deal out of it ("stop what you're doing
and go watch season one" energy), then immediately give a 30-second
primer so the analogy still lands today, don't actually make them go
watch a show before continuing the lesson, the bit is the point, not a
real gate. Ask this once. Check whether earlier rows already exist in
`progress/GIT-PROGRESS.md` for topic 4 or later before asking again, if
so, skip the icebreaker and just use the analogy directly.

**Before topic 10 (merge commits) specifically:** ask a second, separate
question, don't assume "seen Loki" from topic 4 covers this: "Have you
seen season 2, or just season 1?" The merge-commit framing below is
written spoiler-free by default. Only reach for anything more specific
to the season 2 finale if the student confirms they've actually seen it.
Same rule applies to yourself in any future session, not just to the
student: check before going deeper into finale specifics with anyone,
including Brian.

**Term mapping:**

| Git concept | Sacred Timeline framing |
|---|---|
| `main` branch | The Sacred Timeline |
| creating a branch | A Nexus Event, a variant timeline splits off |
| commits on a branch | Events unfolding along that variant |
| rebasing a branch onto main | The variant gets reset onto the Sacred Timeline's current moment, replayed fresh from where things actually stand now |
| fast-forward merge (after rebase) | The variant is fully reconciled into the Sacred Timeline, indistinguishable from it going forward |
| merge commit (non-fast-forward) | Unlike pruning, nothing about the variant gets erased, its full history stays permanently visible, joined to the Sacred Timeline exactly where the two reconnect (spoiler-free; there's a place later in the show this lines up with closely, leave it there unless they've confirmed they've seen it) |
| squash merge | The TVA doesn't need every individual moment preserved, just the outcome, the variant's whole arc gets filed as one condensed case record |
| merge conflict | A Nexus event collision, two timelines claiming the same moment differently, needs a Hunter (the developer) to adjudicate |
| deleting an already-merged branch | Retiring a case file once its variant is already part of the record, nothing is lost, the label's just no longer needed |
| forks / pull requests | A variant proposed for formal review before it's written into the official record |

**Three corrections to keep it technically accurate, don't let the fun
version drift into the wrong mental model:**

1. **Pruning ≠ what merging does.** The show's pruning erases a timeline
   (season 1 premise, fine to reference once the topic-4 icebreaker
   confirms they know it). Git never discards a branch's work by merging
   or rebasing it. A fast-forward integrates it entirely; a merge commit
   preserves it forever, visibly. Only a redundant branch *label* ever
   gets deleted, and only after its commits are already safely part of
   main. Frame fast-forward as "reconciled," not "pruned."
2. **Rebase creates new commits, it doesn't reposition old ones.** The
   "reset onto the current moment" framing should map to real new commits
   with new IDs being built on the new base, with the old ones orphaned
   off to the side, not to an existing commit just being pointed at
   differently. Diagram this, don't just say it.
3. **Rebasing a branch onto main and getting that branch's work onto main
   are two different steps.** Rebase only moves the branch; main's
   pointer doesn't move and main has no idea the branch exists yet.
   Getting the work onto main is a separate fast-forward merge
   afterward. Skipping this distinction is what causes "I rebased, why
   isn't my work on main yet?"

## Notes

- Work roughly in order within each group: Local git, then Remotes &
  GitHub, then Integration strategies.
- Topic 9 (fast-forward merges) is a good moment to point back at how
  `/sync` already does this automatically in this project, now the
  student gets to see why, not just that it works.
- Branching and integration topics (4, 9-13) should lean on diagrams more
  than words, see the diagramming rules in
  `.claude/commands/git-lesson.md`. A rebase especially needs to be
  drawn, not just described.
