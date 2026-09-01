# Algorithms & Data Structures Lab

A self-paced way to learn algorithms and data structures using Claude Code
as your tutor, across three languages: Python, Java, and C#.

## What this repo is

This is the shared baseline your mentor maintains. You don't work in it
directly. You make your own private copy, do all your learning there, and
this repo stays the place updates come from. Setting that copy up is the
first step below.

## Start here

You don't need Git, the GitHub CLI, or Claude Code installed, and you
don't need to have used a terminal before. The only thing you need up
front is a paid Claude plan (Pro, Max, Team, or Enterprise).

1. Install the [Claude app](https://claude.ai/download) and sign in.
2. Make an empty folder where you keep projects, for example
   `Documents/Code`.
3. In the app, start a new **Code** session and point it at that folder.
4. Paste the prompt below in as your first message.

```
I'm brand new to this and I don't have any developer tools set up yet.
Please get me set up, and explain what you're doing as you go, in plain
language. Assume I know nothing about git.

1. Check whether I have git and the GitHub CLI (gh) installed. If either
   is missing, tell me how to install it for my operating system, then
   wait for me to do it.
2. Check whether gh is signed in, using `gh auth status`. If it isn't,
   walk me through `gh auth login` and let me do the browser sign-in
   myself. Do not try to enter my password or any codes for me.
3. Ask me for my name and the email address on my GitHub account, and
   set up my git identity if it isn't already configured.
4. Clone https://github.com/Hallmanac/dsa-lab.git into a folder called
   dsa-lab inside the folder we're in now.
5. Rename that clone's remote from `origin` to `hall`.
6. Create a new PRIVATE GitHub repo for me called dsa-lab using the
   GitHub CLI, set it as `origin`, and push everything to it.
7. When that's all done, tell me how to open a new Code session inside
   the dsa-lab folder, since that's where my lessons will happen.

Stop and ask me whenever you're unsure about something.
```

Claude takes it from there. It checks what you're missing, walks you
through installing it, makes your own private copy of this repo, and
tells you what to do next. Expect it to pause and ask you to do a few
things yourself, like signing in to GitHub in your browser.

[`START-HERE.md`](./START-HERE.md) is the same walkthrough with more
detail, including what to expect while it runs and what to do if
something errors. If you'd rather type the setup commands by hand,
[`GETTING-STARTED.md`](./GETTING-STARTED.md) has the manual version.

**Already set up?** Open a Code session pointed at your own `dsa-lab`
folder and type `/lesson`.

## Staying in sync

Your mentor may push updates to their repo (new lessons, fixed commands).
Just run `/sync` and Claude Code pulls them in for you. It rebases rather
than merges, so history stays linear instead of filling up with merge
commits, and it only ever pushes to your own private repo, never back to
your mentor's.

## What you can learn

You don't need to already know what to ask for. Here's the full list,
roughly easiest/most fundamental first. Just tell Claude which one sounds
interesting, or say you're not sure and let it suggest what's next.

**Core**
Big-O notation, arrays & strings, two pointers, sliding window, hashing
(hash maps & sets), sorting, binary search, recursion, linked lists,
stacks & queues, trees, heaps / priority queues, graphs (BFS & DFS),
backtracking, dynamic programming (1D and 2D), greedy algorithms.

**Advanced / less common**
Tries, union-find, segment trees & Fenwick trees, topological sort,
shortest-path algorithms, bit manipulation, advanced string matching,
bitmask DP, monotonic stacks, interval scheduling.

The full version with more detail lives in `curriculum.md`.

## Commands

- `/lesson`: start a new lesson, or point at one like
  `/lesson hash maps python`
- `/review`: get a solution checked without starting a new lesson
- `/progress`: see a summary of what you've covered, in which languages,
  and what's next
- `/sync`: pull in anything your mentor added since last time
- `/git-lesson`: learn git itself, hands-on (see below)

## Learning git itself

Everywhere else in this lab, Claude Code handles git for you so you can
focus on algorithms. `/git-lesson` is the opposite, on purpose: you type
every command yourself in your own terminal, Claude Code won't run them
for you even if you ask. That's the whole point, it's how the muscle
memory actually forms. It's a separate track from the algorithms
curriculum, see `git-curriculum.md` for the topic list.

## What's in here

```
lessons/<slug>/          one folder per topic, e.g. lessons/03-two-pointers/
  README.md              the concept notes for that topic
  problems.md            the practice problems
  python/ java/ csharp/  your solutions, one folder per language you try
git-lessons/<slug>/      concept notes and diagrams from /git-lesson
progress/                your running logs, algorithms and git kept separate
scratch/                 anything ad hoc, treat it as disposable
curriculum.md            the full topic list with slugs
git-curriculum.md        the separate git topic list
AGENTS.md                the rules Claude follows as your tutor
```

Folders under `lessons/` and `git-lessons/` appear as you go. An empty
repo is expected on day one.

## How it works

- `progress/PROGRESS.md` keeps a running log of what you've covered, in
  which language, and how confident you felt about it. It updates
  automatically as you go, so you can close the terminal and pick back up
  later without losing your place.
- Claude won't just hand you solutions. It'll explain the concept, walk
  through a worked example, then give you problems to solve yourself, with
  hints that build up gradually if you get stuck. The full rules it
  follows are in `AGENTS.md`, if you're curious.

## On the three languages

Start in Python, since it's what you already know best and lets you focus
on the algorithm instead of syntax. Use Java for the topics you're
covering in class. C# is the long-term goal.

You don't need to redo every topic in all three languages right away. When
you do come back to a topic in a new language, Claude won't re-teach the
concept from scratch, it'll do a quick recap and then focus on practicing
the same problems in the new syntax.

## If you get frustrated

Say so. Ask Claude to slow down, re-explain, or give you an easier problem
on the same topic. This is meant to build understanding, not to be a test.

## License

MIT, see [`LICENSE`](./LICENSE). Use, copy, and adapt this however you
like.
