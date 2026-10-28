# Module 6: Commit and push
`🟢 Easy` · 5 min

- **Commit** = save a snapshot on your computer, with a message.
- **Push** = upload your commits to GitHub.

## With GitHub Desktop

1. Check **Current branch** is `training/<your-username>` (**not** `main`).
2. In the **Changes** tab, tick the files in your folder.
3. Bottom left, write a **summary**: what you did, in present tense:
   - ✅ `Add reaction-time game`
   - ✅ `Add unit converter with empty-input check`
   - ❌ `stuff`, `update`, `done`
4. Click **Commit to training/<your-username>**.
5. Click **Push origin** (top right).

## Or ask your AI agent

> Commit the changes in projects/<my-username>/ with a clear message, then push my branch.

Watch what it does, and check it's committing on **your** branch.

## Commit more than once

Good habit: commit every time something works. If the AI breaks things later, you can go back. Make one more small improvement, then commit and push again. You'll see both commits in the **History** tab.

## See it on GitHub

In GitHub Desktop: **Repository → View on GitHub**. Switch the branch dropdown from `main` to your branch and open `projects/<your-username>/`. Your files are on GitHub.

## ✅ Checkpoint

- [ ] I made at least 2 commits with clear messages
- [ ] I can see my files on GitHub on my branch

<details>
<summary>If something goes wrong</summary>

- **About to push to `main`:** stop. Switch to your branch: **Current branch → training/<your-username>**. If you committed on main, see [the guide's troubleshooting](../../guide/README.md#23-when-things-go-wrong).
- **"Would publish a private email":** GitHub → Settings → Emails, then in GitHub Desktop set your Git email to the `noreply` address (File → Options → Git).
- **"Permission denied" / 403:** you're pushing to someone else's copy of the course. Check **Repository → Repository settings → Remote** points at **your** copy (Module 2).
</details>

← [Module 5](05-test-and-review.md) · **Next: [Module 7: Open a draft pull request](07-draft-pull-request.md)** →
