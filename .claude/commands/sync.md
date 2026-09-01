---
description: Pull in the mentor's latest updates and rebase on top, keeping history linear
model: sonnet
---

This syncs with the mentor's repo (the `hall` remote) while keeping commit
history linear and only ever pushing to `origin` (the student's own
private repo). Never push to `hall`, and never run a plain
`git merge hall/main`, this project uses rebase to avoid merge commits.

Before anything else, confirm this copy of the repo actually has a `hall`
remote by running `git remote -v`. The mentor's own baseline copy has
only `origin` and nothing to sync from. If `hall` is missing, stop and
explain that in plain language instead of letting `git fetch hall` fail
with a raw error, and never invent or guess a URL for it.

1. Run `git status`. If there are uncommitted changes, stop and offer to
   commit them first (see AGENTS.md's git rules), or ask whether to stash
   them. Don't rebase over uncommitted work.
2. Run `git fetch hall`.
3. Run `git rebase hall/main`. This replays the student's commits on top
   of whatever the mentor added.
4. If a conflict comes up, do not silently pick a side. Explain in plain
   language what the mentor changed versus what the student changed in
   that spot, and ask which to keep (or whether to keep both). Get the
   two sides the right way round before explaining them: during a rebase
   the `HEAD` side of the conflict markers is the mentor's work being
   replayed onto, and the incoming side, labeled with the commit being
   applied, is the student's. That is the reverse of what the labels
   suggest to anyone used to merges. Check with
   `git show hall/main:<file>` if you are unsure, because telling a
   beginner that their own edit is their mentor's is worse than not
   explaining at all. Use `git rebase --continue` once it's resolved,
   `git rebase --abort` if the student wants to back out entirely.
5. Once the rebase finishes cleanly, run
   `git push --force-with-lease origin main`. This is safe here because
   it's the student's own solo private repo; nobody else could be relying
   on the commits being rewritten. That reasoning is the whole
   justification, so check it still holds: if `origin` is instead a
   shared or public repo that other people clone from, a force-push
   rewrites history out from under them. In that case stop and ask
   before running it.
6. Summarize what happened in plain language: what the mentor added,
   whether anything needed manual resolution, and confirm the student's
   own lesson folders and progress log came through intact.
