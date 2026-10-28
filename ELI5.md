# GitHub, Explained Like You're 5

The super-simple version. No jargon, no commands. ← [Full guide](guide/README.md)

> Want to know how to use Claude to do all of this for you? Read the **[Claude WTFM](CLAUDE-WTFM.md)**.

---

## 🏠 What is GitHub?

Imagine a giant building full of **toy boxes**.

- **GitHub** is the building.
- **Your account** is your own toy box. You decide who else can play with it.
- Each **toy** in a box is a **repository** (a "repo"): one project, like an app, a website or a guide.
- An **organisation** (an "org") is a toy box shared by a whole team or company.
- **Git** is a magic notebook that writes down every single change anyone makes to a toy, so you can always go back.

---

## 📖 The words, made easy

| Big word | What it really means | Like… |
|---|---|---|
| **Repo** | A project folder with its whole history | A toy with its own diary |
| **Branch** | Your own copy to play with | Drawing on tracing paper, not the real picture |
| **`main`** | The real, working version | The picture on the fridge |
| **Commit** | Saving your work with a short note | Taking a photo of your Lego tower |
| **Push** | Sending your saved work up to GitHub | Posting the photo to the family group chat |
| **Pull** | Getting everyone else's latest work | Checking the group chat for new photos |
| **Clone** | Downloading a repo to your computer | Bringing the toy home to play with |
| **Fork** | Your own copy of someone else's repo | Photocopying a friend's colouring book |
| **Pull request (PR)** | "Please can my change go on the fridge?" | Asking a grown-up to check your drawing |
| **Review** | Someone checks your change | The grown-up looking at it |
| **Merge** | Your change joins the real version | Your drawing goes on the fridge |
| **Issue** | A note saying "this is broken" or "wouldn't it be cool if…" | A sticky note on the toy box |
| **Private / Public** | Who can see the repo | Toy box with a lid vs. toy box in the park |

---

## 🔁 The one big rule: never draw on the fridge picture

Don't change `main` directly. Instead:

```
1. Make your own copy    (branch)
2. Change it             (edit)
3. Save it               (commit)
4. Send it up            (push)
5. Ask to add it         (pull request)
6. Someone checks it     (review, even if that "someone" is you or Claude)
7. It joins the real one (merge)
```

If you mess up your copy, who cares? The fridge picture is safe. 🎉

---

## 🚪 Getting started (do this once)

1. Make a free GitHub account at <https://github.com/signup>.
2. Turn on **two-factor login** (Settings → Password and authentication). It's a lock on your door.
3. Make your first repo: click **+** (top right) → **New repository** → give it a name → choose **Private** → tick **Add a README** → **Create repository**.
4. Joining a team? Send them your GitHub username so they can invite you, then click **Accept** on the invite email.

---

## 🙋 What can I do? (No coding needed!)

| I want to… | Do this |
|---|---|
| **Say something is broken** | Open the repo → **Issues** → **New issue**. Say what you expected, what happened, and add a screenshot. |
| **Write down an idea** | Open an **Issue** for it, or use **Discussions** if the repo has them turned on |
| **Fix a typo** | Open the file → click the ✏️ pencil → fix it → **Commit changes** (or **Propose changes** on someone else's repo) |
| **Change or build something** | Make a branch, change it, open a pull request (or ask Claude to: see the [Claude WTFM](CLAUDE-WTFM.md)) |
| **Let someone see my private repo** | Repo → **Settings** → **Collaborators** → **Add people** |
| **Check someone's work** | Open their pull request → **Files changed** → leave nice comments → **Approve** |

---

## 🛑 Things you NEVER do

1. **Never** put passwords, keys or secret codes in a repo. (If you do by accident, change that password or key straight away. Deleting it isn't enough: GitHub remembers.)
2. **Never** put customer or personal info in a repo or in AI chats.
3. **Never** change `main` directly on anything important. Always branch → pull request.
4. **Never** merge or approve something you don't understand. Ask first.
5. **Never** make a repo **public** unless you're sure everything in it is OK for the whole world to see.

---

## 😱 Uh oh, something went wrong

| What happened | Don't panic, do this |
|---|---|
| "I broke it" | That's what branches are for. Go back to your last commit, or ask Claude for help. |
| "It won't let me push" | Something changed on GitHub that you don't have yet. **Pull** first, then push again. |
| "It says merge conflict" | Two changes touched the same line. Ask Claude: *"Help me fix this merge conflict."* |
| "Permission denied" | It's not your repo, or you haven't been invited yet. Ask the owner. |
| "I don't know what's going on" | **Stop.** Don't force anything. Copy the message and ask Claude: *"Explain this like I'm 5."* |

---

## 👣 Where next?

- 🧠 **Use Claude to help:** [Claude WTFM](CLAUDE-WTFM.md)
- 🎓 **Learn by doing (1–2 hrs):** [AI Starter Training](starter-training/README.md)
- 📚 **The full grown-up guide:** [Guide](guide/README.md)
- 🔤 **More words explained:** [Glossary](guide/GLOSSARY.md)
