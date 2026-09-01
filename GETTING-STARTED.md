# Getting Started

Four things to set up before your first lesson: Git, the GitHub CLI,
Claude Code, and your own private copy of this repo. Do these in order.
Once Claude Code is installed, it handles the git and GitHub parts for
you, you won't need to memorize git commands to get going.

If you get stuck on any step, that's normal, see the note at the bottom.

## 1. Confirm you have Claude access

Claude Code requires a paid Claude plan (Pro, Max, Team, or Enterprise).
The free Claude.ai plan doesn't include it. If you're not sure which plan
you're on, check with your mentor before spending time on the rest of
this.

## 2. Install Git

Steps 2 through 4 differ by operating system, so pick the lines that
match yours and ignore the rest.

**Windows:** download and install from
[git-scm.com/downloads/win](https://git-scm.com/downloads/win). The
default options are fine, just click through the installer.

**macOS:** you may already have it. Open Terminal and run
`git --version`. If macOS offers to install the developer tools, accept,
that's all you need. Otherwise install it with [Homebrew](https://brew.sh):

```
brew install git
```

**Linux:** use your distribution's package manager, for example
`sudo apt install git` on Debian or Ubuntu, or `sudo dnf install git` on
Fedora.

## 3. Install the GitHub CLI

**Windows**, from PowerShell:

```
winget install --id GitHub.cli
```

**macOS**, with Homebrew:

```
brew install gh
```

**Linux:** follow the short per-distribution instructions in
[the gh install guide](https://github.com/cli/cli/blob/trunk/docs/install_linux.md).

On any platform you can instead download an installer directly from
[cli.github.com](https://cli.github.com/).

## 4. Install Claude Code

Close and reopen your terminal first, so it picks up the commands you
just installed. Then:

**Windows**, from PowerShell:

```
irm https://claude.ai/install.ps1 | iex
```

**macOS or Linux**, from Terminal:

```
curl -fsSL https://claude.ai/install.sh | bash
```

Close and reopen your terminal again, then verify it worked. This one is
the same everywhere:

```
claude --version
```

You should see a version number. If something looks wrong, run
`claude doctor` for diagnostics.

## 5. Log in to Claude

From here on, every command is identical on all three platforms. Run:

```
claude
```

This opens a browser prompt to log into your Claude account. Follow it,
then type `exit` or press Ctrl+C to leave the session for now.

## 6. Create a GitHub account

Go to [github.com](https://github.com) and sign up if you don't already
have an account. Free is all you need here. Then authenticate the CLI:

```
gh auth login
```

Follow the prompts (choose GitHub.com, HTTPS, and log in via browser when
asked).

## 7. Let Claude Code set up your private copy

This is the last manual step, everything after this is handled for you.
Open a terminal wherever you keep projects and run `claude`, then say:

> Read GETTING-STARTED.md. Clone my mentor's repo at
> `https://github.com/Hallmanac/dsa-lab.git`, rename its remote to
> `hall`, create a new private GitHub repo for me called `dsa-lab` using
> the GitHub CLI, push everything there as `origin`, and set up my git
> identity if it isn't already configured (ask me for my name and the
> email on my GitHub account).

Claude Code will run something close to:

```
git clone https://github.com/Hallmanac/dsa-lab.git dsa-lab
cd dsa-lab
git remote rename origin hall
gh repo create dsa-lab --private --source=. --remote=origin --push
```

From here, `origin` is your private repo (where your work goes) and
`hall` is your mentor's public one (where updates come from). You'll
never push to `hall`, only ever to `origin`, and Claude Code handles that
distinction for you from now on.

## 8. Everyday use

Once you're set up, `cd` into the `dsa-lab` folder, run `claude`, and use:

- `/lesson`: start or continue a lesson
- `/review`: get a solution checked
- `/progress`: see where you stand
- `/sync`: pull in anything your mentor added since last time

You don't need to run git commands yourself. Claude Code commits and
pushes your work to your own private repo automatically as you go, and
`/sync` handles pulling in your mentor's updates. If you ever want to
understand what it's doing under the hood, just ask, that's a good
question, not a distraction.

---

**If you get stuck:** paste the exact error message into Claude Code and
ask it what's going on. That's a normal, expected way to debug setup
issues, not a sign you're doing something wrong.
