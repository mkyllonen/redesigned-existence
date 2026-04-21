---
name: weekly-compound
description: End-of-week ritual. Takes calendar, notes, and wins from the past seven days and surfaces what compounded, what leaked, three questions to sit with, and one bet for next week. Use on Fridays or whenever the user says "weekly review", "run my weekly compound", "what did I learn this week", or invokes "/weekly-compound".
user_invocable: true
---

# Weekly Compound

Not a journal. A pattern-recognition ritual across seven days. When run weekly, it builds a compounding read on what actually moves the needle versus what just feels busy.

## Input

Ask the user for any combination of:

- **Calendar** — meetings, time blocks, actual hours spent.
- **Notes** — scribbles, decisions, observations from the week.
- **Wins list** — anything that went right, however small.
- **Friction log** — anything that went wrong, dragged, or got stuck.
- **Prior weekly-compound file** (if it exists, at `weekly-compound/YYYY-MM-DD.md`).

Missing inputs are fine. Work with what they have. Note any gaps in your output.

## Output

Save to `weekly-compound/YYYY-MM-DD.md` where the date is this Friday (or today).

### 1. What compounded

Three bullet points. The work or decisions from this week whose effects will still be visible 90 days from now. Be specific — "made progress on X" is weak. "Decided Y, which removed Z friction" is strong.

### 2. What leaked

Three bullet points. Where time, energy, or focus drained without compounding. Name names: specific meetings, specific loops, specific avoidances. Do not moralize. Just observe.

### 3. Pattern match

Compare this week to the prior weekly-compound file if one exists. Call out:

- A pattern repeating from last week.
- A pattern finally breaking.
- Something new that wasn't there before.

If no prior file exists, say so and move on.

### 4. Three questions to sit with

Not tactical questions. Not "what should I do Monday." Questions that, if the user actually sat with them over the weekend, would change how they act next week. Examples of the right flavor:

- "Why did I say yes to [X] when I knew it drained from [Y]?"
- "What would I be doing if I believed [my own claim about Z]?"
- "Who am I protecting by staying vague on [topic]?"

Keep them sharp. Three is the cap.

### 5. One bet for next week

Exactly one thing the user is betting next week on. Not a to-do list. A bet — a claim about what will matter, and what they'll do because of it. Example:

> "I'm betting that shipping the draft before Thursday unblocks three downstream decisions. So I'm killing two meetings to make space for it."

Format: "I'm betting that [claim]. So I'm [action]."

### 6. One line to save

Pull or write the single line from this week's work that's worth keeping. Could be a user phrase, a reframe, a punchline. Save it at the top of the file for easy future grep.

## Archive behavior

The file at `weekly-compound/YYYY-MM-DD.md` is permanent. Never overwrite a prior week. Append patterns, don't erase them.

## Never

- Turn this into a gratitude journal.
- Pad when the week was genuinely thin. A three-line entry is fine.
- Tell the user what their bet "should" be. Surface patterns; let them name the bet.
- Skip the "one line to save" — future weeks will grep for these.
