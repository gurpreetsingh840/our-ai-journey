## Day 5 — Week 1 Review: Scavenger Hunt & Preview

> **Goal:** Prove to yourself that you know it — from memory, no looking. Then preview what's coming next week.

---

### Terminal scavenger hunt

Do each of these **without** looking at your cheat sheet first. Then check:

**Round 1 — navigation**

```bash
# 1. Go to your home folder
# 2. Show your current location
# 3. List all files and folders
# 4. Move into projects/
# 5. List what's inside
# 6. Move back home in one command
```

<details>
<summary>Answers (try first!)</summary>

```bash
cd ~
pwd
ls
cd projects
ls
cd ~
```

</details>

---

**Round 2 — creating things**

```bash
# Create a folder called week1-review inside projects/
# Inside it, create 3 files: day1.md, day2.md, day3.md
# Verify they're all there
# Show the full tree from projects/ downward
```

<details>
<summary>Answers (try first!)</summary>

```bash
mkdir ~/projects/week1-review
cd ~/projects/week1-review
touch day1.md day2.md day3.md
ls
tree ~/projects/
```

</details>

---

**Round 3 — open and write**

1. Open `day1.md` in VS Code:

```bash
code ~/projects/week1-review/day1.md
```

2. Write 3 things you learned on Day 1, using Markdown (headings, bullet points)
3. Do the same for `day2.md` and `day3.md`
4. Preview each file with `Ctrl+Shift+V`

---

### Week 1 reflection

Open terminal and create one more file:

```bash
touch ~/projects/week1-review/reflection.md
```

Open it in VS Code and write:

```markdown
# Week 1 reflection

## What I found easy

-

## What was challenging

-

## What surprised me

-

## One thing I want to understand better

-
```

Fill it in honestly. There are no wrong answers.

---

### Preview: What is Git?

Watch this video together (about 5 minutes):

🎥 **[What is Git? — Git Explained in 100 Seconds](https://www.youtube.com/watch?v=hwP7WQkmECE)** (Fireship on YouTube)

After watching, discuss:

1. What problem does Git solve?
2. What's the difference between Git and GitHub?
3. What do you think "commit" means?

Write your answers in `reflection.md` — we'll see how your understanding changes after Week 2.

> 📖 **Read more:** [Git handbook by GitHub](https://guides.github.com/introduction/git-handbook/)

---

### Week 1 wrap-up checklist

Before moving on to Week 2, make sure you can do all of these without help:

- [ ] Open the terminal with `Ctrl + Alt + T`
- [ ] Navigate folders using `cd`, `ls`, `pwd`
- [ ] Create folders and files using `mkdir` and `touch`
- [ ] Open VS Code from the terminal using `code .`
- [ ] Write basic Markdown (headings, lists, bold, code blocks)
- [ ] Find your GitHub profile and read your README
- [ ] Explain what Git is in one sentence

If any box is unchecked — use the weekend to revisit that day's section.

---

### Tip and trick for deeper understanding

#### Trick 1: Retrieval beats rereading

To remember commands long-term, practice "recall first, then check":

1. Try from memory.
2. Run command.
3. Compare result to expectation.
4. Fix and repeat.

This builds real command fluency faster than reading notes repeatedly.

#### Trick 2: One command, three contexts

Pick one command and use it in three different places.

Example with `ls`:

- `ls ~`
- `ls ~/projects`
- `ls ~/projects/notes`

Same command, different context. This teaches transfer, which is the core of real skill.

#### Weekend mini challenge (optional)

Create a fresh folder `~/projects/week1-speedrun` and reproduce the full Week 1 structure from memory in under 15 minutes:

- Create folders
- Create files
- Open in VS Code
- Write one short Markdown note

If you can do it without checking guides, Week 1 is fully internalized.

---

### Day 5 tip

> Sat/Sun are catch-up and go-ahead days. If you finished everything — try exploring GitHub: search for "awesome python" and browse the repos people have built. See what's possible.
