## Day 1 — API Keys and Setup

> **Goal:** Safely store your Anthropic API key, install the right packages, and prove your setup works with a test script.

---

### What is an API?

Imagine you walk into a restaurant. You don't go into the kitchen and cook your own food. You give your order to the **waiter**, and the waiter brings your food back.

An **API** works the same way:

- **Your Python program** = you sitting at the table
- **The API** = the waiter
- **Claude** = the chef in the kitchen

Your program sends a message. The API delivers it to Claude. Claude sends an answer back. You never need to know how Claude actually works — you just use the API.

```mermaid
flowchart LR
    A[Your Python program] -->|sends a request| B[Anthropic API]
    B -->|forwards message| C[Claude AI]
    C -->|generates reply| B
    B -->|returns response| A
    A -->|prints the answer| D[Your screen]
```

---

### What is an API key?

To use the Anthropic API you need an **API key**. Think of it like a password that proves to Anthropic's servers that your program is allowed to use Claude.

**Important rules about API keys:**

1. **Never put your API key directly in your code.** If you push your code to GitHub, the whole world can see it — and someone could use your key and rack up a huge bill on your account.
2. **Never share your API key** with anyone.
3. **Store it in a `.env` file** — a special file that stays on your computer and never gets uploaded.

```mermaid
flowchart TD
    A[Get API key from console.anthropic.com] --> B[Save it in a .env file]
    B --> C{Is .env in .gitignore?}
    C -->|Yes| D[Safe to push to GitHub]
    C -->|No| E[STOP — add it to .gitignore first!]
    D --> F[Python reads the key from the environment]
    F --> G[API call works]
```

---

### Step 1 — Get your API key (10 min)

1. Open Firefox and go to [https://console.anthropic.com](https://console.anthropic.com)
2. Sign up for a free account (ask a parent or guardian if you need help)
3. Click **API Keys** in the left sidebar
4. Click **Create Key**
5. Give it a name like `my-first-key`
6. **Copy the key now** — it starts with `sk-ant-...`

> You can only see the full key once. If you close the page without copying it, you will need to create a new key. That is fine — just delete the old one and make a fresh one.

---

### Step 2 — Create your project folder (5 min)

Open your terminal (`Ctrl + Alt + T`) and run these commands:

```bash
cd ~/projects
mkdir week-7-ai-chatbot
cd week-7-ai-chatbot
code .
```

VS Code opens with your new empty folder. This is where all of this week's work will live.

---

### Step 3 — Create the `.env` file (5 min)

In VS Code, create a new file called `.env` (yes, the dot is part of the name).

Add this one line — replace the placeholder with your actual key:

```
ANTHROPIC_API_KEY=sk-ant-your-actual-key-goes-here
```

Save the file. It should look something like this:

```
ANTHROPIC_API_KEY=sk-ant-api03-abc123...
```

> Your `.env` file is now sitting safely on your computer. Never send this file to anyone.

---

### Step 4 — Create `.gitignore` to protect your secret (5 min)

A `.gitignore` file tells Git "never upload these files to GitHub." You need to add `.env` to it right now, before you ever run `git add`.

Create a new file in VS Code called `.gitignore` and add these lines:

```
.env
__pycache__/
*.pyc
```

Save it. Now even if you run `git add .` by accident, your `.env` will be ignored.

```mermaid
flowchart LR
    A[git add .] --> B{Is file in .gitignore?}
    B -->|Yes — .env| C[File is skipped. Secret stays safe.]
    B -->|No — other files| D[File is staged and will be uploaded]
```

> Never remove `.env` from `.gitignore`. This is a habit every professional developer has.

---

### Step 5 — Install the required packages (5 min)

In the terminal (make sure you are in your project folder), run:

```bash
pip install anthropic python-dotenv
```

You will see output like this — it is downloading and installing the packages:

```
Collecting anthropic
  Downloading anthropic-...
Collecting python-dotenv
  Downloading python_dotenv-...
Successfully installed anthropic-... python-dotenv-...
```

These two packages do different things:

| Package         | What it does                                              |
| --------------- | --------------------------------------------------------- |
| `anthropic`     | Lets your Python program talk to the Anthropic API        |
| `python-dotenv` | Reads your `.env` file and loads the key into Python      |

---

### Step 6 — Check your folder structure (2 min)

Run `ls -a` in your terminal (the `-a` shows hidden files that start with a dot):

```bash
ls -a
```

You should see:

```
.  ..  .env  .gitignore
```

Your project folder now has two invisible files. You are ready.

---

### Hands-on exercise

**Build a setup test script (30 min)**

This exercise checks that everything is wired up correctly before you write any real chatbot code.

**Part 1 — Create `test_setup.py`**

In VS Code, create a new file called `test_setup.py` and type this out (don't copy-paste — typing it helps you remember it):

```python
# test_setup.py
# This script checks that our setup is correct.

import os
from dotenv import load_dotenv

# Step 1: load the .env file
load_dotenv()

# Step 2: read the API key from the environment
api_key = os.environ.get("ANTHROPIC_API_KEY")

# Step 3: check if the key was found
if api_key is None:
    print("ERROR: API key not found.")
    print("Check that your .env file exists and has ANTHROPIC_API_KEY=...")
else:
    # Show only the first 10 characters so we don't accidentally print the whole key
    print("API key found!")
    print("It starts with:", api_key[:10], "...")
    print("Length:", len(api_key), "characters")
    print("")
    print("Setup looks good. Ready for Day 2!")
```

**Part 2 — Run it**

```bash
python3 test_setup.py
```

If everything is correct, you will see:

```
API key found!
It starts with: sk-ant-api0 ...
Length: 108 characters

Setup looks good. Ready for Day 2!
```

**Part 3 — What happens if .env is missing?**

Try renaming your `.env` file temporarily:

```bash
mv .env .env.backup
python3 test_setup.py
mv .env.backup .env
```

You will see the error message. This is exactly what happens when people forget to set up their `.env` file. Now rename it back — you need it for the rest of the week.

**Part 4 — Check that .gitignore works**

Initialise Git and check the status:

```bash
git init
git status
```

Look at the output carefully. You should see `test_setup.py` listed under "Untracked files". You should NOT see `.env` listed at all. That means `.gitignore` is working.

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        test_setup.py
```

If `.env` does not appear — great job! Your secret is safe.

---

### What you learned today

- What an API is and why programs use them
- What an API key is and why you must keep it secret
- How to store a secret in a `.env` file
- How to protect secrets with `.gitignore`
- How to install Python packages with `pip`
- How to read an environment variable in Python with `os.environ.get()`

### Tip and trick for deeper understanding

#### Trick 1: Verify your key loaded without printing the whole thing
When `load_dotenv()` runs, it quietly copies your `.env` file into memory — but it does not tell you if it worked. A smart way to check is to look at just the first few characters of the key using `key[:10]`. If it starts with `sk-ant-`, you know it loaded correctly. If it comes back as `None`, your `.env` file is in the wrong folder or has a typo in the variable name.

```python
import os
from dotenv import load_dotenv

load_dotenv()
key = os.environ.get("ANTHROPIC_API_KEY", "")
print("Ready!" if key.startswith("sk-ant-") else "Key not found — check your .env file")
```

#### Trick 2: `.gitignore` only protects files Git has never seen before
Here is a trap that catches beginners: if you accidentally run `git add .env` *before* adding it to `.gitignore`, Git starts tracking that file — and adding it to `.gitignore` afterwards will NOT stop Git from uploading it. If that ever happens, run `git rm --cached .env` to tell Git to forget the file without deleting it from your computer. After that, `.gitignore` will protect it properly again.

#### Quick challenge (10 minutes)
1. Add a second variable to your `.env` file on a new line: `MY_NAME=YourActualName`
2. In `test_setup.py`, read that variable with `os.environ.get("MY_NAME")` and print `"Hello, [name]! Setup is ready."`
3. Run `git status` and confirm that `.env` still does not appear anywhere in the output — both secrets are protected.

---

### Day 1 tip

> The `.gitignore` step feels boring — until the day you accidentally push your API key to a public GitHub repo. That mistake can cost real money. Do it right on Day 1 and you will never have to worry about it.
