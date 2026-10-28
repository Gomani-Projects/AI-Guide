# AI Starter Training

A hands-on course that takes you from zero to **building a small app with an AI coding agent and submitting it for review on GitHub**, all in about **1–2 hours**.

No coding experience needed. You'll work entirely on your own computer, and you won't break anything as long as you stay on your own branch and never touch `main`.

> New to the words? Keep the **[Glossary](../guide/GLOSSARY.md)** open in another tab.

---

## What you'll do

```
 ┌───────────────┐   ┌──────────────┐   ┌──────────────┐   ┌──────────────┐
 │ 1. Install    │ → │ 2. Get your  │ → │ 3. Make your │ → │ 4. Build an  │
 │    your tools │   │    own copy  │   │    branch    │   │    app w/ AI │
 └───────────────┘   └──────────────┘   └──────────────┘   └──────┬───────┘
                                                                  ↓
 ┌───────────────┐   ┌──────────────┐   ┌──────────────┐   ┌──────────────┐
 │ 8. Keep it in │ ← │ 7. Open a    │ ← │ 6. Commit &  │ ← │ 5. Test and  │
 │    your repo  │   │    draft PR  │   │    push      │   │    review    │
 └───────────────┘   └──────────────┘   └──────────────┘   └──────────────┘
```

## Modules

Work through them in order. Each one ends with a ✅ checkpoint.

| # | Module | Level | Time |
|---|---|---|---|
| 0 | [Welcome: how this works](modules/00-welcome.md) | 🟢 Easy | 5 min |
| 1 | [Install your tools](modules/01-install-tools.md) | 🟢 Easy | 15 min |
| 2 | [Get your own copy of this course](modules/02-clone.md) | 🟢 Easy | 10 min |
| 3 | [Create your branch](modules/03-branch.md) | 🟢 Easy | 5 min |
| 4 | [Plan and build your app with AI](modules/04-build-with-ai.md) | 🟡 Moderate | 30–45 min |
| 5 | [Test it and review the changes](modules/05-test-and-review.md) | 🟡 Moderate | 10 min |
| 6 | [Commit and push](modules/06-commit-and-push.md) | 🟢 Easy | 5 min |
| 7 | [Open a draft pull request](modules/07-draft-pull-request.md) | 🟢 Easy | 10 min |
| 8 | [Put your app in your own repo](modules/08-your-own-repo.md) | 🟡 Moderate | 10 min |
| 9 | [You're done: what next?](modules/09-next-steps.md) | 🟢 Easy | 5 min |

### Level-up modules (optional)

Take these once you've finished the core course, in any order, **but do Module 10 first**. They use the fake data in `projects/_sample-data/`.

| # | Module | Level | Time |
|---|---|---|---|
| 10 | [Keeping data secure](modules/10-data-security.md) | 🟢→🟡 | 20 min |
| 11 | [Deploy as a web app](modules/11-deploy-web-app.md) | 🟡→🔴 | 30 min |
| 12 | [Deploy as a mobile app](modules/12-deploy-mobile-app.md) | 🟡→🔴 | 30 min |
| 13 | [Connect your tool to Excel, Power BI and other apps](modules/13-connect-to-other-apps.md) | 🟡→🔴 | 30–45 min |
| 14 | [Build a dashboard](modules/14-build-a-dashboard.md) | 🟡 | 30–45 min |

**Levels:** 🟢 Easy = point and click · 🟡 Moderate = a few settings, follow carefully · 🔴 Hard = terminal commands (always optional here)

## How this repo is organised

```
AI-Starter-Training/
├── README.md              ← you are here
├── modules/               ← the course, one file per step
├── projects/
│   ├── _example-split-bill/   ← a finished example to look at
│   ├── _sample-data/          ← fake data for the level-up modules
│   └── <your-github-username>/ ← YOUR work goes here (you'll create it)
└── .github/               ← pull request checklist (used automatically)
```

**Golden rule:** only ever add or change files inside **your own folder**, `projects/<your-github-username>/`.

## Why `main` is off-limits

Nobody (and no AI) should push to `main` or merge into it. That's deliberate:
- The course stays clean, so you can redo it or pass it on.
- You practise the real workflow: **branch → commit → push → pull request**.
- Your pull request stays open as a **draft** so you (or anyone you invite) can look at it and comment. It will never be merged, and that's fine. **Never click Merge.**

---

Stuck? Paste the exact error or the step you're on into your AI agent and ask it to explain in plain English. Finished? Show your app to a friend or colleague.

Ready? → **[Start Module 0](modules/00-welcome.md)**
