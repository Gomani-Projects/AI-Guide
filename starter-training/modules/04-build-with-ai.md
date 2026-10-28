# Module 4: Plan and build your app with AI
`🟡 Moderate` · 30–45 min

The fun part. You'll **plan first, then build in small steps**, the habit that separates good AI-built apps from messy ones.

## Step 1: Pick something small

Keep it to **one screen** that runs by opening an HTML file in your browser: no installs, no logins, no database. Some ideas:

| Type | Ideas |
|---|---|
| 🧰 **Tool** | Unit converter (m ↔ ft, kPa ↔ psi) · Timesheet hours calculator · Job cost estimator · Safety checklist that ticks off items |
| 🎮 **Game** | Reaction-time tester · Number guessing game · Memory card match · Simple quiz about your job or hobby |
| 📊 **App** | Daily to-do list (saves in the browser) · Countdown to a project deadline · Random team-lunch picker |

Something that solves a small problem **you** actually have is best.

## Step 2: Plan with the AI

Point your agent at your folder. In the Claude desktop app, open the **Code** tab and select the `AI-Starter-Training` folder. Then send:

> I'm doing a beginner training course. I want to build **[your idea]** as a single-page web app in the folder `projects/<my-username>/`.
>
> Rules:
> - Plain HTML, CSS and JavaScript only. It must work by double-clicking `index.html`. No installs, no frameworks, no internet needed.
> - Keep it small and simple, with at most 3 files.
> - Only create or change files inside `projects/<my-username>/`.
>
> Before writing any code, ask me up to 5 questions about what I want, then give me a short plan: what's on the screen, what the user can do, and what happens with bad input. Wait for my OK before building.

Answer its questions. **Read the plan.** If you don't understand something, ask it to explain more simply. Say OK when you're happy.

## Step 3: Build it

Let it build. When it asks permission to create files, check they're inside **your folder**, then allow.

Then open `projects/<my-username>/index.html` in your browser (double-click it in Explorer/Finder).

## Step 4: Improve it, one change at a time

Make **2–3 small improvements**, one prompt each, checking in the browser after every change. For example:

> Make the buttons bigger and use these colours: dark blue #1F3A5F and white.

> If someone leaves the box empty, show a friendly message instead of an error.

> Add a "Reset" button that clears everything.

**Tips:**
- Be specific: what, where, and what "done" looks like.
- If something breaks, copy the **exact** error and paste it in: *"I got this error: … Explain what caused it, then fix it."*
- If it goes in circles, stop and start a fresh conversation with a clear summary.

## Step 5: Add a README for your app

> Create a short README.md in my folder: the app name, what it does, how to open it, and one line saying it was built with [your AI tool] during AI Starter Training.

## ✅ Checkpoint

- [ ] My app opens and works in the browser
- [ ] I made at least 2 small improvements, checking after each
- [ ] My folder has an `index.html` and a `README.md`
- [ ] **Nothing** was created outside `projects/<my-username>/`

<details>
<summary>If something goes wrong</summary>

- **The AI created files elsewhere:** ask it: *"Move everything you created into projects/<my-username>/ and delete anything you created outside it."* Check GitHub Desktop's **Changes** list to confirm.
- **Page is blank:** in the browser press F12 → **Console** tab, copy any red error, and give it to the AI.
- **It wants to install things (npm, Python…):** say no. Remind it: *"Plain HTML/CSS/JS only, no installs."*
</details>

← [Module 3](03-branch.md) · **Next: [Module 5: Test and review](05-test-and-review.md)** →
