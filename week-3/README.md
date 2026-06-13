# Week 3 — GitHub: Remote Repos, Pull Requests & Collaboration

> **Who this is for:** Everyone following along — you should have finished Week 2 (local Git) before starting here.
> **OS:** Ubuntu Linux
> **Time:** ~1 hour per day, Monday to Friday
> **Goal by end of week:** You can push code to GitHub, collaborate with a partner using branches and pull requests, and contribute to someone else's project using a fork.

---

## Overview

Week 3 is where Git goes from something you do alone on your laptop to something you do *with other people on the internet*. That is the heart of how real software gets built — thousands of developers sharing code, reviewing each other's work, and merging changes together. This week you learn exactly that workflow.

Each day builds on the previous one, so work through them in order.

## Daily plan

| Day                | Title                                 | Goal                                                                              |
| ------------------ | ------------------------------------- | --------------------------------------------------------------------------------- |
| [Day 1](./day1.md) | Push to GitHub                        | Link your local repo to GitHub and upload your commits for the first time.        |
| [Day 2](./day2.md) | Clone and Pull                        | Download any repo from GitHub and keep it up to date with `git pull`.             |
| [Day 3](./day3.md) | Branches on GitHub                    | Push a local branch to GitHub and merge it using GitHub's merge button.           |
| [Day 4](./day4.md) | Pull Requests                         | Open a pull request, add a description, leave a review comment, and merge it.     |
| [Day 5](./day5.md) | Fork & Contribute + Week 3 Review     | Fork a partner's repo, make a change, and open a PR back to their original repo.  |

## Suggested flow

1. Start with [Day 1](./day1.md) — you need a repo on GitHub before any of the other days make sense.
2. [Day 2](./day2.md) introduces `git clone` and `git pull` — practice these on a partner's repo or any public repo you like.
3. [Day 3](./day3.md) and [Day 4](./day4.md) work best in pairs — one person reviews the other's pull request.
4. [Day 5](./day5.md) ties everything together with the full fork-to-PR workflow and reviews the whole week.

---

## Week 3 quick reference

| Command                          | What it does                                              |
| -------------------------------- | --------------------------------------------------------- |
| `git remote add origin URL`      | Link your local repo to a GitHub repo                     |
| `git remote -v`                  | Show the remote repos linked to your local repo           |
| `git push -u origin main`        | Upload your commits to GitHub for the first time          |
| `git push`                       | Upload new commits after the first push                   |
| `git pull`                       | Download the latest changes from GitHub                   |
| `git clone URL`                  | Download a complete repo from GitHub to your computer     |
| `git push origin branch-name`    | Push a local branch up to GitHub                         |
| `git fetch`                      | Check GitHub for new changes without downloading them yet |
| `git branch -r`                  | List all branches that exist on GitHub (remote branches)  |
| `git checkout -b branch-name`    | Create a new branch and switch to it immediately          |

---

_End of Week 3 — next up: Week 4 — Python fundamentals_
