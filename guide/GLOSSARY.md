# Glossary

Plain-English definitions of terms you'll see on GitHub, in AI coding tools, and in "vibecoding" conversations. ← [Back to the guide](README.md)

**Jump to:** [Git & GitHub](#git--github) · [AI coding tools](#ai-coding-tools) · [Vibecoding slang](#vibecoding-slang) · [General dev terms](#general-development-terms)

---

## Git & GitHub

| Term | Meaning |
|---|---|
| **Git** | Version-control software that records every change to a project so you can see history and undo mistakes. |
| **GitHub** | Website that hosts Git repositories online and adds collaboration tools (issues, pull requests, reviews). |
| **Repository (repo)** | A project folder plus its entire change history. |
| **Organisation (org)** | A shared GitHub account that owns repos for a team or company. |
| **Clone** | Download a full copy of a repo to your computer. |
| **Fork** | Your own copy of someone else's repo on GitHub. Mostly used for other people's projects; in your own repos (or a team's, if you have access), use branches instead. |
| **Branch** | A separate line of work. Change things on a branch without affecting `main`. |
| **`main`** | The primary branch — the trusted, working version. (Older repos may call it `master`.) |
| **Commit** | A saved snapshot of changes, with a message describing them. |
| **Commit message** | The short description attached to a commit. |
| **Stage / `git add`** | Choose which changes go into the next commit. |
| **Push** | Upload your commits to GitHub. |
| **Pull** | Download others' new commits from GitHub and merge them into your copy. |
| **Fetch** | Check GitHub for new commits without merging them yet. |
| **Pull Request (PR)** | A request to merge your branch into `main`. Where review and discussion happen. |
| **Merge** | Combine one branch's changes into another. |
| **Merge conflict** | Two branches changed the same lines; Git needs a human (or AI) to decide which to keep. |
| **Rebase** | Replay your commits on top of the latest `main` for a cleaner history. Powerful; ask before using on shared branches. |
| **Diff** | The exact lines added (green, `+`) and removed (red, `−`) between two versions. |
| **HEAD** | "Where you are right now" — the latest commit on your current branch. |
| **Origin** | The default nickname for the GitHub copy of a repo you cloned. |
| **Remote** | Any online copy of a repo (usually `origin`). |
| **Revert** | Create a new commit that undoes an earlier one. Safe way to undo. |
| **Reset** | Move a branch back to an earlier commit. Can destroy work — use with care. |
| **Force push** | Overwrite GitHub's copy with yours. Can delete others' work. Avoid on shared branches. |
| **Stash** | Temporarily shelve uncommitted changes so you can switch tasks. |
| **Tag / Release** | A named marker on a specific commit, e.g. `v1.2.0`, often with downloadable files. |
| **`.gitignore`** | A file listing things Git should never track (secrets, build output, `node_modules`). |
| **README** | The front page of a repo — what it is and how to use it. |
| **Issue** | A tracked bug report, task, or feature request. |
| **Discussion** | A forum-style thread for ideas and questions, which a repo or organisation can turn on. |
| **Review** | Comments / approval / change requests on a PR. |
| **Code owner** | Person or team automatically asked to review changes to certain files. |
| **Branch protection** | Rules on a branch, e.g. "`main` needs 1 approval before merge". |
| **GitHub Actions** | Automations that run on GitHub (e.g. run tests on every PR). |
| **CI/CD** | Continuous Integration / Continuous Deployment — automatically testing and releasing code on every change. |
| **Workflow (Actions)** | A GitHub Actions config file in `.github/workflows/`. |
| **Gist** | A single shareable snippet of code or text on GitHub. |
| **Codespaces** | A full coding environment running in your browser, hosted by GitHub. |
| **`gh`** | The GitHub command-line tool. |
| **GitHub Pages** | Free website hosting straight from a repo. The site is public even if the repo is private. |
| **Worktree** | An extra folder checked out on a different branch of the same repo, so you (or several AI agents) can work on two branches at once. |
| **Template repository** | A repo you can copy as a starting point for a new one. |
| **SSH key** | A secure key pair that lets your computer talk to GitHub without a password. |

---

## AI coding tools

| Term | Meaning |
|---|---|
| **LLM (Large Language Model)** | The AI "brain" behind tools like Claude, ChatGPT and Copilot. Predicts text, including code. |
| **AI coding assistant** | A tool that suggests or writes code, e.g. GitHub Copilot, Claude Code, Cursor, Windsurf. |
| **Agent / agentic coding** | An AI that doesn't just suggest code but *acts*: reads files, runs commands, edits, tests and commits in a loop until the task is done. |
| **Autocomplete / inline suggestion** | Grey "ghost text" the AI suggests as you type. Press Tab to accept. |
| **Chat mode** | Asking the AI questions or giving instructions in a chat panel. |
| **Prompt** | The instruction you give the AI. |
| **Prompt engineering** | Writing prompts carefully to get better results. |
| **Context** | Everything the AI can "see" right now: your messages, open files, instructions file. |
| **Context window** | The maximum amount of text the AI can hold in mind at once. Long sessions can fill it and the AI "forgets" early details. |
| **Token** | The unit AI models count text in (~¾ of a word). Usage limits and costs are measured in tokens. |
| **Hallucination** | The AI confidently making something up — a function, file, setting or fact that doesn't exist. |
| **System prompt / instructions file** | Standing instructions the AI reads every session (`CLAUDE.md`, `AGENTS.md`, `copilot-instructions.md`, `.cursorrules`). |
| **Model** | The specific AI version in use (e.g. Claude Opus, Claude Sonnet, GPT). Bigger = smarter but slower/costlier. |
| **Plan mode** | Asking the AI to plan before making changes, so you can approve the approach. |
| **Permission prompt** | The AI asking "may I run this command / edit this file?" Read these — don't auto-approve blindly. |
| **MCP (Model Context Protocol)** | A standard way to plug AI tools into other systems (GitHub, databases, browsers, docs). |
| **Tool use / function calling** | The AI calling an external tool (run a command, search the web) rather than just writing text. |
| **Skill** | A folder with a `SKILL.md` file of instructions for a specific task. The AI loads it only when relevant. Works across several AI tools. |
| **`SKILL.md`** | The main file of a skill: a short header (name, description) plus step-by-step instructions. |
| **Frontmatter** | The block between `---` lines at the top of a Markdown file holding settings like `name` and `description`. |
| **Plugin** | An installable bundle of skills, commands, agents and tool connections. |
| **Marketplace** | A Git repo that lists plugins so a team can find and install them. |
| **Slash command** | A shortcut typed as `/name` that triggers a saved instruction or skill. |
| **Hook** | An automatic action that runs at a set moment, e.g. "run the formatter after every edit". |
| **Subagent** | A helper AI the main agent spins up for part of a task. |
| **Multi-agent** | Several AI agents working in parallel on parts of a job. Needs clear boundaries and one integrator. |
| **Integrator** | The person or agent who combines parallel work, tests it together and owns the final result. |
| **Context engineering** | Setting up the files, rules, examples and tools around an AI so it can succeed, rather than relying on one clever prompt. |
| **Progressive disclosure** | Giving the AI the essentials first and letting it look up detail only when needed. Saves context. |
| **Completion criteria / definition of done** | An explicit description of what "finished" looks like, so the AI can check its own work. |
| **CLI agent** | An AI coding tool you run in a terminal, e.g. Claude Code, Gemini CLI, Codex. |
| **Claude desktop app** | Anthropic's app for Windows/Mac with chat plus a Code tab that can work on project folders. |
| **Cline** | An open-source AI coding agent extension for VS Code. |
| **Lovable / Bolt** | Browser-based tools that build a whole web app from a description. |
| **RAG** | Retrieval-Augmented Generation — the AI looks up relevant documents before answering. |
| **Temperature** | A setting for how random/creative the output is. Lower = more predictable. |
| **Guardrails** | Rules or checks that stop an AI doing something unsafe. |
| **Human-in-the-loop** | A person reviews or approves the AI's work at key points. |

---

## Vibecoding slang

| Term | Meaning |
|---|---|
| **Vibecoding** | Building software mostly by describing what you want to an AI and accepting its output, focusing on the result ("the vibe") rather than reading every line. Term popularised by Andrej Karpathy in 2025. Great for prototypes; risky for production without review. |
| **Vibe check** | Quickly running the app to see if it *feels* right, rather than formal testing. Do it — but don't let it replace real tests. |
| **One-shot** | The AI gets it right in a single prompt. |
| **Few-shot** | Giving the AI a few examples of what you want so it copies the pattern. |
| **Zero-shot** | Asking with no examples. |
| **Prompt → prototype** | Going from an idea to a working demo in one session. |
| **Accept all / YOLO mode** | Letting the AI apply every change (or run every command) without review. Fast, dangerous. Only on a throwaway branch. |
| **Doom loop / AI spiral** | The AI keeps "fixing" a bug by making new ones. Fix: stop, revert to the last good commit, start a fresh session with a clearer prompt. |
| **Context rot** | Quality drops as a long session fills up with old, irrelevant detail. Fix: start a new session. |
| **Slop / AI slop** | Low-quality, bloated or generic AI output nobody checked. |
| **Spaghetti code** | Tangled, hard-to-follow code. Common when many AI changes pile up unreviewed. |
| **Ship it** | Release / merge it. |
| **LGTM** | "Looks good to me" — common approval comment on PRs. |
| **WIP** | Work in progress — not ready for review yet. Mark PRs as **Draft** for this. |
| **Nit** | A tiny, optional suggestion in a review ("nit: typo here"). |
| **PTAL** | "Please take another look" (after addressing review comments). |
| **Rubber-ducking** | Explaining your problem out loud (or to an AI) to understand it better. |
| **Yak shaving** | Getting side-tracked by a chain of small tasks unrelated to the real goal. |
| **Tech debt** | Shortcuts taken now that make future changes harder. Vibecoding creates it fast. |
| **Greenfield / Brownfield** | Starting a brand-new project / working on an existing one. |
| **MVP** | Minimum Viable Product — the smallest version worth showing people. |
| **Dogfooding** | Using your own tool internally before others do. |
| **Brain dump** | Pasting all your messy thoughts about an idea into an AI chat so it can help turn them into a plan. |
| **Spec / PLAN.md** | A short written plan (users, features, flow, data, definition of done) the AI works from. |
| **AI-assisted development** | An experienced coder writes the code and uses AI for autocomplete and debugging. Contrast with vibecoding, where the AI writes most of it. |
| **PRD (Product Requirements Document)** | A short document saying what you're building, for whom, the features, and what "done" means. |
| **Architecture.md** | A document describing the stack and how the parts fit together, with the reasons for each decision. |
| **Mission / build plan** | A file listing the project's goal and phases that the AI re-reads to stay on track between sessions. |
| **Drift** | The AI slowly wandering from the plan: adding features you didn't ask for or changing things it shouldn't. |
| **Context pollution** | Large, mixed-up files or long chats that confuse the AI, so it starts making wrong assumptions. |
| **Hostile review** | Asking an AI (ideally a fresh session or a different model) to review code as if trying to break it. |
| **Acceptance criteria** | The checklist that defines "working correctly" for a feature, written before it's built. |
| **Checkpoint** | A saved point you can go back to, usually a Git commit. |
| **Boring stack** | Well-known, widely used technology. Easier for AI and people to get right. |
| **SDLC** | Software Development Life Cycle: plan → design → build → test → release → maintain. |
| **Product owner** | The person who decides what gets built and what "right" looks like. When vibecoding, that's you. |
| **Learn vs Build** | Two kinds of lesson: understanding a concept, and making something with it. Mix both. |
| **Happy path** | The scenario where everything goes right. AI often only handles this — ask it about edge cases. |
| **Edge case** | An unusual input or situation (empty list, huge file, weird date) that can break things. |

---

## General development terms

| Term | Meaning |
|---|---|
| **Frontend** | What the user sees and clicks (web page, app screen). |
| **Backend** | The behind-the-scenes server, logic and data. |
| **Full-stack** | Frontend + backend. |
| **API** | A defined way for programs to talk to each other. |
| **Endpoint** | A specific address in an API, e.g. `/api/jobs`. |
| **Database** | Where an app stores data long-term. |
| **Dependency / package** | Someone else's code your project uses (installed via `npm`, `pip`, etc.). |
| **Package manager** | Tool that installs dependencies — `npm` (JavaScript), `pip` (Python), `nuget` (.NET). |
| **Environment variable / `.env`** | Settings (often secrets) kept outside the code. Never commit `.env`. |
| **Secret** | A password, API key or token. Must never go in a repo. |
| **Local / localhost** | Running on your own computer. |
| **Dev / Staging / Production (prod)** | Test environment → pre-release check → the live version real users rely on. |
| **Deploy** | Put a version of the app where people can use it. |
| **Build** | Turn source code into something that runs. |
| **Bug** | Something not working as intended. |
| **Debug** | Find and fix a bug. |
| **Refactor** | Restructure code without changing what it does. |
| **Test (unit / integration / end-to-end)** | Automated checks that a small piece / several pieces together / the whole app work. |
| **Linter** | A tool that flags style issues and likely mistakes automatically. |
| **Terminal / CLI / shell** | The text-based window where you type commands (PowerShell, Bash, Terminal). |
| **IDE / editor** | The app you write code in — VS Code, Cursor, JetBrains. |
| **Framework** | A ready-made structure for building apps (React, Next.js, Django, .NET). |
| **Open source** | Code anyone can view and reuse, under a licence. |
| **CRUD** | Create, Read, Update, Delete: the four basic things most apps do with data. |
| **Single responsibility** | Each file or function does one job. Makes code easier for people and AI to follow. |
| **Source of truth** | The one place where the real, authoritative data or rules live (usually the backend/database). |
| **Deny by default** | Nothing is allowed unless a rule explicitly allows it. |
| **Idempotent** | Safe to repeat: pressing "Submit" twice doesn't create two orders. |
| **Race condition** | A bug where two things happen at once and the result depends on which finishes first. |
| **Rate limiting** | Capping how often someone can call a feature, to prevent abuse or overload. |
| **Caching** | Keeping a copy of data that's slow to fetch, so it can be reused quickly. |
| **N+1 query** | A slow pattern where an app makes one database request per item instead of one for the whole list. |
| **Memory leak** | An app gradually using more and more memory until it slows down or crashes. |
| **Mock-up** | A rough visual version of a screen to agree the look before building it properly. |
| **Row Level Security (RLS)** | A database rule so each user can only see or change their own rows. Essential for apps with logins. |
| **Supabase** | A popular hosted database and login service used by many AI app builders. |
| **OAuth / "Sign in with…"** | Logging in to one service using an account from another (e.g. signing in to a CLI tool through your browser). |
| **Static site** | A website made only of HTML, CSS and JavaScript files, with no server logic. Can be hosted on GitHub Pages. |
| **Hosting / Netlify / Vercel** | Services that put your app on the internet. |
| **Node.js / npm** | A way to run JavaScript outside the browser, and its package manager. Many AI CLI tools need it. |
| **Open Graph tags** | Hidden page info that controls the title, image and description shown when a link is shared. |
| **Licence** | Legal terms for reusing code. Check before copying code from the internet. |

---

Missing a term? Ask your AI: *"Explain ___ in plain English, with an analogy."*
