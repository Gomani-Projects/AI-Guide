# AI Coding Guides

**Status:** planning

## Goal
A generic, beginner-friendly set of guides for anyone learning GitHub and AI coding tools (especially Claude). No company or org details, so it can be handed to anyone or copied into their own repo.

## Contents
| Start here | What it is |
|---|---|
| [ELI5.md](ELI5.md) | GitHub explained like you're 5 |
| [CLAUDE-WTFM.md](CLAUDE-WTFM.md) | How to use Claude (Chat, Code tab, CLI), step by step |
| [starter-training/](starter-training/README.md) | Hands-on 1–2 hour course: build a small app with AI and open a draft pull request |
| [guide/](guide/README.md) | The full guide, plus [Glossary](guide/GLOSSARY.md) and [Token Optimisation](guide/TOKEN-OPTIMISATION.md) |

## Notes
- `starter-training/` is meant to become its own repo (learners copy it in Module 2). Split it out with:
  `git subtree split --prefix=apps/ai-coding-guides/starter-training -b starter-training-export`
- Links between the guides are relative, so the folder works anywhere as long as it stays together.
