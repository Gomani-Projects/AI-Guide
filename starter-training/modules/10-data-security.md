# Module 10: Keeping data secure
`🟢 Easy → 🟡 Moderate` · 20 min · **Do this before modules 11–14**

The moment a tool touches real data (yours, your employer's or your customers'), or goes anywhere other than your own computer, security becomes your job. Most leaks aren't clever hacks. They're a key pasted in the wrong place, a "public" tick-box, or a spreadsheet emailed to the wrong person.

## 1. Know what kind of data you're handling 🟢

| Class | Examples | OK in an AI prompt? | OK in a repo? |
|---|---|---|---|
| **Public** | Published specs, marketing text | ✅ | ✅ |
| **Internal** | Procedures, non-sensitive project info | ✅ **approved AI tools only** (at work: the ones your employer approves) | ✅ private repo |
| **Confidential** | Costs, contracts, technical data, designs | ⚠️ only if the data owner (e.g. IT or your manager) has approved that tool for it | ⚠️ private repo, restricted access |
| **Personal / customer** | Names, phone numbers, addresses, HR or health info, client data | ❌ | ❌ |
| **Secrets** | Passwords, API keys, tokens, connection strings | ❌ never | ❌ never |

When in doubt, treat it as the next class up and ask.

**Build and test with fake data.** Ask your AI: *"Make me a realistic fake sample CSV with the same columns as this header row."* (Paste only the header, not the data.) There's a sample in [`projects/_sample-data/`](../projects/_sample-data/).

## 2. Use AI tools safely 🟢

- For work, use the **AI tools and accounts your employer approves**. Free personal accounts may use your data for training; check the tool's privacy settings.
- Don't paste confidential or personal data into prompts. Describe the *shape* of the data instead.
- Read permission prompts before the AI runs commands or reads folders. Don't point it at a folder full of sensitive files.
- Don't install AI plugins, MCP servers or extensions from unknown sources. They can see what the AI sees.

## 3. Keep secrets out of code 🟡

- Put secrets in a **`.env`** file, and make sure `.env` is in **`.gitignore`** (it already is in this repo).
- Commit a **`.env.example`** with the variable names but fake values, so others know what's needed.
- On hosting platforms, put secrets in the platform's **environment variables / secrets** settings, never in code.
- **Leaked a secret?** **Change (rotate) the key immediately**, and tell whoever owns the system or repo. Deleting the commit isn't enough: it stays in history and may already be copied.

Ask your AI: *"Scan this project for any hard-coded passwords, keys, tokens or connection strings, and move them to a .env file."*

## 4. Build apps that protect data 🟡

If your app has logins or stores data, give your AI these rules (put them in `CLAUDE.md` / `AGENTS.md`):

```markdown
## Security rules
- Deny by default: users see only what they are explicitly allowed to see.
- Enforce permissions on the server/database, never only in the browser.
- Validate all input on the server.
- Never expose secrets or keys to the browser or mobile app.
- Use HTTPS everywhere.
- Don't log personal data or secrets.
- If a requirement about access or data is unclear, stop and ask.
```

| Topic | What to check |
|---|---|
| **Logins** | Use an existing sign-in provider ("Sign in with Microsoft/Google", or your employer's single sign-on) rather than building your own password system. |
| **Least privilege** | Each user and each service gets only the access it needs. Read-only where possible. |
| **Database rules** | With Supabase/Firebase, turn on **Row Level Security** / security rules so users can only reach their own rows. |
| **Dependencies** | Every package you install is someone else's code. Prefer few, well-known ones. Ask: *"Check this project's dependencies for known vulnerabilities."* |
| **Sharing** | Check every "public", "anyone with the link" or "publish to web" setting. Default to private. |

## 5. Before you share or deploy anything: checklist 🟢

- [ ] Only fake or approved data in the repo and the app
- [ ] No secrets in code; `.env` is git-ignored
- [ ] Repo is **private**
- [ ] I know who can access the deployed app, and it's only the people who should
- [ ] Logins use an existing sign-in provider (if the app has users)
- [ ] I asked the AI for a security review in a fresh session, and fixed what it found
- [ ] The data owner (e.g. IT, for work data) has OK'd it if it touches confidential data

## ✅ Checkpoint

- [ ] I can name the five data classes and what's allowed for each
- [ ] I know what to do if a secret leaks

← [Module 9](09-next-steps.md) · **Next: [Module 11: Deploy as a web app](11-deploy-web-app.md)** →
