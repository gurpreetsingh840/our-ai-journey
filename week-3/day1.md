## Day 1 — Push to GitHub

> **Goal:** Link your local Git repo to GitHub and upload your commits so your code lives on the internet for the first time.

---

### What does "remote" mean?

So far in Week 2, all your Git work lived only on your laptop. The commits, the branches, the history — all local. Only you could see it.

A **remote** is a copy of your repo that lives somewhere else — in this case, on GitHub's servers. When you push to the remote, your code travels over the internet and gets stored on GitHub. Now anyone you share the link with can see it. And you have a backup.

> **Analogy:** Your local repo is like a notebook on your desk. GitHub is like a photocopier connected to the internet — you push your notebook there and now your teacher, your partner, or anyone in the world can read it. Your original notebook is still on your desk, unchanged.

```mermaid
flowchart LR
    A[Your laptop\nlocal repo] -->|git push| B[GitHub\nremote repo]
    B -->|git pull| A
    C[Partner's laptop] -->|git push| B
    B -->|git pull| C
```

The two arrows matter — you can **push** your changes up, and **pull** other people's changes down. That is the whole idea of collaboration.

---

### Step 1 — Create a new repo on GitHub

Before you can push, you need an empty repo on GitHub to push *into*.

1. Open Firefox and go to [https://github.com](https://github.com)
2. Click the **+** icon (top right) → **New repository**
3. Fill in:
   - **Repository name:** `my-story`
   - **Description:** `My short story project from Week 2`
   - Set to **Public**
   - **Do NOT** tick "Add a README file" — leave everything unticked
4. Click **Create repository**

GitHub shows you an empty repo with setup instructions. Keep this page open — you will copy the URL from it in a moment.

> **Why leave README unticked?** If you add a README on GitHub, the repo already has one commit. That makes connecting it to your local repo more complicated. Start empty and push everything yourself.

---

### Step 2 — Connect your local repo to GitHub

Open the terminal in VS Code (`` Ctrl+` ``) and navigate to your `my-story` folder from Week 2:

```bash
cd ~/projects/github/my-story
```

Check that it is a Git repo with some commits already:

```bash
git log --oneline
```

You should see your commits from Week 2. Good.

Now link this local repo to the GitHub repo you just created. On the GitHub page you should see the URL — it looks like `https://github.com/YOUR-USERNAME/my-story.git`. Copy it, then run:

```bash
git remote add origin https://github.com/YOUR-USERNAME/my-story.git
```

Replace `YOUR-USERNAME` with your actual GitHub username.

The word **origin** is just a nickname for your remote. You could call it anything, but every developer in the world calls it `origin` by convention. Use that name.

Confirm it saved:

```bash
git remote -v
```

Output:

```
origin  https://github.com/YOUR-USERNAME/my-story.git (fetch)
origin  https://github.com/YOUR-USERNAME/my-story.git (push)
```

Two lines — one for downloading (fetch), one for uploading (push). Both pointing at your GitHub repo.

```mermaid
flowchart TD
    A[cd into your local repo] --> B["git remote add origin URL"]
    B --> C["git remote -v to confirm"]
    C --> D[Local repo is now linked to GitHub!]
```

---

### Step 3 — Personal Access Tokens

When you try to push, GitHub will ask you to prove you are who you say you are. GitHub no longer accepts plain passwords — instead it uses a **Personal Access Token (PAT)**.

> **Analogy:** A PAT is like a special key card for your GitHub account. You generate one in your account settings, and you use it instead of your password when Git asks. You can delete the key card at any time if you think someone stole it, without changing your actual GitHub password.

**Generate a token — follow these steps exactly:**

1. On GitHub, click your profile picture (top right) → **Settings**
2. Scroll to the very bottom of the left sidebar → **Developer settings**
3. Click **Personal access tokens** → **Tokens (classic)**
4. Click **Generate new token** → **Generate new token (classic)**
5. In the **Note** box type: `my-ubuntu-laptop`
6. Set **Expiration:** 90 days
7. Under **Select scopes**, tick **repo** (this gives full access to your repos)
8. Scroll down → **Generate token**
9. **Copy the token immediately** — GitHub only shows it once

It looks like this: `ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx`

Paste it into a text file somewhere safe while you finish today's lesson.

---

### Step 4 — Push your commits to GitHub

Upload your local commits:

```bash
git push -u origin main
```

Git asks for your credentials:

- **Username:** your GitHub username
- **Password:** paste your **PAT** (not your regular GitHub password)

> **Why `-u`?** The `-u` flag means "set upstream". It tells Git: from now on, when I say `git push` in this folder, always push to `origin main`. You only need `-u` the very first time. After that, just type `git push`.

If it works, you see something like:

```
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Writing objects: 100% (6/6), 800 bytes | 800.00 KiB/s, done.
To https://github.com/YOUR-USERNAME/my-story.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

Go to your GitHub repo in Firefox and refresh. **Your files are there.** Your commits, your history, your whole story — live on the internet.

```mermaid
flowchart LR
    A["git push -u origin main"] --> B[Git asks: username?]
    B --> C[Git asks: password?]
    C --> D[Paste your PAT]
    D --> E[Commits travel to GitHub]
    E --> F[Your repo is live!]
```

---

### Step 5 — Make a new commit and push again

Let's confirm the everyday workflow. Add one more line to your story:

```bash
echo "" >> story.txt
echo "The end." >> story.txt
```

Stage, commit, and push:

```bash
git add story.txt
git commit -m "Add ending to story"
git push
```

No `-u` needed this time. Just `git push`. Refresh GitHub — the new commit is there instantly.

> **The everyday loop: write → add → commit → push.** That is what you will do every single day as a developer.

---

### Step 6 — Save your token so you do not have to type it every time

Typing your token on every push gets old fast. Tell Git to remember it:

```bash
git config --global credential.helper store
```

The next time you enter your token, Git saves it. Future pushes will not ask for it again on this computer.

> **Note:** This saves the token as plain text in your home folder. That is fine for your personal laptop. Never use this on a shared or school computer.

---

### Hands-on exercise

Work through all the steps above from the beginning. When you finish, complete these bonus challenges:

**Challenge A — Explore your repo on GitHub**

```bash
# Nothing to type — do this in Firefox
```

1. Go to `https://github.com/YOUR-USERNAME/my-story`
2. Click `story.txt` — you can read the file right in the browser
3. Click the **clock icon** (Commits) — every commit from Week 2 is listed
4. Click any commit hash — you see exactly what changed in that commit (green = added, red = removed)

**Challenge B — Edit a file directly on GitHub**

1. Click `story.txt` in your repo
2. Click the **pencil icon** (Edit this file)
3. Add a new line: `(A story by YOUR NAME)`
4. Scroll down → click **Commit changes** → **Commit changes**

**Challenge C — Pull the GitHub change back down**

GitHub now has a commit your laptop does not have. Sync it:

```bash
git pull
```

Expected output:

```
Updating abc1234..def5678
Fast-forward
 story.txt | 1 +
 1 file changed, 1 insertion(+)
```

Confirm the line is now in your local file:

```bash
cat story.txt
```

**That round trip — push up, edit on GitHub, pull back down — is the foundation of everything you build on this week.**

---

### What you learned today

- What a "remote" is — a copy of your repo stored on the internet
- How to create an empty GitHub repo and link it to a local repo with `git remote add origin URL`
- What a Personal Access Token is and how to generate one in GitHub settings
- How to upload commits with `git push -u origin main` (first time) and `git push` (every time after)
- How to sync changes from GitHub back to your laptop with `git pull`
- How to browse your commits and files directly on GitHub's website

---

### Tip and trick for deeper understanding

#### Trick 1: "origin" is just a nickname — you can check it any time
The name `origin` is not a special Git word — it is simply the nickname you chose when you ran `git remote add origin`. You could have called it `github` or `cloud` and every command would still work. The whole developer world agreed on `origin` the same way everyone agreed to call the big cold box a "fridge". Run `git remote -v` any time you forget what URL your remote is pointing at — Git prints both the fetch and push addresses.

#### Trick 2: The `-u` flag links your branches once and for all
When you run `git push -u origin main`, Git permanently ties your local `main` branch to `origin/main`. After that one-time setup, typing just `git push` is enough — Git already knows where to send the commits. The `-u` stands for "set upstream". If you ever clone the repo to a new computer, you need to do `-u` again for that fresh copy, because the link is stored on your laptop, not on GitHub.

#### Quick challenge (10 minutes)
Confirm your remote is set up correctly, make one small change, and practise the short-form push:

```bash
# 1. Verify origin points at the right GitHub URL
git remote -v

# 2. Add one sentence to your story and commit it
echo "And they all coded happily ever after." >> story.txt
git add story.txt
git commit -m "Add final sentence"

# 3. Push with NO flags — this works because -u was already set
git push
```

Refresh your GitHub repo in Firefox and confirm the new commit is there.

---

### Day 1 tip

> If `git push` gives you an error saying "rejected" or "non-fast-forward", it usually means GitHub has a commit your laptop does not have yet. Run `git pull` first, then `git push` again. Pull before you push — start building that habit today.
