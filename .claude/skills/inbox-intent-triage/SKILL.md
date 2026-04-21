---
name: inbox-intent-triage
description: Sort emails by whether they advance the user's stated goals — not by time, sender, or label. Use when the user says "triage my inbox", "sort by importance", "what should I respond to", or invokes "/inbox-intent-triage".
user_invocable: true
---

# Inbox Intent Triage

Standard email tools sort by time, sender, or unread status. This skill sorts by **strategy**: does this email advance the user's goals, drain from them, or neither?

## Setup (one-time)

If the user hasn't defined their goals yet, ask for:

- **Three current goals** (the real ones — what success looks like in the next 90 days).
- **One anti-goal** (the thing they want to protect against — burnout, scope creep, distractions, a specific trap).

Save these to `triage-goals.md` in the current folder. On future runs, offer to reuse or update.

## Input

Ask the user to paste or attach:

- A list of email subject lines + sender + short preview (50-100 words each is plenty).
- Or a full email dump if they have it.

Work with whatever they give you. Don't demand a specific format.

## Triage output

Sort every email into one of four buckets. Inside each bucket, rank by impact.

### Advances goals — respond today

Emails that directly move one of the three goals forward. For each:

- Sender + subject.
- Which goal it advances.
- Recommended action in one sentence (reply, schedule, delegate, decide).
- Suggested response opening line (ready to paste).

### Drains from goals — delete, delegate, or decline

Emails that pull toward the anti-goal or steal attention from goals. For each:

- Sender + subject.
- Why it drains.
- One of three actions: `archive`, `decline template`, `delegate to [role]`.
- If `decline template`: provide a one-line reply the user can send immediately.

### Unclear — 10-second triage questions

Emails where you can't tell. For each, offer a single yes/no question the user can answer to decide. Do not ask more than one question per email.

### Noise — batch archive

Newsletters, notifications, receipts, marketing. Just count them and recommend batch archive. Don't list individually.

## Rule

Do not suggest the user spend more than 30 minutes clearing this triage. If the load is bigger than that, cut the lowest-impact items from the "advances goals" bucket and move them to tomorrow.

## Never

- Sort by sender prestige or deadline pressure alone.
- Recommend responding to everything.
- Treat "inbox zero" as the goal. Goal alignment is the goal.
- Store goals or email content outside the user's current folder.
