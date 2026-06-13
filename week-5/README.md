# Week 5 — Python Projects: Data Structures & APIs

> **Who this is for:** Everyone continuing from Week 4.
> **OS:** Ubuntu Linux
> **Python:** Python 3
> **Time:** ~45–60 min per day, Monday to Friday
> **Goal by end of week:** You can store data in lists and dictionaries, read and write files, call a real API, and ship a working personal dashboard to GitHub.

---

## Overview

Week 5 is all about building real things. You already know the basics of Python — now you'll learn how to **organise data**, **save it to a file**, and even **pull live data from the internet**. By Friday you'll have a personal dashboard program you built yourself.

Each day builds on the last, so work through them in order.

## Daily plan

| Day                | Title                              | Goal                                                                          |
| ------------------ | ---------------------------------- | ----------------------------------------------------------------------------- |
| [Day 1](./day1.md) | Lists — Keeping Things in Order    | Create and use lists to store multiple values in one variable.                |
| [Day 2](./day2.md) | Dictionaries — Look Things Up Fast | Use dictionaries to pair names with values, like a digital contact book.      |
| [Day 3](./day3.md) | Files — Save Data That Sticks      | Read from and write to text files so data survives when the program closes.   |
| [Day 4](./day4.md) | pip and APIs — Reach the Internet  | Install a library with pip and call a real public API to fetch live data.     |
| [Day 5](./day5.md) | Mini Project — Personal Dashboard  | Combine lists, files, and APIs into one program, then commit it to GitHub.   |

## Suggested flow

1. Do [Day 1](./day1.md) and [Day 2](./day2.md) first — they teach the data structures used every day after.
2. [Day 3](./day3.md) upgrades the Day 1 to-do list so it saves to disk. Keep that file handy.
3. [Day 4](./day4.md) teaches the API skill you need for the Friday project.
4. [Day 5](./day5.md) is project day — bring all your files together and commit everything.

---

## Week 5 quick reference

| Concept                        | Example                                      | What it does                          |
| ------------------------------ | -------------------------------------------- | ------------------------------------- |
| Create a list                  | `fruits = ["apple", "banana"]`               | Store multiple values in order        |
| Get item by index              | `fruits[0]`                                  | Returns `"apple"` (index starts at 0) |
| Add to a list                  | `fruits.append("mango")`                     | Adds item to the end                  |
| Remove from a list             | `fruits.remove("banana")`                    | Removes first match                   |
| Length of a list               | `len(fruits)`                                | Returns number of items               |
| Loop a list                    | `for f in fruits:`                           | Visit each item one by one            |
| Create a dictionary            | `pet = {"name": "Rex", "age": 3}`            | Store key–value pairs                 |
| Get a value by key             | `pet["name"]`                                | Returns `"Rex"`                       |
| Add a key                      | `pet["colour"] = "brown"`                    | Adds new key–value pair               |
| Loop a dictionary              | `for k, v in pet.items():`                   | Visit each key and value              |
| Open a file for reading        | `with open("data.txt") as f:`                | Safely opens a file                   |
| Write to a file                | `with open("data.txt", "w") as f:`           | Creates or overwrites file            |
| Append to a file               | `with open("data.txt", "a") as f:`           | Adds to end of file                   |
| Install a library              | `pip install requests`                       | Downloads a package from the internet |
| Import a library               | `import requests`                            | Makes the library available in code   |
| Call an API                    | `r = requests.get("https://...")`            | Fetches data from a web address       |
| Parse JSON                     | `data = r.json()`                            | Turns the response into a dictionary  |

---

_End of Week 5 — next up: Week 6 — AI concepts, prompting, and ethics_
