# Week 2 — Git: Local Version Control

> **Who this is for:** Everyone following along — you finished Week 1.
> **OS:** Ubuntu Linux
> **Time:** ~1 hour per day, Monday to Friday
> **Goal by end of week:** You can track every change you make to your code, write meaningful commit messages, use branches to experiment safely, and undo mistakes — all without touching the internet.

---

## Overview

This week is all about Git — the tool every developer on the planet uses to save and track their work. Think of Git as a **save-game system** for your code. You can take a snapshot whenever you like, scroll back to any previous snapshot, and even spin up a separate copy of your project to try risky ideas without breaking the original.

Everything this week happens on your own computer — no internet needed. Week 3 will push your work up to GitHub for the world to see. This week is about building the foundation.

## Daily plan

| Day                | Title                              | Goal                                                                              |
| ------------------ | ---------------------------------- | --------------------------------------------------------------------------------- |
| [Day 1](./day1.md) | What is Git? init, status, add     | Turn a folder into a Git project and stage your first file.                       |
| [Day 2](./day2.md) | git commit — saving a snapshot     | Make your first commits and read your project's history with git log.             |
| [Day 3](./day3.md) | git diff — seeing what changed     | Inspect changes before committing and navigate history.                           |
| [Day 4](./day4.md) | Branches — working in parallel     | Create a branch, experiment safely, and merge your changes back.                  |
| [Day 5](./day5.md) | Week 2 Review + git restore (undo) | Undo mistakes with git restore and prove you know Git from memory.                |

## Suggested flow

1. Start with [Day 1](./day1.md) — configure Git and create your first repository.
2. [Day 2](./day2.md) and [Day 3](./day3.md) build on the same `my-story/` project from Day 1 — work through them in order.
3. [Day 4](./day4.md) introduces branches — the most powerful Git concept this week.
4. Use [Day 5](./day5.md) at the end of the week to test yourself without looking at your notes.

---

## Week 2 quick reference

| Command                          | What it does                                   |
| -------------------------------- | ---------------------------------------------- |
| `git init`                       | Start tracking a folder with Git               |
| `git status`                     | See what has changed since the last commit     |
| `git add filename`               | Stage one file for the next commit             |
| `git add .`                      | Stage all changed files at once                |
| `git commit -m "message"`        | Save a snapshot with a description             |
| `git log`                        | Show full commit history                       |
| `git log --oneline`              | Show compact history (one line per commit)     |
| `git diff`                       | Show changes that are not yet staged           |
| `git diff --staged`              | Show changes that are staged                   |
| `git show`                       | Show what the most recent commit changed       |
| `git show abc1234`               | Show what a specific commit changed            |
| `git branch`                     | List all branches                              |
| `git branch name`                | Create a new branch called name                |
| `git switch name`                | Switch to a branch (modern style)              |
| `git checkout name`              | Also switches to a branch (older style)        |
| `git merge name`                 | Merge branch name into the current branch      |
| `git restore filename`           | Undo unsaved changes to a file                 |
| `git restore --staged filename`  | Unstage a file (move it back out of the box)   |

---

_End of Week 2 — next up: Week 3 — GitHub: remote repos and collaboration_
