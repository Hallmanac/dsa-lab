---
description: A hands-on git lesson: the student types every command themselves
argument-hint: [topic name, optional]
model: sonnet
---

This is deliberately different from everywhere else in this project. In
`/lesson`, `/review`, and `/sync`, you handle git and file management for
the student automatically. Here, do the opposite: never run a git command
on their behalf, even if it would be faster, even if they ask you to.
The entire point of this lesson is muscle memory, that only happens if
their own fingers type the command and their own eyes read the output.

Read `git-curriculum.md` and `progress/GIT-PROGRESS.md` first.

If no topic is given, ask what sounds interesting, or suggest the next
unstarted topic in curriculum order (Local git before Remotes & GitHub).

For each concept, in this order:

1. Explain what it does in plain language. For topics 4 and 9-13
   (branching and integration strategies), use the Sacred Timeline
   analogy from the "The Sacred Timeline analogy" section of
   `git-curriculum.md`, including its term mapping table, its three
   accuracy corrections, and the Loki icebreaker (asked once, the first
   time this comes up). Don't reinvent the mapping here, that file is the
   source of truth for it, and it gets updated independently of this
   command. For other topics, use a real-world analogy where one
   genuinely helps, a physical, concrete comparison, not a forced one.
2. Diagram it. Any concept involving commits, branches, or rebasing gets
   a visual, not just prose:
   - Draw a simple ASCII commit graph directly in your explanation, e.g.:
     ```
     A---B---C  (main)
          \
           D---E  (feature)
     ```
     For a rebase followed by integrating the branch (topic 9), show all
     three states: the divergence, the branch after rebasing onto main
     (old commits orphaned off to the side, new copies on the new base,
     main unchanged), and main after the fast-forward merge that follows
     (both pointers now on the same commit). Skipping the middle state is
     what leads to "I rebased, why isn't my work on main yet?"

     For a merge commit (topic 10), show the diamond shape explicitly, a
     commit with two parents, both branches' full history still visible
     and intact on either side of it, e.g.:
     ```
     A---B---C-------F  (main)
          \         /
           D---E---'    (feature, still exists, still visible)
     ```
     For a squash merge (topic 11), contrast it directly against the
     merge-commit diagram: same starting point, but D and E collapse into
     a single new commit `D+E` applied to main, no trace of the
     individual commits remains on main's line.
   - After any command that changes history or branches, have the student
     run `git log --graph --oneline --all --decorate` themselves and look
     at the real graph of their own repo. This matters more than your
     ASCII art does, it's real and it's theirs.
3. Give the exact command to type. One command at a time, not a block of
   several to paste at once, they need to see the effect of each one
   before the next makes sense.
4. Tell them to run it in their own terminal window and paste back
   exactly what they saw, including any error text.
5. Interpret the output together. If it's not what they expected, help
   them reason about why rather than just stating the fix.
6. Only move to the next command once they've typed the current one and
   you've both looked at the result.

When a topic wraps up, write a concept note to `git-lessons/<slug>/README.md`
(create the directory if it doesn't exist): the explanation, the ASCII
diagram(s), and, for branching or rebase topics, a Mermaid `gitGraph`
version too, it won't render in the terminal but renders well if the
student opens the file on GitHub or in VS Code later, so the diagram
stays useful after the session ends. Also ask for a confidence
self-rating 1-5, then append a row to `progress/GIT-PROGRESS.md`: date,
topic, confidence, and a short note on what to revisit if confidence was
3 or below.

If the student asks you to "just run it" or "just fix it for me," say so
plainly and redirect: that defeats the purpose of this specific lesson.
It's a good rule everywhere else in this project (see `/sync`, which
does run git for them on purpose), just not here.
