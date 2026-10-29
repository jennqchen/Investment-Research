# Investment Research: Idea Vetting Desk

A research desk that **comes up with** business ideas and **stress-tests**
them the way an investor would, tuned to your own background.

You run it by talking to Claude. No coding needed.

## The analogy

Think of it as an investment committee with six partners. Each one cares
about a single question and gives the idea a grade from 1 to 5:

```
            ┌──────────────────────────────┐
  Idea ───▶ │  1. Market size     "Big?"   │
            │  2. Founder fit     "You?"   │
            │  3. Competition     "Room?"  │──▶  Score /100  ──▶  Pursue / Explore / Pass
            │  4. Funding         "Money?" │
            │  5. Copycat moat    "Clone?" │
            │  6. AI-proofing     "Last?"  │
            └──────────────────────────────┘
```

Any partner can veto: a score of 1 on any lens raises a red flag, however
good the total looks.

## What to say to Claude

| You say | What happens |
|---------|-------------|
| "Interview me for my profile" | Claude asks about your background, skills, network and goals, and saves them. Do this first. |
| "Give me 5 ideas in B2B sales tooling" | Brainstorms ideas that fit *you*, with quick gut-check scores. |
| "Vet: a fractional CRO marketplace for Series A startups" | Full research: market sizing, competitor map, recent funding rounds, moat and AI analysis. Writes a report and adds it to the dashboard. |
| "Compare my top 3 ideas" | Side-by-side table with a recommendation. |
| "Re-score X assuming I bring on a technical co-founder" | Updates the scores under a new assumption. |
| "Change my weights: AI-proofing 25%, funding 5%" | Re-weights how ideas are ranked. |

## Where things live

| Folder | What's inside |
|--------|--------------|
| `profile/` | Your founder profile |
| `framework/` | The scoring rubric (what earns a 1 vs a 5 on each lens) |
| `ideas/` | One report per vetted idea |
| `dashboard/` | The visual scorecard |
