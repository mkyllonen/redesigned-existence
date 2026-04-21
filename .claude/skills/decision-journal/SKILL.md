---
name: decision-journal
description: Log a structured decision with reasoning, alternatives rejected, and success criteria. Stored for later query. Use when the user says "log this decision", "record what I decided", "journal this choice", or invokes "/decision-journal". Also runs in query mode to answer "what did I decide about X?"
user_invocable: true
---

# Decision Journal

Most journaling is prose. This skill enforces schema — turning decisions into structured records an AI can reason across later. Ten entries in, Claude can spot patterns the user can't see alone.

## Two modes

The skill runs in one of two modes. Detect based on user intent.

- **Log mode** — user wants to record a new decision.
- **Query mode** — user wants to retrieve or analyze past decisions.

If ambiguous, ask which.

## Log mode

Ask the user in this order. Do not skip steps. Accept short answers, but do not let them skip a field.

1. **Decision (one sentence).** What did you decide?
2. **Date.** Default to today if unstated.
3. **Why.** What's the core reason? (Not a list of factors — the one that tipped it.)
4. **Constraints.** What are you optimizing against? (Time, money, energy, scope, reputation, other.)
5. **Alternatives rejected.** Name at least two options you considered and rejected. One sentence each on why.
6. **Evidence.** What data, conversation, or experience informed this? (Can be thin — "gut" counts, but label it as gut.)
7. **Assumptions.** What has to be true for this decision to be right? Minimum two. These are the fragile bits.
8. **Success criteria.** How will you know this decision was right? Be specific and observable.
9. **Review date.** When will you come back and check? Default to 30 days from today.
10. **Confidence (1-10).** How sure are you right now?
11. **Tags.** One to three short tags for grep later (`pricing`, `hiring`, `product`, `scope`, etc.).

Save as `decisions/YYYY-MM-DD-[short-slug].md` using this exact format:

```yaml
---
date: YYYY-MM-DD
decision: [one sentence]
confidence: [1-10]
review_date: YYYY-MM-DD
tags: [tag1, tag2]
status: open
---

## Why
[answer]

## Constraints
[answer]

## Alternatives rejected
- [option 1]: [why rejected]
- [option 2]: [why rejected]

## Evidence
[answer]

## Assumptions
- [assumption 1]
- [assumption 2]

## Success criteria
[answer]
```

After saving, confirm to the user: path, review date, tags.

## Query mode

When the user asks "what did I decide about X" or "review my decisions on Y":

1. Scan `decisions/*.md` files.
2. Filter by tag, decision text, or content match.
3. Return a table: date, decision, confidence, status.
4. If the user asks for analysis, run across matching entries and surface:
   - Patterns in assumptions that repeatedly turn out wrong.
   - Decisions whose review date has passed but status is still `open`.
   - Contradictions between past decisions and current stated direction.
   - Average confidence for decisions that later got reversed (if status tracking is in use).

## Review mode (bonus)

When the user says "review this decision" and names one:

1. Load the file.
2. Ask: "Did this turn out right? (yes / no / partial / too early)"
3. Update frontmatter: `status: reviewed`, `outcome: [their answer]`, add a `reviewed_date`.
4. Append a new section at the bottom: `## Outcome` with their notes on what happened, what they missed, what assumption was wrong.

## Never

- Let the user skip "alternatives rejected." If they only considered one option, say so explicitly in the entry.
- Treat confidence of 10 as credible without probing — it's almost always false certainty.
- Modify an old decision's original fields. Only append to `## Outcome`.
- Surface decisions across unrelated projects — respect the current folder's scope.
