---
name: ideate
description: Generate new business ideas tailored to the founder's profile, then give each a quick first-pass score. Use when the user asks to "brainstorm ideas", "give me business ideas", "ideate on [theme]", "what could I build in [industry]", or "find opportunities in [trend]".
---

# Ideate

Generate business ideas that fit **this** founder, not generic startup ideas.

## Inputs
1. Read `profile/my-profile.md`. If it is mostly empty, say so in one line and
   offer to run the profile interview (see `CLAUDE.md`), but still proceed
   using what is there.
2. Read `framework/scoring-rubric.md`.
3. Note any theme, industry, or constraint the user gave. If none, use the
   profile's industries and skills as the starting point.

## Process
1. **Spot the shifts.** Run 3–5 web searches for what is changing right now in
   the theme: new regulation, AI capability jumps, cost curves, buyer
   behaviour, recent funding clusters, companies that just failed. List 4–6
   shifts with a source each.
2. **Cross with the founder.** For each shift, ask: where does the founder's
   skill set, network or industry knowledge give them a head start? Use these
   idea patterns as prompts:
   - Productise the service (turn repeated advisory work into software or a fixed-price offer)
   - Picks and shovels (sell to the companies riding the shift)
   - Unbundle a bloated incumbent for one underserved segment
   - Trust layer (humans accountable for AI output in high-stakes decisions)
   - Network-as-product (marketplace, community, or curated access the founder already brokers)
   - Proprietary dataset that compounds with every customer
3. **Generate 8–10 candidates**, then cut to the best **5**. Drop anything that
   scores 1 on AI future-proofing or copycat moat at a glance.

## Output
For each of the 5 ideas, a compact card:

```
### <Idea name>
One-line pitch: <who it's for> + <what pain> + <how>
Why now: <the shift, with source link>
Why you: <specific profile item it leverages>
First customer: <a type of person in the founder's network>
Quick scores (gut-check, unresearched): Market _/5 · Fit _/5 · Competition _/5 · Funding _/5 · Moat _/5 · AI _/5 → ~__/100
Biggest risk: <one sentence>
```

End with a one-line recommendation of which 1–2 to run through full vetting,
and ask: "Want me to vet one of these?"

Save the full output to `ideas/brainstorm-<YYYY-MM-DD>-<theme-slug>.md`.
Do not add brainstorm ideas to the dashboard; only fully vetted ideas go there.
