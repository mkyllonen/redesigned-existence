---
name: offer-stress-test
description: Red-team any offer, pitch, or sales email. Output the seven most likely reasons a prospect says no, plus one counter-move per objection. Use when the user says "stress test this offer", "why would someone say no", "red team my pitch", or invokes "/offer-stress-test".
user_invocable: true
---

# Offer Stress Test

Most writers never hear their own offer red-teamed. This skill fixes that. Paste an offer, get the seven objections most likely to kill the sale — ranked by probability — plus a counter-move per objection.

## Input

Ask the user for:

1. The **offer itself** — pitch, email, sales page copy, or verbal summary.
2. The **target buyer** — one sentence describing who this is for.
3. Optional: **price** and **format** (one-time, recurring, DFY, DIY, cohort, etc.).

If any are missing, proceed with assumptions but mark them as assumptions.

## Output

### Seven objections, ranked

For each of the seven objections, output:

**Objection [N] — [short name]**

- **The inner monologue.** Write the exact words the prospect thinks when they read the offer. First person, unedited. One to three sentences.
- **Why this kills the sale.** What specifically in the offer triggered this. Quote the phrase if you can.
- **Counter-move.** One specific change to the offer copy, price, format, or framing that neutralizes this objection. Be concrete — rewrite the line if needed.

Rank the seven by probability: highest-risk first. Do not pad. If there are really only four serious objections, say so and stop at four.

### Common objection categories to scan for

Scan the offer against these categories. Skip any that don't apply.

1. **Belief** — they don't believe it works.
2. **Belief in self** — they believe it works for others, not for them.
3. **Price** — not "too expensive" — specifically "too expensive relative to the risk."
4. **Timing** — wrong moment in their life or business.
5. **Trust** — don't know who the seller is, or have a reason to doubt.
6. **Effort** — hidden work they don't want to do.
7. **Alternatives** — something cheaper or free solves enough of the problem.
8. **Identity** — buying this would mean admitting something they're not ready to admit.
9. **Social risk** — how it looks to their peers, spouse, boss.
10. **Post-purchase regret** — fear of buyer's remorse specifically.

### Hidden weakness

After the seven, identify **the single biggest structural weakness** in the offer — the thing that, if fixed, would move the needle more than any tactical rewrite. One paragraph. Blunt.

### Verdict

One of three:

- **Ship it.** Minor tweaks only.
- **Fix the top three first.** These specific objections are sale-killers.
- **Rebuild.** The offer's foundation is wrong, not the copy.

## Never

- Be polite about weak offers.
- Offer ten equal-weight objections when three are dominant.
- Suggest the user "add more value" without specifying what and why.
- Refuse to give a verdict.
