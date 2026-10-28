# GitHub + AI Coding Tools: A Practical Guide

How to build, share and improve apps using GitHub and AI coding assistants (Claude, GitHub Copilot, Cursor, ChatGPT and others).

You don't need any coding experience to start. If a word is unfamiliar, check the **[Glossary](GLOSSARY.md)**.

> 🐣 **Want the super-simple version first?** Read **[GitHub ELI5](../ELI5.md)** and the **[Claude WTFM](../CLAUDE-WTFM.md)** (how to use Claude, explained simply).

### Difficulty levels

Every topic is tagged so you can pick what suits you:

| Tag | Meaning |
|---|---|
| 🟢 **Easy** | Point and click. No coding or commands. |
| 🟡 **Moderate** | Installing an editor, changing settings, following steps carefully. |
| 🔴 **Hard** | Typing commands in a terminal, or ideas that need some experience first. |

Start with the 🟢 topics. Nothing in 🔴 is required to contribute.

> 🎓 **Prefer learning by doing?** Take the hands-on **[AI Starter Training](../starter-training/README.md)**: install an AI agent and GitHub Desktop, build a small app, and open your first pull request, step by step.

---

## Contents

**Part 1: Understand**
| # | Topic | Level |
|---|---|---|
| 1 | [The big picture: Git, GitHub and AI tools](#1-the-big-picture) | 🟢 Easy |
| 2 | [What is vibecoding?](#2-what-is-vibecoding) | 🟢 Easy |
| 3 | [Learning approach](#3-learning-approach) | 🟢 Easy |

**Part 2: Set up**
| # | Topic | Level |
|---|---|---|
| 4 | [Create your GitHub account](#4-create-your-github-account) | 🟢 Easy |
| 5 | [Install and use the Claude desktop app](#5-install-and-use-the-claude-desktop-app) | 🟢 Easy |
| 6 | [Install GitHub Desktop](#6-install-github-desktop) | 🟢 Easy |
| 7 | [Browser-based app builders (Lovable, Bolt)](#7-browser-based-app-builders) | 🟢 Easy |
| 8 | [VS Code with an AI extension](#8-vs-code-with-an-ai-extension) | 🟡 Moderate |
| 9 | [Terminal basics](#9-terminal-basics) | 🔴 Hard |
| 10 | [Command-line AI tools (Claude Code CLI, gh)](#10-command-line-ai-tools) | 🔴 Hard |

**Part 3: Build**
| # | Topic | Level |
|---|---|---|
| 11 | [Your first contribution (practice exercise)](#11-your-first-contribution) | 🟢 Easy |
| 12 | [Suggest ideas and report bugs without code](#12-suggest-ideas-and-report-bugs) | 🟢 Easy |
| 13 | [Plan before you prompt](#13-plan-before-you-prompt) | 🟢 Easy |
| 14 | [Writing good prompts](#14-writing-good-prompts) | 🟢 Easy |
| 15 | [The everyday workflow: branch → commit → pull request](#15-the-everyday-workflow) | 🟡 Moderate |
| 16 | [Checking AI-written work before you commit](#16-checking-ai-written-work) | 🟡 Moderate |
| 17 | [Reviewing someone else's work](#17-reviewing-someone-elses-work) | 🟡 Moderate |
| 18 | [Context engineering: setting AI up to succeed](#18-context-engineering) | 🟡 Moderate |
| 19 | [Publishing a website with GitHub Pages](#19-publishing-with-github-pages) | 🟡 Moderate |
| 20 | [Skills, plugins and marketplaces](#20-skills-plugins-and-marketplaces) | 🔴 Hard |
| 21 | [Running multiple AI agents at once](#21-running-multiple-ai-agents) | 🔴 Hard |

**Part 4: Stay safe**
| # | Topic | Level |
|---|---|---|
| 22 | [Ground rules](#22-ground-rules) | 🟢 Easy |
| 23 | [When things go wrong](#23-when-things-go-wrong) | 🟡 Moderate |
| 24 | [Command cheat sheet](#24-command-cheat-sheet) | 🔴 Hard |

**Part 5: Keep costs down**
| Topic | Level |
|---|---|
| 📉 **[Token optimisation: keeping AI usage down](TOKEN-OPTIMISATION.md)**: habits, model choice, cutting verbosity, caching and tools | 🟢–🔴 Mixed |

[Further reading and credits](#further-reading-and-credits)

---

# Part 1: Understand

## 1. The big picture
`🟢 Easy`

| Thing | What it is | Analogy |
|---|---|---|
| **Git** | Software that tracks every change to a folder of files | "Track changes" plus unlimited undo for a whole project |
| **GitHub** | A website that stores Git projects online so people can share them | OneDrive/SharePoint, built for code |
| **Organisation** | A team's or company's shared space on GitHub (optional; your own account works fine) | A shared team drive |
| **Repository (repo)** | One project: its files and their full history | One project folder |
| **AI coding tool** | An assistant that reads, writes and explains code from plain-English instructions | A very fast junior developer who needs clear direction and checking |

**The core idea:** nobody edits the "real" version directly. You make a copy (a *branch*), change it, then ask for it to be merged back in (a *pull request*). Someone checks it first. This lets many people, and their AI assistants, work on the same project without breaking each other's work.

```
main  ──●────────●──────────────●──►   (the trusted, working version)
         \                     /
my-fix    ●──●──●── Pull Request   (your changes, reviewed before merging)
```

## 2. What is vibecoding?
`🟢 Easy`

**Vibecoding** means building software by describing what you want in plain English and letting an AI write the code. You focus on the result (the "vibe") rather than the syntax.

**Why it's great:** anyone with an idea can build a working prototype, fast. It's a brilliant way to learn by experimenting.

**Where it goes wrong:**
- Accepting AI output without checking it.
- Skipping the basics: version control (Git), security, and knowing roughly how your app fits together.
- Messy projects with no structure or README, so nobody (including the AI) can find anything later.
- Endless tiny tweaks ("move it 2 pixels left… no, back") that break things that were working.

**Vibecoding vs AI-assisted development:** in AI-assisted development, an experienced coder writes the code and uses AI for autocomplete and debugging. In vibecoding, the AI writes most of it and you direct. Both are fine; the more important the app, the more you should move toward reviewing and understanding what gets written.

## 3. Learning approach
`🟢 Easy`

**1. Learn by doing.**
Courses go out of date fast because the tools change with every new AI model. The people who get good at this mostly just start building.
- **Start smaller than you think.** The point of a first project isn't the idea. It's learning the loop: **describe → review → test → fix**.
- **Solve a problem you actually have.** You'll care more and know when it's right.
- **Finish one small thing** rather than starting ten.
- **Stick with one tool** while you learn. Almost any decent AI assistant will do. Hunting for the "best" tool wastes time.
- **Expect to break things.** Getting stuck is where the learning happens. Commit often so breaking things is cheap.
- **Learn from others' projects:** find a similar project on GitHub, clone it, and ask your AI to explain how it works.

**Good first projects:**

| Project | What it teaches |
|---|---|
| Task tracker: add, edit, complete, delete. Store locally first; add a login and database later. | Screens, saving data, the basics of every app |
| Simple one-page website | Layout, styling, publishing |
| An app that fetches data from a public API (weather, exchange rates) | How apps talk to other services |
| A small automation script (rename files, tidy a spreadsheet) | Automating a real chore |
| Calculator or expense tracker | Input, validation, edge cases |

**2. Understand the fundamentals as you go.**
AI handles the syntax; your job becomes more like a **product owner and designer**. You don't need to write code, but you do need to know roughly how software fits together, or you can't tell whether what the AI built is solid or a time bomb. Learn the basics of:
- **Frontend vs backend,** and why important rules and permissions belong in the backend
- **APIs:** how the frontend, backend and other services talk to each other
- **Databases:** where data lives and who can see it
- **Git and version control** (this guide)
- **Basic system design:** small, focused parts that each do one job
- **Getting an app online (hosting),** not just running it on your own computer

You can have the AI teach you most of this: *"Explain every file you just created and why it's there."* Don't just copy its fixes. Ask until you understand why they work.

**3. Plan before prompting.** Five minutes of planning saves hours of the AI going in circles. See [Plan before you prompt](#13-plan-before-you-prompt).

**4. Build in small steps.** One feature at a time, test it, commit it, then the next. It feels slower but it's much faster overall. **Don't let the project get bigger than your ability to debug it.**

**5. Check it's worth building.** "I can build it" isn't the same as "people need it". Before building a tool for others, ask: who has this problem, how do they handle it today, and would they switch?

**A suggested path:**

| Stage | Do this |
|---|---|
| Week 1 | Topics 1–7, 11, 12. Chat with Claude, make your first contribution. |
| Week 2 | Topics 13–16. Build a small tool on a branch and open a pull request. |
| Later | Topics 17–21 as you need them. |

---

# Part 2: Set up

## 4. Create your GitHub account
`🟢 Easy`

1. Sign up at <https://github.com/signup>. It's free.
2. Turn on **two-factor authentication (2FA)**: profile picture → **Settings** → **Password and authentication**.
3. Optional: add a profile picture and your name so people recognise you.
4. Joining a team or company organisation? Send them your GitHub username, then accept the invite from your email.

## 5. Install and use the Claude desktop app
`🟢 Easy`

The Claude desktop app is the easiest way to start: chat for questions and planning, and a **Code** tab that can work on files and projects for you.

**Install:**
1. Download from <https://claude.ai/download> (Windows or Mac).
2. Run the installer and sign in with your Claude account.

**Using it:**
- **Chat:** ask questions, brainstorm, plan an app, get errors explained. Good for [planning before you prompt](#13-plan-before-you-prompt).
- **Code tab:** point Claude at a project folder and ask it to build or change things. It can read and edit files, run the app, and use Git and GitHub for you (it can clone, branch, commit and open pull requests if you ask).
- **Permission prompts:** Claude asks before editing files or running commands. Read what it's asking. If you're not sure, say no and ask it to explain.
- **Start fresh when stuck:** a new conversation with a clear summary of the goal often beats a long, confused one.

**Try it:** in a Chat, type *"Here's what I do day to day: ___. Suggest five small tools I could build as a beginner to make it easier, and what each would need."*

## 6. Install GitHub Desktop
`🟢 Easy`

GitHub Desktop lets you do everything in [the everyday workflow](#15-the-everyday-workflow) with buttons instead of commands.

1. Download from <https://desktop.github.com/> and sign in with your GitHub account.
2. **File → Clone repository** → choose one of your repos (or one you've been given access to).
3. Use **Current branch → New branch** before making changes.
4. After editing, write a summary at bottom-left and click **Commit**.
5. Click **Push origin**, then **Create Pull Request**.

It also installs Git for you.

## 7. Browser-based app builders
`🟢 Easy`

Tools that build a whole app from a description, entirely in your web browser:

| Tool | Good for |
|---|---|
| [Lovable](https://lovable.dev) | The most beginner-friendly. Full web apps with little setup. |
| [Bolt](https://bolt.new) | A bit more technical: some backend logic and a built-in terminal. |

**Tips:**
- **Connect it to GitHub** (both support this) and save it to your GitHub account (or your team's organisation), so the code is backed up, versioned and shareable.
- If your app has user logins or stores data, make sure data is protected so users can only see their own records. In Supabase-backed apps this is called **Row Level Security (RLS)**. Ask the tool: *"Is Row Level Security enabled on every table?"*
- Good places for design ideas: [Google Fonts](https://fonts.google.com), [Coolors](https://coolors.co) for colour schemes, [Mobbin](https://mobbin.com) and [Dribbble](https://dribbble.com) for layouts.

## 8. VS Code with an AI extension
`🟡 Moderate`

[VS Code](https://code.visualstudio.com/) is a free code editor with Git built in. Add an AI assistant as an extension:

- **GitHub Copilot:** Extensions panel → search "GitHub Copilot" → install → sign in with GitHub.
- **Claude Code:** Extensions panel → search "Claude Code" → install → sign in.
- **Cline:** an open-source AI agent extension that works with many AI models.

Use the **Source Control** panel (branch icon on the left) to see changes, commit and push. [Cursor](https://cursor.com) and Windsurf are VS Code-based editors with AI built in and work the same way.

## 9. Terminal basics
`🔴 Hard`

The **terminal** (also called the command line, shell or CLI) is a window where you type commands instead of clicking. On Windows it's **PowerShell** or **Windows Terminal**; on Mac it's **Terminal**.

| Command | What it does |
|---|---|
| `pwd` | Show which folder you're in |
| `ls` (or `dir`) | List files in this folder |
| `cd foldername` | Go into a folder |
| `cd ..` | Go up one folder |
| `mkdir name` | Make a new folder |
| `code .` | Open this folder in VS Code |

Tips:
- **Tab** auto-completes file and folder names. **↑** repeats your last command.
- **Ctrl + C** stops whatever is running.
- If a command asks for something you don't understand, stop and ask. Don't paste commands from the internet (or an AI) unless you know what they do.
- On Windows, if scripts won't run, you may need: `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`. Check with IT first.

Tell Git who you are (once per computer):
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## 10. Command-line AI tools
`🔴 Hard`

These run inside a terminal and are the most powerful option: the AI can read your whole project, run commands and tests, and work through multi-step tasks on its own.

| Tool | Install | Run |
|---|---|---|
| **Claude Code** | See <https://claude.com/claude-code> | `claude` inside a project folder |
| **GitHub CLI** | <https://cli.github.com/> | `gh auth login`, then `gh pr create`, `gh issue list`, etc. |
| **Others** | Gemini CLI, OpenAI Codex CLI | `gemini`, `codex` |

Most sign in through your web browser the first time. Requires Git and often [Node.js](https://nodejs.org/) installed.

---

# Part 3: Build

## 11. Your first contribution
`🟢 Easy`

Practise the whole workflow on something harmless. First, make a practice repo: on GitHub click **+** → **New repository** → name it `practice` → **Private** → tick **Add a README** → **Create repository**. Then pick **one** method.

**Option A, in your browser (easiest):**
1. Open `README.md` in your practice repo and click the pencil ✏️ icon.
2. Add a line at the bottom: `Hello from <your name>!`.
3. Click **Commit changes…**, choose **Create a new branch**, name it `add-hello`, then **Propose changes**.
4. Click **Create pull request**, look at **Files changed**, then **Merge pull request**. Done: you've done the full loop.

**Option B, with the Claude desktop app:**
Open the Code tab and ask: *"Clone <my-username>/practice, create a branch called add-hello, add 'Hello from [my name]!' to the end of README.md, commit it, push, and open a pull request."* Watch what it does and read each permission prompt.

**Option C, with GitHub Desktop:** follow the steps in [section 6](#6-install-github-desktop).

## 12. Suggest ideas and report bugs
`🟢 Easy`

You don't need to code to contribute.

- **Ask a question or share an idea:** if the repo or organisation has **Discussions** turned on, post there (often split into Q&A, Ideas, and Show and tell). Otherwise open an **Issue**.
- **Report a bug:** open the repo → **Issues** → **New issue**. Include what you expected, what happened, steps to reproduce, and a screenshot.
- **Fix a typo:** open the file on GitHub → pencil ✏️ → edit → **Propose changes**.
- **Comment on a pull request:** open it → **Files changed** → click a line to comment.

## 13. Plan before you prompt
`🟢 Easy`

The most common beginner mistake is opening an AI tool and typing "build me an app". Plan first.

1. **Brain-dump.** In a Claude chat, paste every scattered thought, feature and note about your idea. Messy is fine.
2. **Let the AI interview you like a product manager would.** Ask: *"Interview me one question at a time until you understand exactly what I want to build. Be honest and critical. Tell me if parts of the idea are weak or unnecessary."* (By default AI tends to tell you every idea is brilliant and to suggest more features than you need.)
3. **Answer the key questions:**
   - **Who** uses it and **what problem** does it solve?
   - **What are the screens,** and what can the user do on each?
   - **What data** gets saved? Is any of it sensitive?
   - **What should happen when something goes wrong?** (Bad input, lost connection, button pressed twice.)
   - **What must never happen?** (e.g. one user seeing another's records.)
   - **Must-have features** for version 1 (3–5 at most) vs "later".
   - **What does "done" look like** for version 1?
4. **Choose a boring stack.** Ask the AI to recommend simple, well-known technology and explain why. Decide it up front: **changing the stack halfway through is painful.** Keep the frontend and backend separate.
5. **Write the plan into your repo** as a few short files the AI reads every session:

   | File | Contains |
   |---|---|
   | `PRD.md` (product requirements) | What it is, who it's for, features, "done" criteria |
   | `ARCHITECTURE.md` | The stack, how the parts fit together, and **why** each decision was made |
   | `BUILD-PLAN.md` | Phases, each with the components to build and how you'll know it works |
   | `CLAUDE.md` / `AGENTS.md` | Rules for the AI, the current state of the project, and lessons from past mistakes. See [section 18](#18-context-engineering). |

   Small projects can combine these into one file.
6. **Get a second opinion.** Paste the plan into a different AI (or ask a colleague) and ask what's missing or risky.
7. **Read the plan before any code is written.** If you don't understand it, ask for a simpler version.
8. **For anything visual,** ask for a quick HTML mock-up first, and give it example screenshots or sites you like. It's much easier to agree the look before the real build.
9. **Build one feature at a time** from the plan. When things are going well, it's tempting to do two at once. Don't.

**Leave until later:** logins, payments, AI features, dashboards and integrations. Get the core working first; adding these on day one is how beginner projects turn into spaghetti.

## 14. Writing good prompts
`🟢 Easy`

| Weak prompt | Strong prompt |
|---|---|
| "Fix the app" | "The export button on the Reports page throws an error when the table is empty. Make it show 'No data to export' instead." |
| "Make it look better" | "Increase the padding on the dashboard cards and make the headings bold. Don't change the colours." |
| "Add a database" | "Before writing code, suggest two options for storing the job list and explain the trade-offs." |

- **One task at a time.** Small requests mean small changes you can check.
- **Ask for a plan first** on anything bigger than a small fix: *"Plan this before writing code."*
- **Say what not to touch:** *"Only change the Reports page."*
- **Paste the exact error message** when something breaks, rather than describing it.
- **Ask it to explain:** *"Explain what this file does in plain English."*
- **Ask how to test:** *"How can I check this works?"*

## 15. The everyday workflow
`🟡 Moderate`

This is the loop you'll repeat for every change. Each step shows the plain-English version, the command, and what to ask your AI tool.

| # | Step | Command | Or ask your AI tool |
|---|---|---|---|
| 1 | **Get the project** (first time) | `git clone https://github.com/<owner>/<repo>.git` | "Clone `<owner>/<repo>` from GitHub" |
| 2 | **Get the latest version** | `git switch main` then `git pull` | "Switch to main and pull the latest changes" |
| 3 | **Make your own branch** | `git switch -c fix/login-button` | "Create a branch called fix/login-button" |
| 4 | **Make changes** | *(edit yourself or with AI)* | "Make the login button bigger on mobile" |
| 5 | **Check what changed** | `git status` and `git diff` | "Show me what you changed and why" |
| 6 | **Save a snapshot (commit)** | `git add .` then `git commit -m "Make login button larger on mobile"` | "Commit this with a clear message" |
| 7 | **Upload your branch (push)** | `git push -u origin fix/login-button` | "Push this branch" |
| 8 | **Ask for review (pull request)** | `gh pr create` or the green button on GitHub | "Open a pull request describing the change" |
| 9 | **Respond to feedback** | Repeat steps 4–7 on the same branch | "Address the review comments on the PR" |
| 10 | **Merge** | Click **Merge** on GitHub once approved | |

**Branch names:** short prefix + description, lowercase, hyphens: `feature/export-to-excel`, `fix/date-format-au`, `docs/setup-steps`, `experiment/new-dashboard`.

**Commit messages:** say what changed and, if not obvious, why. ✅ `Fix date showing in US format on invoices` ❌ `stuff`, `updates`, `fixed it`.

**Commit often.** Every time something works, commit it. If the AI breaks things next, you can go straight back.

## 16. Checking AI-written work
`🟡 Moderate`

AI tools are fast but not accountable. **You are.** Before you commit:

- [ ] Read the diff (the Changes view in GitHub Desktop / VS Code, or `git diff`). Do you roughly understand what changed?
- [ ] Run the app and check it actually works, including what happens with empty or unusual input.
- [ ] No passwords, API keys or customer data in the changes.
- [ ] It only changed what you asked for, with no surprise rewrites elsewhere.
- [ ] No new packages or services you didn't expect.
- [ ] Click every button and try bad input: blank fields, huge numbers, double-clicks.
- [ ] Ask: *"Review your own change for bugs, security issues and edge cases."* Even better, open a **fresh session or a different AI** and ask it to review the change like a sceptical senior engineer trying to break it.

**It looking right doesn't mean it is right.** The AI sounds confident even when it's wrong, and bugs can hide behind a working screen. Write down tests for the features that matter most.

**Debugging:** stay in charge. Read the error, paste it in exactly, and ask the AI to **explain the cause in plain English before it fixes anything**. Never accept a fix you don't understand. If it wants to rewrite half the app to fix a small bug, say no and go back to your last good commit.

**Rules to give the AI for anything important** (put them in your instructions file):
- If a requirement is unclear, **stop and ask**. Never invent business rules.
- Important rules, permissions and calculations live in the **backend**. The frontend (what the user sees) can't be trusted.
- **Deny by default:** nothing is visible to a user unless it's explicitly allowed.
- Check all input on the backend, and never expose secrets or keys to the frontend.
- Return clear error messages, never just "something went wrong".

**Common beginner mistakes:**
- Building too much at once
- Not reading the plan
- Changing the stack mid-project
- Adding logins too early
- Letting the AI rewrite the whole app for a tiny bug
- Not committing, so there's no checkpoint to go back to
- Vague prompts like "make it better"
- Not testing after every small change

**For growing apps 🔴:** now and then ask your AI to check for common hidden problems: *"Check this project for N+1 database queries, missing rate limiting, missing caching and memory leaks, and explain any you find."*

If a pull request was mostly AI-written, say so in the description (e.g. "Written with Claude Code, reviewed and tested by me").

## 17. Reviewing someone else's work
`🟡 Moderate`

1. Read the pull request description. What is it meant to do?
2. Check **Files changed**. Comment on specific lines.
3. If you can, try it: `gh pr checkout <number>`, or ask your AI tool to check out the PR.
4. Finish with **Review changes** → **Comment**, **Approve**, or **Request changes**.

Be kind and specific: *"This breaks when the list is empty. Could we add a check?"* beats *"This is wrong."*

## 18. Context engineering
`🟡 Moderate`

A clever prompt matters less than the **environment** the AI works in: the files, rules, examples and tools it can see. Ask yourself: *what would a capable new colleague need to do this task well?* Then put that in the repo.

**Add an instructions file** that the AI reads every session:

| Tool | File |
|---|---|
| Claude Code | `CLAUDE.md` |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Cursor | `.cursor/rules/` |
| Many tools | `AGENTS.md` |

**What to put in it:**
- What the app does and who uses it
- How to run it and how to test it
- Folder layout: where things live
- Conventions ("use Australian date format", "all pages use the shared header")
- Hard rules ("never edit the `data/` folder", "never commit `.env`")
- What "done" means ("tests pass and the page loads without errors")

- Lessons learned: what broke and how it was fixed, so it doesn't happen again

**Keep it short.** The more rules you pile in, the more likely the AI is to skip some. Keep only rules that matter, and cut the rest.

**Treat the instructions file as a living document.** A simple session loop:
1. **Start:** *"Read CLAUDE.md and tell me where we're up to."*
2. **Build** one component, and test it straight away.
3. **Finish:** *"Update CLAUDE.md with what we did, what works, any decisions and why, and anything that failed."* Then commit.

**Keep files small and focused.** Big files that do many jobs confuse the AI ("context pollution") and it starts guessing. Ask for one job per file. When adding a big feature, ask it to **reuse existing code** rather than creating new copies, and to tidy up (refactor) regularly.

**Tell it to check live documentation** for any outside service or library, rather than relying on what it remembers. That goes out of date.

**Other techniques:**
- **Show, don't tell.** Point to a good existing file: *"Build the new page the same way as `reports.html`."*
- **Keep it short and layered.** Put the essentials in the instructions file and link to longer docs, rather than cramming everything in.
- **Give it tools to check its own work:** tests, a way to run the app, a browser to look at the result.
- **Keep docs next to the code** they describe, and keep them up to date.

## 19. Publishing with GitHub Pages
`🟡 Moderate`

GitHub Pages turns a repo containing a simple website (HTML, CSS, JavaScript) into a live site for free.

1. Open the repo → **Settings** → **Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**, pick `main`, and **Save**.
3. Wait a minute, then check the **Actions** tab. Your site appears at `https://<owner>.github.io/<repo-name>/`.
4. For apps that need building (React, Next.js), choose **GitHub Actions** as the source instead and pick the matching template.

⚠️ **A Pages site is public on the internet, even if the repo is private.** Never publish internal or customer data this way. On a work repo, check with whoever manages it before enabling Pages.

Alternatives for apps with a backend: Netlify, Vercel, or Azure.

## 20. Skills, plugins and marketplaces
`🔴 Hard`

Ways to package know-how so every AI session, and every teammate, can reuse it.

| Thing | What it is | Analogy |
|---|---|---|
| **Skill** | A folder with a `SKILL.md` file: instructions for a specific task (e.g. "how we write site reports"), plus optional scripts and templates. The AI loads it only when relevant. | A recipe card |
| **Plugin** | A bundle of skills, commands, agents and tool connections, installed as one package. | A recipe book |
| **Marketplace** | A Git repo listing available plugins, so a team can browse and install them. | The bookshop |

**A minimal skill:**
```
site-report/
├── SKILL.md
├── templates/report-template.md   (optional)
└── scripts/                       (optional)
```
```markdown
---
name: site-report
description: Writes a site inspection report in our standard format. Use when the user asks for a site report or inspection write-up. Not for invoices or quotes.
---

# Site report

1. Ask for the site name, date, inspector and findings.
2. Fill in templates/report-template.md.
3. Use Australian spelling and DD/MM/YYYY dates.
```

**Writing good skills:**
- The **`description`** decides when the skill is used. Say what it does, when to use it, and when *not* to.
- Write instructions as clear steps, and explain *why* for anything non-obvious.
- Keep it under ~500 lines; link to longer docs instead of copying them in.
- Test it on several realistic requests before sharing.
- Only install skills and plugins from sources you trust. They can run code.
- **Don't collect skills for the sake of it.** Today's AI models are capable on their own, and many skills people share online just add bloat. Add one when you keep repeating the same instructions, not before.

**Sharing with a team:** keep shared skills and plugins in one repo that works as a marketplace, so anyone with access can install them.

## 21. Running multiple AI agents
`🔴 Hard`

Advanced users can run several AI agents in parallel. It's powerful, and chaotic if unmanaged.

- **Split the work so it doesn't overlap.** Frontend vs backend, or one agent investigating while another writes tests. Vague tasks like "improve the app" guarantee collisions.
- **Write a contract first** for each agent: what it delivers, which files it owns, what it must not touch.
- **Isolate them.** Give each agent its own branch, ideally in its own **git worktree** (a separate folder checked out on its own branch), so they don't overwrite each other's files.
- **Isolated isn't the same as compatible.** Two branches can each work alone and still break when combined (e.g. one renames a field the other uses).
- **Have one integrator,** a person or an agent, who merges everything, runs all the tests together, and checks the result still meets the original goal.
- **Use agents as reviewers too:** one builds, another checks for bugs, security and accessibility.
- **Don't parallelise small jobs.** One agent is often faster than coordinating five.

---

# Part 4: Stay safe

## 22. Ground rules
`🟢 Easy`

1. **Never commit secrets:** passwords, API keys, tokens, connection strings. Keep them in a `.env` file listed in `.gitignore`. If one is committed by accident, change it immediately and tell the repo owner if it isn't you. Deleting it later doesn't remove it from history, so the key must be changed.
2. **Never push directly to `main`.** Always branch and open a pull request.
3. **No customer or personal data** in repos, AI prompts, issues or screenshots.
4. **Every repo has a README** saying what it is, who owns it and how to run it.
5. **Small pull requests** get reviewed and merged faster.
6. **You own what you merge,** whether you or an AI wrote it.
7. **Private by default.** New repos are private unless there's a reason to share publicly.
8. **Read permission prompts.** Don't auto-approve AI tools running commands you don't understand.

## 23. When things go wrong
`🟡 Moderate`

| Problem | What it means | Fix |
|---|---|---|
| `rejected ... fetch first` when pushing | Someone pushed changes you don't have | `git pull`, then push again |
| **Merge conflict** | You and someone else changed the same lines | Open the file, keep the right version (between `<<<<<<<` and `>>>>>>>`), save, commit. Or ask your AI: *"Help me resolve this merge conflict."* |
| Broke everything, not committed yet | Uncommitted changes are bad | `git restore .` throws away all uncommitted changes (⚠️ can't be undone) |
| Committed something wrong | Last commit needs undoing | `git revert HEAD` makes a new commit that undoes it (safe) |
| Made changes on `main` by mistake | Wrong branch | `git switch -c my-new-branch` moves you and your changes to a new branch |
| **AI going in circles** ("doom loop") | Too much context, or an unclear goal | Stop. Go back to your last good commit. Start a fresh session with a clear, specific prompt. |
| AI "forgets" earlier instructions | Context window is full | Start a new session. Put lasting rules in the instructions file ([section 18](#18-context-engineering)). |
| `Permission denied` / `403` | No access to that repo | Check it's the right repo, or ask its owner to add you |
| Push blocked: "would publish a private email" | GitHub is protecting your email | Use your GitHub no-reply email: GitHub → Settings → Emails |

When in doubt: **stop, don't force-push, and ask** someone who knows Git, or paste the exact message into your AI and ask it to explain before doing anything.

## 24. Command cheat sheet
`🔴 Hard`

```bash
git clone <url>               # download a repo
git status                    # what's changed?
git pull                      # get latest changes
git switch -c <branch>        # new branch
git switch <branch>           # change branch
git add .                     # stage all changes
git commit -m "message"       # save a snapshot
git push                      # upload
git log --oneline             # history
git diff                      # see exact changes
git worktree add ../<folder> <branch>   # extra working folder for a branch
gh pr create                  # open a pull request
gh pr checkout <number>       # try someone's PR locally
```

---

## Further reading and credits

This guide draws on these excellent free resources. Worth exploring once you're comfortable:

**GitHub basics**
- [Introduction to GitHub](https://github.com/skills/introduction-to-github) (GitHub Skills): hands-on course, under an hour 🟢
- [First Contributions](https://github.com/firstcontributions/first-contributions): practise making a pull request, with guides for GitHub Desktop, VS Code and more 🟢
- [GitHub for Beginners: GitHub Pages](https://github.blog/developer-skills/github/github-for-beginners-getting-started-with-github-pages/) 🟡

**Vibecoding**
- [Vibe Coding for Beginners](https://github.com/maddiedreese/vibe-coding-for-beginners): ideas to deployed app with browser tools 🟢
- [What is Vibe Coding?](https://thecodeabides.com/blog/what-is-vibe-coding/) 🟢
- [Context Engineering for Vibe Coders](https://thecodeabides.com/blog/context-engineering-for-vibe-coders/) 🟡
- [Multi-Agent Vibe Coding Without Chaos](https://thecodeabides.com/blog/multi-agent-vibe-coding-without-chaos/) 🔴
- [Vibe coding dev environment installer](https://wuu73.org/vibe/): scripted setup of Git, Node, Python, VS Code and CLI AI tools 🔴

**AI and agents**
- [Generative AI for Beginners](https://github.com/microsoft/generative-ai-for-beginners) (Microsoft): 21 lessons split into "Learn" and "Build" 🟡
- [Agent Skills Guide](https://github.com/open-edge-platform/skills/blob/main/SKILLS_GUIDE.md) 🔴
- [Agent Skills, Plugins and Marketplaces](https://chris-ayers.com/posts/agent-skills-plugins-marketplace/) 🔴

**Process guides**
- [The AI Builder's Playbook](https://jeffcu.github.io/AI_Builders_Playbook/guide.html): plan first, then build in sessions around a living `CLAUDE.md` 🟡
- [AINews Learn](https://www.ainews.tech/learn) and [AI coding workflows](https://www.ainews.tech/coding): short beginner guides 🟢

**Community**
- [r/vibecoding](https://www.reddit.com/r/vibecoding/) and [r/vibecodingcommunity](https://www.reddit.com/r/vibecodingcommunity/): real-world threads on learning by doing, fundamentals and planning, which shaped sections 3, 13, 16 and 18

---

**Make it your own.** Copy this guide into your own repo and adapt it for your team: branch, edit, open a pull request.
