# Module 11: Deploy as a web app
`🟡 Moderate → 🔴 Hard` · 30 min

**Deploying** means putting your app somewhere other people can open it in a browser, without needing a copy of your files.

> ⚠️ Do [Module 10: Keeping data secure](10-data-security.md) first. Once it's deployed, **the host decides who can see it**, not you.

## 1. Choose where it runs

| Option | Best for | Who can see it | Level |
|---|---|---|---|
| **GitHub Pages** | Harmless demos, plain HTML apps | ⚠️ **Anyone on the internet** (even from a private repo) | 🟢 |
| **Netlify / Vercel / Cloudflare Pages** | Public sites, prototypes, small apps with serverless functions | Public by default; password or login protection on paid plans | 🟡 |
| **Azure Static Web Apps** | **Internal company tools**: can require company Microsoft sign-in | Only people you allow (set up with IT) | 🟡 |
| **Azure App Service / containers** | Apps with a real backend and database | Controlled by IT / login | 🔴 |
| **Power Apps** | Forms and simple data apps on Microsoft 365 data (SharePoint, Excel, Dataverse) | Company users | 🟡 |

**Rule of thumb:** anything with real or work data → a **private option with sign-in** (at work, agree it with IT, e.g. Azure with company sign-in, or Power Apps). Public hosts → harmless demos only.

## 2. How modern deployment works

```
you push to main  →  host notices  →  host builds your app  →  new version is live
```

This is called **CI/CD** (continuous integration / continuous deployment). You connect the host to your GitHub repo once; after that, **every push to `main` redeploys automatically**. That's another reason to use branches and pull requests: `main` = what's live.

## 3. Walkthrough: a quick public demo with GitHub Pages 🟢

Only for a harmless app like your training project, in **your own repo** from Module 8:

1. Your repo on GitHub → **Settings → Pages**.
2. **Source:** Deploy from a branch → `main` → `/ (root)` → **Save**.
3. Wait a minute, then check the **Actions** tab. Your site is at `https://<your-username>.github.io/<repo-name>/`.
4. Open it on your phone too.

To take it down: Settings → Pages → **Unpublish site**.

## 4. Walkthrough: an internal tool on Azure Static Web Apps 🔴

This needs an Azure subscription; **talk to IT first**. Then ask your AI agent:

> I have a plain HTML/JS app in this repo. Walk me through deploying it to Azure Static Web Apps from GitHub, step by step, explaining each step in plain English. It must only be accessible to people signing in with our organisation's Microsoft accounts. Fetch the current Microsoft documentation rather than relying on memory. Don't run any commands until I say so.

What you'll end up with:
- A GitHub Actions workflow file in `.github/workflows/` that deploys on every push to `main`
- A `staticwebapp.config.json` that requires sign-in for every page
- A URL like `https://<random-name>.azurestaticapps.net` (IT can add a nicer company domain)

## 5. Apps with a backend and database 🔴

If your app needs to save shared data, it needs a **backend** (server code) and a **database**. The rules from [Module 10](10-data-security.md) matter most here:
- Keys and connection strings go in the host's **secret settings**, never in code.
- Permissions are enforced on the **server or database**, not just in the browser.
- Plan it before building: *"Suggest the simplest secure way to host this app with a small database for about 20 internal users, and explain the trade-offs and monthly cost."*

## ✅ Checkpoint

- [ ] I know which hosting options are public and which can be company-only
- [ ] (Optional) I deployed my training app to GitHub Pages and opened it on my phone

<details>
<summary>If something goes wrong</summary>

- **Pages shows 404:** wait 2–3 minutes; check the Actions tab for a red ❌; make sure `index.html` is at the root of the repo.
- **It works locally but not online:** file names are case-sensitive online (`Logo.png` ≠ `logo.png`). Paths starting with `C:\` won't work. Ask the AI to make all paths relative.
</details>

← [Module 10](10-data-security.md) · **Next: [Module 12: Deploy as a mobile app](12-deploy-mobile-app.md)** →
