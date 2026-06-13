# Week 7 — Python + AI APIs: Building Real Applications

> **Who this is for:** Students who have completed Weeks 1–6 (Python basics, Git, the terminal).
> **OS:** Ubuntu Linux
> **Language:** Python 3
> **Time:** ~45–60 min per day, Monday to Friday
> **Goal by end of week:** You have a working AI-powered chatbot that runs in the terminal, uses the Anthropic Claude API, and lives on GitHub.

---

## Overview

This week you connect Python to a real AI service. You will learn how to use API keys safely, make your first request to Claude, build a chatbot that remembers the conversation, give Claude different personalities, and ship the finished project to GitHub.

Each day builds on the last — by Friday you have a complete, polished app.

## Daily plan

| Day                | Title                                      | Goal                                                                           |
| ------------------ | ------------------------------------------ | ------------------------------------------------------------------------------ |
| [Day 1](./day1.md) | API Keys and Setup                         | Safely store an API key and verify your environment is ready.                  |
| [Day 2](./day2.md) | First API Call to Claude                   | Send a message to Claude from Python and print the reply.                      |
| [Day 3](./day3.md) | Build a Chatbot with Conversation History  | Keep a running history so Claude remembers earlier messages.                   |
| [Day 4](./day4.md) | System Prompts and Personas                | Give Claude a role and see how it changes every answer.                        |
| [Day 5](./day5.md) | Polish, Test, and Push to GitHub           | Add error handling, tidy the code, and publish the finished project.           |

## Suggested flow

1. Do the days in order — each one depends on what you built the day before.
2. Keep your project folder open in VS Code all week.
3. If the API call fails, check Day 1 first — 90 % of problems are a missing API key.
4. On Day 5, use the commit messages you learned in Week 2.

---

## Week 7 quick reference

### API terms

| Term              | What it means                                                                         |
| ----------------- | ------------------------------------------------------------------------------------- |
| **API**           | A way for your program to use someone else's service over the internet                |
| **API key**       | A secret password that proves your program is allowed to use the service              |
| **endpoint**      | The specific URL your program sends its request to                                    |
| **request**       | The message your program sends to the API                                             |
| **response**      | The answer the API sends back                                                         |
| **model**         | The AI brain you are talking to (e.g. `claude-opus-4-7`)                              |
| **max_tokens**    | The maximum length of Claude's reply (roughly 1 token ≈ 1 word)                      |
| **system prompt** | A hidden instruction that tells Claude what role to play                              |
| **message role**  | Either `"user"` (you) or `"assistant"` (Claude)                                       |
| **environment variable** | A value stored in your shell so code can read it without the value being in the code |

### Python snippets

**Install packages**

```bash
pip install anthropic python-dotenv
```

**Load your API key from a `.env` file**

```python
from dotenv import load_dotenv
load_dotenv()          # reads .env and adds values to the environment
```

**Create a client and send one message**

```python
import anthropic

client = anthropic.Anthropic()   # reads ANTHROPIC_API_KEY from the environment

message = client.messages.create(
    model="claude-opus-4-7",
    max_tokens=1024,
    messages=[{"role": "user", "content": "Hello!"}]
)

print(message.content[0].text)
```

**Add a system prompt**

```python
message = client.messages.create(
    model="claude-opus-4-7",
    max_tokens=1024,
    system="You are a friendly science teacher for 12-year-olds.",
    messages=[{"role": "user", "content": "What is gravity?"}]
)
```

**Keep conversation history**

```python
history = []

history.append({"role": "user", "content": user_input})

response = client.messages.create(
    model="claude-opus-4-7",
    max_tokens=1024,
    messages=history
)

reply = response.content[0].text
history.append({"role": "assistant", "content": reply})
```

**Handle errors gracefully**

```python
try:
    response = client.messages.create(...)
except anthropic.APIConnectionError:
    print("Could not connect — check your internet.")
except anthropic.AuthenticationError:
    print("Bad API key — check your .env file.")
except anthropic.RateLimitError:
    print("Too many requests — wait a moment and try again.")
```

---

_End of Week 7 — next up: Week 8 — Final project and demo day_
