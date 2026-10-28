# Module 8: Put your app in your own repo
`🟡 Moderate` · 10 min

Your app lives inside your copy of the course. Give it a home of its own where **you** own `main` and can keep building.

## Step 1: Copy your app to a new folder

Copy your folder `projects/<your-username>/` to somewhere **outside** the training repo, e.g. `Documents\GitHub\my-reaction-game`.

(Or ask your AI: *"Copy projects/<my-username>/ to Documents\GitHub\<app-name>."*)

## Step 2: Turn it into a repo and publish it

**With GitHub Desktop:**
1. **File → Add local repository…** → choose your new folder.
2. It says *"This directory does not appear to be a Git repository"*. Click **create a repository**, then **Create repository**.
3. Click **Publish repository**.
   - **Name:** your app name, e.g. `my-reaction-game`
   - **Keep this code private:** ✅ ticked
   - **Organization:** choose **None** to put it on your personal account.
4. Click **Publish repository**.

**Or ask your AI agent:**
> Make Documents\GitHub\<app-name> a Git repository, commit everything, and publish it as a private repo called <app-name> on my personal GitHub account.

## Step 3: Make a change and push it

This is your repo, so you can commit straight to `main`:
1. Ask your AI for one more improvement in the new folder.
2. Commit it in GitHub Desktop and click **Push origin**.
3. **Repository → View on GitHub.** There it is.

> 💡 In team projects, you'd still use branches and pull requests, even when you *could* push to `main`. On a personal practice repo it's fine to keep it simple.

## Optional 🔴: put it on the web

A plain HTML app can be published for free with **GitHub Pages** (repo → Settings → Pages). ⚠️ The website is **public** even if the repo is private, so only do this with harmless demo apps. See [Publishing with GitHub Pages](../../guide/README.md#19-publishing-with-github-pages).

## ✅ Checkpoint

- [ ] My app is in its own private repo on my GitHub account
- [ ] I pushed at least one change to it

← [Module 7](07-draft-pull-request.md) · **Next: [Module 9: What next?](09-next-steps.md)** →
