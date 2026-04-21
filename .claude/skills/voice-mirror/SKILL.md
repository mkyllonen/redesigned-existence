---
name: voice-mirror
description: Capture the user's writing voice from samples, then apply it to future outputs. Use when the user says "capture my voice", "write like me", "match my tone", "sound more like me", or invokes "/voice-mirror".
user_invocable: true
---

# Voice Mirror

Most AI writing sounds like everyone else. This skill fixes that by learning the delta between the user's writing and generic AI output — then applying it to anything they create.

## Phase 1: Build the profile

Ask the user for **5 writing samples**, each roughly 200-500 words. Prefer variety: an email, a social post, something they wrote angry, something personal, something professional.

If they can only give fewer, work with what they have but flag that fewer samples = shallower profile.

Read all samples. Extract and save these eight dimensions to `voice-profile.md` in the current folder:

1. **Cadence** — average sentence length, variation, rhythm patterns.
2. **Vocabulary tier** — reading grade level, domain jargon, signature words used more than average writers.
3. **Hedging pattern** — frequency and form ("maybe," "I think," softeners, disclaimers, or the absence thereof).
4. **Opening moves** — how they start a piece (statement, question, story, contrarian claim, setup-punchline).
5. **Closing moves** — how they end (summary, cliffhanger, CTA, question, silence).
6. **Forbidden patterns** — what they never do that generic AI loves (em dashes, "furthermore," hollow three-item lists, "it's important to note," corporate-speak).
7. **Signature moves** — quirks that make it them (specific metaphors, recurring themes, punctuation habits, typography).
8. **Tone range** — tones they can hit (playful, cutting, warm, blunt) and which are absent.

Show the profile to the user. Ask: "Does this feel accurate? What's missing or wrong?" Revise until they confirm.

Save the final version as `voice-profile.md`.

## Phase 2: Apply the profile

When the user asks for voice-matched output:

1. Load `voice-profile.md`. If not found, ask the user where it lives or offer to run Phase 1.
2. Draft the response normally, in your head.
3. Run a rewrite pass that applies each profile dimension:
   - Shift sentence rhythm to match their cadence.
   - Swap vocabulary toward their tier and signature words.
   - Match their hedging frequency.
   - Open and close with their moves.
   - Strip forbidden patterns ruthlessly.
   - Insert signature moves only if they fit naturally — never force.
4. Deliver the voice-matched version. Don't narrate what you did.

## Phase 3: Check mode

When the user says "check this in my voice" or pastes a draft asking "does this sound like me?":

Run the draft against the profile. Return:

- A score 0-100 for each of the eight dimensions.
- The top 3 lines that don't match, each with a proposed rewrite.
- The top 3 lines that are peak them.

Honesty mode: if the draft is mostly not them, say so plainly. Do not soften.

## Never

- Flatten voice toward "professional."
- Reintroduce forbidden patterns to sound polished.
- Lecture about writing craft.
- Ask for more samples when the user has already given clear direction.
- Store the profile outside the user's folder or reference it across unrelated projects.
