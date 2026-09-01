# Start Here

This is the page for someone starting from nothing.

It does not matter if you don't have Git, the GitHub CLI, or Claude Code
installed. It does not matter if you've never used a terminal. You do not
need to know what any of those things are yet. This page assumes none of
them, and Claude will walk you through whatever is missing.

There is exactly one thing you need before you begin: a paid Claude plan
(Pro, Max, Team, or Enterprise). The free plan doesn't include the coding
features this uses. If you're not sure which plan you're on, ask your
mentor before spending time here.

The whole idea: instead of you following a long list of install steps,
you point Claude at this repo and it does the setup with you.

## Two words you'll see a lot

**Git** is a tool that saves snapshots of your work as you go. Think of
the version history in Google Docs, where you can look back at what a
document looked like last Tuesday, except it works for folders of code
and you decide when each snapshot gets taken. It runs on your own
computer.

**GitHub** is a website that stores copies of those snapshots online, so
your work is backed up and your mentor can share updates with you. Git is
the tool, GitHub is the place. They're easy to mix up because of the
names.

You'll need Git installed eventually, but not before you start. Claude
checks whether you have it and walks you through installing it if you
don't. You will never have to memorize Git commands to use this lab.
Claude runs them for you, and if you ever get curious about what it's
doing, `/git-lesson` teaches Git properly, one command at a time.

## 1. Install the Claude app

Download it from [claude.ai/download](https://claude.ai/download) and
sign in with your Claude account. This is the desktop app, not the
website.

You do not need to install Claude Code separately. It comes with the app.

The desktop app runs on Windows and Mac. If you're on Linux, this
assisted path isn't available to you, so use
[`GETTING-STARTED.md`](./GETTING-STARTED.md) instead. It sets the same
thing up from the terminal and works fine on Linux.

## 2. Make an empty folder for your projects

Somewhere you'll remember. It can be completely empty, that's expected.

**On Windows:** open File Explorer, go to your `Documents` folder, and
make a new folder called `Code`. Its full path will look something like
`C:\Users\yourname\Documents\Code`.

**On a Mac:** open Finder, go to your `Documents` folder, and make a new
folder called `Code`. Its full path will look something like
`/Users/yourname/Documents/Code`.

Make the folder now, before the next step. You just need it to exist.

## 3. Start a Code session pointed at that folder

In the Claude app, start a new **Code** session rather than a normal
chat. Claude will ask which folder to work in. Choose the folder you
just made.

The wording of the button may look slightly different depending on your
app version. You're looking for the option that lets Claude work with
files on your computer, as opposed to a plain conversation.

## 4. Paste in this prompt

Copy everything in the box below and send it as your first message.

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

Claude takes over from here.

## 5. What to expect while it runs

None of the following means something went wrong:

- **Claude will ask your permission to run commands.** That's normal and
  it's how it's supposed to work. Read what it's asking, then approve.
- **It will stop and ask you to do things.** Installing Git sets off a
  security prompt from your operating system. On Windows that's a User
  Account Control box asking whether to allow the install. On a Mac it's
  a dialog asking for your login password. Either way it's expected.
  Signing in to GitHub happens in your browser, under your control.
  Claude shouldn't do those parts for you, and it will wait while you do
  them.
- **You'll be asked to create a GitHub account** if you don't have one.
  A free account is all you need. This part is yours to do. Claude will
  point you at the sign-up page but won't create the account or type a
  password for you. That's deliberate, not a limitation, and the same
  goes for signing in to GitHub later.
- **It may take a few rounds of back and forth.** That's the normal shape
  of this, not a sign it's failing.

If anything errors, paste the exact error message back to Claude and ask
what's going on. That is a completely normal way to work, not a sign
you're doing it wrong.

## 6. Open your new folder and start learning

When Claude says setup is done, you'll have a `dsa-lab` folder inside the
folder you made in step 2.

**Start a new Code session pointed at `dsa-lab` itself**, not the folder
above it. This matters. The tutor instructions live inside that folder,
and Claude only picks them up when the session is pointed directly at it.
If you skip this, Claude will still be helpful, but it won't act as your
tutor.

Then type:

```
/lesson
```

It will ask what you'd like to learn and which language you want to use.
You don't need to know the answer, you can say you're not sure and let it
suggest something.

## What you just set up

Two copies of this project now exist, and it's worth knowing why:

- **`origin`** is your own private repo on GitHub. Your work goes here.
  Claude saves and uploads it for you automatically as you go.
- **`hall`** is your mentor's public copy, which is where this came from.
  You'll never push to it. When your mentor adds new material, you run
  `/sync` and it comes to you.

You don't have to remember any of that. Claude handles it. It's here so
the words aren't a mystery when you see them.

---

**Prefer to do it yourself?** If you'd rather type the setup commands by
hand, or if the assisted setup above got stuck,
[`GETTING-STARTED.md`](./GETTING-STARTED.md) has the manual version with
every command spelled out.
