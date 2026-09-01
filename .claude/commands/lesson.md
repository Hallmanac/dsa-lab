---
description: Start a guided DS&A lesson on a topic, or continue where you left off
argument-hint: [topic name] [language, optional]
model: sonnet
---

Read `progress/PROGRESS.md` and `curriculum.md` first.

Parse $ARGUMENTS for a topic name and, optionally, a language (python,
java, or csharp).

- If no topic is given, don't just default to the next one in sequence:
  ask what sounds interesting, and if they're not sure, show the full
  Core list from curriculum.md (plain names, no need to already know the
  terms) grouped by whether it's already been started, plus any
  topic-language pair logged with confidence 3 or below as a "revisit"
  option. Only offer Advanced topics if they ask for something harder or
  have finished most of Core.
- If they say something like "I don't know" or "you pick," suggest the
  next unstarted Core topic in curriculum order, but say what it is and
  ask them to confirm rather than just starting it.

Language is chosen fresh every time this command runs. Never assume or
carry a default over from a previous lesson or session.

- If $ARGUMENTS didn't include a language, ask directly: "Which language
  for this lesson (Python, Java, or C#)?" Wait for their answer before
  doing anything else.
- If $ARGUMENTS did include one, don't skip the step silently: confirm it
  back in one short line ("This one's in Java.") so the choice is still
  visible and deliberate, not just parsed quietly in the background.

Find the topic's slug in curriculum.md and use `lessons/<slug>/` as the
working directory for this session.

- If `lessons/<slug>/README.md` doesn't exist yet, this is the student's
  first pass at the topic: run the full explainer, analogy, and worked
  example per AGENTS.md, and write `README.md` and `problems.md`.
- If it already exists, this is a repeat in a new language: give a brief
  recap instead of the full explainer, reuse the problems already in
  `problems.md`, and still walk through one worked example in the new
  language.

Create `lessons/<slug>/<language>/` if it doesn't already exist, and have
the student solve the practice problems there. Do not reveal or move to
the next problem until they've made a real attempt at the current one.
Follow the tiered-hint rules in AGENTS.md if they get stuck, one tier at a
time.

When the lesson wraps up, ask them to self-rate confidence 1-5, then
append one row to `progress/PROGRESS.md`: date, topic, language, problems
attempted, confidence, and a short note on what to revisit if confidence
was 3 or below.
