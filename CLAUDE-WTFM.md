# Claude WTFM

**W**rite **T**he **F**riendly **M**anual: how to actually use Claude, explained simply. ← [Full guide](guide/README.md) · [GitHub ELI5](ELI5.md)

---

## 🤖 What is Claude?

Claude is an AI helper. You talk to it in normal English and it talks back, writes things, explains things, and (in the right app) builds and changes code for you.

Think of it as a **really fast, really keen new teammate** who:
- ✅ knows a lot and never gets tired
- ✅ will do exactly what you ask
- ❌ sometimes sounds sure when it's wrong
- ❌ doesn't know your project unless you tell it
- ❌ forgets everything when you start a new chat

**You are the boss. Claude is the helper. You check its work.**

---

## 🧰 Which Claude do I use?

| Where | What it's for | Level |
|---|---|---|
| **Claude Chat** ([claude.ai](https://claude.ai) or the desktop app) | Asking questions, planning, writing, explaining errors | 🟢 Easy |
| **Claude desktop app → Code tab** | Building and changing projects on your computer. It can read files, edit them, run things, and use GitHub for you. | 🟢 Easy |
| **Claude Code in VS Code** | Same as the Code tab, inside a code editor | 🟡 Moderate |
| **Claude Code in a terminal** (`claude`) | Same again, typed commands only | 🔴 Hard |

**Start with Chat for thinking, the Code tab for doing.** Download the desktop app from <https://claude.ai/download>.

---

## 🚀 Your first 10 minutes

1. Install the desktop app and sign in.
2. Open a **Chat** and type:
   > *"Explain what GitHub is like I'm 5."*
3. Open the **Code tab**, pick a folder (an empty one is fine) and type:
   > *"Make me a one-page website that says hello and shows today's date. Then open it so I can see it."*
4. Watch what it does. **Read every permission pop-up** before you click Allow.
5. Ask: *"Explain every file you just made, in plain English."*

That's it. You've vibecoded. 🎉

---

## 🗣️ How to talk to Claude

**Pretend you're texting a smart new teammate who's never seen your project.**

| ❌ Don't say | ✅ Say |
|---|---|
| "Fix it" | "The Save button on the Jobs page does nothing when I click it. Find out why and explain before fixing." |
| "Make it nicer" | "Make the headings bigger and add more space between cards. Don't change the colours." |
| "Build me an app" | "Interview me one question at a time until you understand what I want to build. Then write a short plan. No code yet." |
| *(describe the error)* | *(paste the exact error message)* |

**Magic phrases that help a lot:**
- *"Plan this first. Don't write code yet."*
- *"Explain like I'm 5."*
- *"Only change the ___ file / page."*
- *"Ask me if anything is unclear. Don't guess."*
- *"How can I check this works?"*
- *"Be honest. What's wrong with this idea?"* (Claude is too nice by default.)

---

## 🔁 The golden loop

Do this over and over. Small steps win.

```
  1. Ask for ONE small thing
           ↓
  2. Read what it changed
           ↓
  3. Test it yourself (click it, break it)
           ↓
  4. Works? → Save it (commit)
     Broken? → Paste the error back, or undo
           ↓
       back to 1
```

**Commit every time something works.** Then if Claude breaks it next, you just go back.

---

## 🐙 Letting Claude do the GitHub bits

In the **Code tab**, you don't need to learn Git commands. Just ask:

| You want to… | Say to Claude |
|---|---|
| Get a project | *"Clone <owner>/<repo-name> from GitHub"* |
| Start working safely | *"Make a new branch called fix/save-button"* |
| See what changed | *"Show me what you changed and why"* |
| Save your work | *"Commit this with a clear message"* |
| Send it up | *"Push this branch"* |
| Ask for review | *"Open a pull request explaining the change"* |
| Get the latest | *"Switch to main and pull the latest changes"* |
| Fix a clash | *"Help me resolve this merge conflict"* |
| Review a teammate's PR | *"Check out PR #12 and tell me what it does and if anything looks risky"* |

⚠️ If Claude ever offers to push to **`main`**, **force-push**, or **delete** something, say **no** and ask why.

---

## 🛡️ Permission pop-ups

Claude asks before it edits files or runs commands. That's your safety net.

- **Read it.** What is it about to do?
- **Not sure?** Click no, and ask: *"What does that command do and why do you need it?"*
- **Never** blindly click "Allow all" on a project you care about.
- **Stop button:** press **Esc** to stop Claude mid-task. It won't be offended.

---

## 📝 Give Claude a memory (CLAUDE.md)

Claude forgets everything between chats. Fix that with a file called **`CLAUDE.md`** in your project. Claude reads it every time.

Easiest way: in the Code tab, type **`/init`** and Claude writes one for you. Then keep it short, with things like:

```markdown
# Job Tracker
What: a small app for tracking site jobs.
Run it: open index.html in a browser.
Rules:
- Australian dates (DD/MM/YYYY)
- Never commit the .env file
- Only change one page at a time
Where we're up to: Jobs list works. Next: export to Excel.
```

**End of each session, say:** *"Update CLAUDE.md with what we did and what's next, then commit."*

---

## ⌨️ Handy shortcuts (Code tab / terminal)

| Type this | It does |
|---|---|
| `/init` | Writes a CLAUDE.md for your project |
| `/clear` | Fresh start (forgets this conversation) |
| `/compact` | Squishes a long conversation so it keeps working |
| `/model` | Pick a different model (or use the model picker in the app) |
| **Esc** | Stop what it's doing |
| **Esc Esc** | Rewind to an earlier point |
| **Shift + Tab** | Switch modes, e.g. **Plan mode** (it plans but doesn't touch files) |

**Which model?** Smaller/faster ones (Haiku) for quick simple stuff, the middle one (Sonnet) for everyday work, the biggest (Opus) for hard problems. Bigger = smarter but uses more of your allowance. See [Token Optimisation](guide/TOKEN-OPTIMISATION.md).

---

## 😵 When Claude goes weird

| What's happening | What to do |
|---|---|
| It keeps going round in circles | **Stop.** Undo to your last good commit. `/clear` and start fresh with a clear, short ask. |
| It forgot what you told it | The chat got too long. Start fresh, and put the important stuff in CLAUDE.md. |
| It wants to rewrite the whole app for a tiny bug | Say **no**. *"Smallest possible fix only."* |
| It says it's done but it doesn't work | *"It doesn't work. Here's what I see: ___. Find the cause and explain it before fixing."* |
| You don't understand what it did | *"Explain that like I'm 5."* Keep asking until you get it. |
| It made something up (a fake link, a fake feature) | That happens. Tell it, and ask it to check the real docs. |

---

## 🚫 The never-ever list

1. **Never** paste passwords, API keys or secret codes into Claude.
2. **Never** paste customer or personal data into Claude.
3. **Never** let it push to `main`.
4. **Never** accept a change you don't understand.
5. **Never** forget: **you** own what gets merged, not Claude.

If Claude wrote most of a pull request, say so in the description: *"Written with Claude, reviewed and tested by me."*

---

## 📋 Copy-paste starter prompts

**Plan an idea:**
> I want to build ___. Interview me one question at a time until you understand it. Be honest if parts of the idea are weak. Then write a short plan with 3–5 must-have features. No code yet.

**Start a session:**
> Read CLAUDE.md and tell me where we're up to and what's next.

**Build one thing:**
> Make a new branch. Build only ___. Test it. Show me what you changed. Don't commit yet.

**Check its work:**
> Review your own change like a grumpy senior engineer trying to break it. List bugs, security problems and things you didn't test.

**Finish up:**
> Update CLAUDE.md with what we did and what's next. Commit, push, and open a pull request.

---

## 👣 Where next?

- 🐣 [GitHub ELI5](ELI5.md): the GitHub words, super simple
- 🎓 [AI Starter Training](starter-training/README.md): build your first app step by step
- 📚 [Full guide](guide/README.md): everything, in more detail
- 💬 Stuck? Ask Claude: *"Explain what's going wrong like I'm 5, then tell me the safest next step."*
