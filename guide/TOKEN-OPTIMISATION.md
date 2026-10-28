# Token Optimisation: Keeping AI Usage Down

How to get the same (or better) results from AI coding tools while using fewer tokens, which means lower cost, fewer usage-limit lockouts, and often better answers. ← [Back to the guide](README.md)

Difficulty tags work the same way as in the main guide: 🟢 Easy · 🟡 Moderate · 🔴 Hard.

---

## Contents

| # | Topic | Level |
|---|---|---|
| 1 | [What tokens are and why they matter](#1-what-tokens-are-and-why-they-matter) | 🟢 Easy |
| 2 | [The ten habits that save the most](#2-the-ten-habits-that-save-the-most) | 🟢 Easy |
| 3 | [Manage your conversation (context)](#3-manage-your-conversation) | 🟢 Easy |
| 4 | [Pick the right model for the job](#4-pick-the-right-model-for-the-job) | 🟢 Easy |
| 5 | [Write prompts that don't need retries](#5-write-prompts-that-dont-need-retries) | 🟢 Easy |
| 6 | [Cut verbosity: shorter answers, less waste](#6-cut-verbosity) | 🟡 Moderate |
| 7 | [Lean instructions files and fewer tools](#7-lean-instructions-files-and-fewer-tools) | 🟡 Moderate |
| 8 | [Prompt caching](#8-prompt-caching) | 🟡 Moderate |
| 9 | [Token-saving tools and plugins](#9-token-saving-tools-and-plugins) | 🔴 Hard |
| 10 | [Measuring your usage](#10-measuring-your-usage) | 🟡 Moderate |

---

## 1. What tokens are and why they matter
`🟢 Easy`

A **token** is the unit AI models read and write in: roughly ¾ of an English word, or about 4 characters. "Token optimisation" means getting the job done with fewer of them.

Everything counts:

| Counts as tokens | Examples |
|---|---|
| **Input:** everything the AI reads | Your message, the whole conversation so far, files it opens, command output, your instructions file, tool definitions |
| **Output:** everything the AI writes | Its replies, code, explanations, plans, its "thinking" |

Why it matters:
- **Output costs more than input,** typically around **5×** per token. Long, chatty answers are expensive.
- **Every message re-sends the whole conversation.** Message 50 in a long chat carries messages 1–49 with it. Long sessions get more expensive with every turn.
- **Subscriptions have limits.** Wasted tokens mean hitting "usage limit reached" mid-task.
- **Less is often better.** A focused context gives more accurate answers. A bloated one leads to confusion and "context rot" (see the [Glossary](GLOSSARY.md)).

---

## 2. The ten habits that save the most
`🟢 Easy`

1. **One task per conversation.** Start a new chat when you switch topics.
2. **Plan with a strong model, build with a cheaper one.**
3. **Be specific the first time.** Retries are the biggest hidden cost.
4. **Tell it which files matter** so it doesn't read the whole project to find them.
5. **Ask for short answers:** "Just the code, no explanation" or "Answer in 3 bullet points."
6. **Don't paste huge logs.** Paste the error and the 10–20 lines around it.
7. **Keep your instructions file short** (`CLAUDE.md`, `AGENTS.md`, etc.).
8. **Turn off tools and connectors you're not using.**
9. **Stop it early** when it's going the wrong way (Esc in Claude Code). Don't let it finish a bad answer.
10. **Commit working code** so you can roll back instead of asking the AI to "undo" its way out of trouble.

---

## 3. Manage your conversation
`🟢 Easy`

The conversation history (the **context**) is re-read on every turn, so keeping it lean is the single biggest lever.

| Situation | Do this | In Claude Code |
|---|---|---|
| Switching to an unrelated task | Start a fresh conversation | `/clear` |
| Long session, same task, getting slow or forgetful | Summarise and continue | `/compact` (optionally add what to keep: `/compact keep the database decisions`) |
| Want to see what's filling the context | Check it | `/context` |
| Research, then plan, then build | Do each in its own session; carry over a short written summary, not the whole chat | Save the plan to a file, `/clear`, then "read PLAN.md and build step 1" |
| AI stuck in a loop | Stop. Roll back to the last commit. Fresh session with a clearer prompt. | Esc, then `/clear` |

**Hand-over trick:** before starting a new session, ask *"Summarise what we've decided and what's left to do in under 200 words."* Paste that into the new session instead of dragging the whole history along.

---

## 4. Pick the right model for the job
`🟢 Easy`

Bigger models are smarter but cost much more per token. Most tasks don't need the biggest one.

| Task | Model tier | Examples |
|---|---|---|
| Architecture, tricky debugging, planning | **Top / reasoning** | Claude Opus, GPT reasoning models |
| Everyday building from a clear plan | **Mid** | Claude Sonnet |
| Renaming, formatting, simple edits, quick questions | **Light / fast** | Claude Haiku, "mini" models |

- **Plan with a strong model, then implement with a cheaper one.** A good plan makes the cheap model's job easy.
- **Stick with one model per session** where you can. Switching mid-conversation can throw away cached savings (see [section 8](#8-prompt-caching)).
- **Auto model selection** (offered by Copilot and others) routes tasks for you and is sometimes discounted.
- In Claude Code, switch with `/model`.

---

## 5. Write prompts that don't need retries
`🟢 Easy`

Every "no, not like that" costs a whole round trip plus the growing history. The fix is a clear first prompt:

| Include | Example |
|---|---|
| **Where** | "In `src/reports/export.js`…" (saves it searching the whole project) |
| **What** | "…make the export button show 'No data to export' when the table is empty." |
| **Limits** | "Don't change any other files." |
| **Done means** | "Done when clicking export on an empty table shows the message and nothing crashes." |
| **Output wanted** | "Reply with just a one-line summary of the change." |

Also:
- **Batch small related changes** into one message rather than five separate ones.
- **Give it a way to check its own work** (tests, a linter, a way to run the app). Errors caught early don't snowball into long fix-it conversations.

---

## 6. Cut verbosity
`🟡 Moderate`

AI tools are chatty by default: they restate your question, narrate every step ("Let me look at the file…", "Great, now I'll…"), add long summaries and caveats, and explain code you didn't ask about. That's all **output tokens, the expensive kind**, and it also fills up the context for every future turn. Trimming it typically saves **20–40% of output tokens** with no loss in quality.

### Same answer, two ways

**Verbose (~120 tokens):**
> Great question! I'd be happy to help you with that. Let me take a look at the code. I've examined the file and I can see that the issue is in the date formatting function. The problem is that it's using the US format. I'll go ahead and fix that for you now. I've updated the function to use the Australian format (DD/MM/YYYY). This should resolve the issue you were experiencing. Let me know if you need anything else!

**Concise (~20 tokens):**
> Fixed: `formatDate()` in `utils/date.js` now uses DD/MM/YYYY instead of MM/DD/YYYY.

Same fix, about **one-sixth of the tokens**, and easier to read.

### Three ways to get concise output

**Level 1: ask (🟢 Easy).** Add to your prompt: *"Be brief. No preamble, no summary. Just the code and one line on what changed."*

**Level 2: make it a standing rule (🟡 Moderate).** Put it in your instructions file so every session follows it:

```markdown
## Response style
- Be concise. No preamble ("Great question", "I'd be happy to"), no closing offers.
- Don't narrate steps. Report the result.
- Don't repeat code back unless asked.
- Summaries: 3 bullets max.
- Explain only when asked or when something is risky.
```

**Level 3: install a verbosity-reducing skill, plugin or output style (🟡 Moderate).**
These package the rules above (and usually more) so they apply automatically, often with smarter behaviour such as "stay terse, but give full detail for security warnings".

| Type | What it does |
|---|---|
| **Terse-output skills/plugins** | Tell the AI to answer in the fewest words that keep the meaning: no filler, no narration, short final summaries |
| **"Build less" skills** | Push the AI to write the minimum code that works (reuse what exists, no unrequested extras), which cuts output *and* future re-reading |
| **Output styles** | Some tools (e.g. Claude Code) let you switch the whole response style; a concise style applies to every reply |
| **Lean-output nudges** | Some optimiser plugins automatically push the AI to be briefer as the context fills up |

An example minimal skill (see [Skills in the main guide](README.md#20-skills-plugins-and-marketplaces)):

```markdown
---
name: concise
description: Keeps replies short. Use for all coding tasks unless the user asks for a detailed explanation.
---

- Lead with the result. No preamble or sign-off.
- One-line summary of each change; no step-by-step narration.
- Don't echo code back. Reference file:line instead.
- Full detail only for errors, security risks, or when asked.
```

**Watch out for:**
- **Too terse can backfire.** If you have to ask "what do you mean?", you've spent more than you saved. Keep explanations for things that are risky or new to you.
- **Beginners:** while you're learning, *some* explanation is valuable. Ask for it when you want it, e.g. *"explain this one in plain English"*, rather than getting it on every reply.
- **Test before rolling out.** Try a skill on a few real tasks and compare. Good ones publish benchmarks showing where they help *and* where they don't.

---

## 7. Lean instructions files and fewer tools
`🟡 Moderate`

Your instructions file and every connected tool are loaded into **every single request**, so small savings here multiply.

**Instructions files (`CLAUDE.md`, `AGENTS.md`, `copilot-instructions.md`):**
- Keep them short and concrete: project-specific facts and rules, not general advice the AI already knows.
- Link to longer docs rather than pasting them in; the AI will open them when needed.
- Prune regularly. Delete rules that no longer apply.
- A good instructions file *saves* tokens overall, because the AI stops exploring to work out how your project is set up.

**Tools and connectors (MCP servers, plugins, extensions):**
- Each connected tool adds its description to every request. GitHub found unused tool definitions added **8–12 KB per call** in its own automated workflows. Removing them was its biggest quick win.
- Only enable the connectors you need for this project. Disable the rest.
- Where a simple command does the job (e.g. `gh pr diff`), it's often cheaper than a heavyweight tool integration.
- Be choosy with skills: install ones you actually use.

---

## 8. Prompt caching
`🟡 Moderate`

When the start of a request is identical to a recent one (same instructions, same earlier conversation), providers can reuse it from a **cache** at a big discount: on Anthropic models, cached input costs about **10% of the normal price**. Most coding tools do this automatically. Your job is just not to break it:

- **Stay in one session** for one task, rather than frequently starting over on the same work.
- **Don't switch models mid-conversation.** The cache is per model.
- **Don't edit your instructions file mid-session.** It changes the start of every request.
- **Set up connectors and settings before you start,** not halfway through.
- **Caches expire after a few minutes of inactivity** (longer on some plans). Resuming an old session after a break costs full price for the first message.

One published case study cut total AI spend by **59–70%** mainly by raising the cache hit rate from 7% to 84%.

---

## 9. Token-saving tools and plugins
`🔴 Hard`

For heavy users, there are open-source tools that cut tokens automatically. Most sit between the AI and your files or terminal and shrink what gets sent.

| Approach | What it does | Typical claimed saving |
|---|---|---|
| **Command-output compression** | Condenses long terminal output (test runs, builds, git logs) before the AI reads it | 60–90% on those commands |
| **Smart file reading** | On re-reads, sends only what changed, or just the outline (function names) instead of the whole file | 20–30% on reads; much more for code exploration |
| **Search/log compression** | Summarises long search results and logs | ~15% |
| **Loop detection** | Spots the AI retrying the same failing thing and stops it | Prevents runaway sessions |
| **Session checkpoints** | Saves key decisions before auto-compaction so they aren't lost | Fewer "re-explain everything" moments |

Examples to explore: [Token Optimizer](https://github.com/alexgreensh/token-optimizer) (plugin for Claude Code, Copilot, Cursor and others; the author reports ~28% fewer tokens over 30 days), and the [token-optimization topic on GitHub](https://github.com/topics/token-optimization?o=desc&s=stars) for command-output proxies, context compressors and terse-output skills.

⚠️ **Before installing any of these:**
- They see everything the AI sees: your code and command output. Only use well-established, open-source tools, and, on work projects, **check with whoever manages your tools first**.
- Claimed savings are the authors' own figures. Measure on your own work ([section 10](#10-measuring-your-usage)).
- Aggressive compression can hide detail the AI needed. If quality drops, turn it off.

---

## 10. Measuring your usage
`🟡 Moderate`

You can't improve what you can't see.

- **Claude Code:** `/context` shows what's filling the context window; `/usage` shows how much of your plan's limits you've used.
- **Claude app / claude.ai:** Settings → Usage.
- **GitHub Copilot:** your GitHub account's Copilot / billing settings show premium request usage.
- **API users:** the provider's console shows tokens per day, per model, per key. Use separate keys per project to see which one is costing what.

**Try this:** do the same small task twice, once your usual way and once applying [section 2](#2-the-ten-habits-that-save-the-most) and a concise-output rule. Compare the usage. Share what you find with the team.

---

## Sources and further reading

- [AI Token Optimization Guide](https://neuraltrust.ai/blog/ai-token-optimization-guide) (NeuralTrust): prompt compression, caching, model routing, output limits and monitoring
- [Optimize AI usage](https://docs.github.com/en/copilot/tutorials/optimize-ai-usage) (GitHub Docs): model choice, context management, cache preservation, plan-then-implement
- [Improving token efficiency in GitHub agentic workflows](https://github.blog/ai-and-ml/github-copilot/improving-token-efficiency-in-github-agentic-workflows/) (GitHub Blog): pruning unused tools, CLI instead of heavy tool calls, 19–62% reductions
- [Token Optimizer](https://github.com/alexgreensh/token-optimizer): open-source plugin for automatic context compression
- [GitHub topic: token-optimization](https://github.com/topics/token-optimization?o=desc&s=stars): community tools ranked by stars
- [AI Token Optimization](https://www.infosys.com/iki/perspectives/ai-token-optimization.html) (Infosys): enterprise perspective
