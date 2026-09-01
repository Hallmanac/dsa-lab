# Algorithms & Data Structures Lab

A self-paced way to learn algorithms and data structures using Claude Code
as your tutor, across three languages: Python, Java, and C#.

## What this repo is

This is the shared baseline your mentor maintains. You don't work in it
directly. You make your own private copy, do all your learning there, and
this repo stays the place updates come from. Setting that copy up is the
first step below.

## First-time setup

You'll need a paid Claude plan (Pro, Max, Team, or Enterprise) and a
GitHub account. Git, the GitHub CLI, and Claude Code all get installed
along the way, so you don't need them beforehand.

New here? Follow [`GETTING-STARTED.md`](./GETTING-STARTED.md) first, it
walks through installing Claude Code and setting up your own private
copy of this repo. Come back here once that's done.

Already set up? Open a terminal in your own copy, run `claude`, and type
`/lesson`.

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
