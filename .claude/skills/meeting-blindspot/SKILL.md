---
name: meeting-blindspot
description: Process a meeting transcript or notes and surface what was decided, what was committed, and where the user failed to push back. Not a summary tool. Use when the user says "debrief this meeting", "what did I miss", "where should I have pushed back", or invokes "/meeting-blindspot".
user_invocable: true
---

# Meeting Blindspot

Every tool summarizes meetings. This one acts as a post-meeting mirror, showing the user what they missed in real time — especially the places they should have pushed back but didn't.

## Input

Ask the user for:

1. The **transcript or notes** (paste, file path, or dictated recap).
2. The **user's role** in the meeting (who they are, what they wanted from it).
3. Optional: **desired outcome** going in (if they stated one).

If notes are thin, work with what they have but flag confidence level.

## Output structure

Return the following, each section clearly labeled.

### 1. Decisions made

Only decisions that were actually made. Not discussions, not "we should." Each line: who decided, what was decided, when it takes effect.

### 2. Commitments

Two sub-lists:

- **Yours.** What the user explicitly or implicitly agreed to do.
- **Theirs.** What the other party or parties agreed to do. Include the person's name.

Include dates if mentioned. Flag undated commitments as "no deadline stated — risk."

### 3. Open loops

Anything raised but not resolved. One line each, labeled as:

- **Needs decision** (someone has to call it)
- **Needs info** (blocked on data)
- **Dropped** (raised and forgotten)

### 4. Blindspots — where you should have pushed back

This is the skill's core. Scan the transcript for three specific moments where the user:

- Agreed too quickly to something that costs them.
- Let a vague commitment from the other party slide.
- Accepted a framing that wasn't in their interest.
- Stayed quiet when they had a strong counterpoint.
- Moved on from a question that wasn't actually answered.

For each, cite the verbatim line (or near-verbatim). State what a sharper version of the user would have said. Keep it to three moments — rank by impact.

### 5. Follow-up draft

One or two sentences the user should send within 24 hours to close the biggest risk surfaced in section 4. Ready to paste.

## Honesty rule

If the user did well, say so in one line and move on. Don't manufacture blindspots. Don't inflate the pushback list to feel useful. If the meeting was clean, say: "No significant blindspots. Move forward."

## Never

- Summarize for the sake of summary. Every section must be actionable.
- Name-and-shame the other party. Focus on the user's actions.
- Offer generic advice ("you should be more assertive"). Only specific, moment-level suggestions.
- Skip section 5 — the follow-up draft is where value lands.
