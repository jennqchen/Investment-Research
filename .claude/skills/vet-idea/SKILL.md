---
name: vet-idea
description: Run a full, researched investment-style vetting of one business idea across market size, founder fit, competition, funding landscape, copycat moat and AI future-proofing, write a report, and add it to the scorecard dashboard. Use when the user asks to "vet [idea]", "score this idea", "is [idea] a good business", "research [idea]", or "deep dive on [idea]".
---

# Vet an idea

Act like a skeptical early-stage investor doing diligence for the founder.
The goal is a decision, not a cheerleading memo.

## Before researching
1. Read `profile/my-profile.md` and `framework/scoring-rubric.md`. Use the
   profile's custom weights if it lists them.
2. Restate the idea in one line: **customer + problem + solution + business model**.
   If any of the four is missing and you can't infer it sensibly, ask one
   short question. Otherwise state your assumption and go.

## Research (web search; aim for 12–20 searches total)
Work through each lens. Collect sources as you go.

1. **Market size**
   - Analyst/top-down figures (search "<category> market size <year>").
   - Build a bottom-up estimate: # of target buyers × price × purchases/yr. Show the math.
   - Growth rate and the "why now".
2. **Founder fit**: match idea requirements to profile skills, network, gaps. No search needed.
3. **Competition**
   - Direct competitors (names, funding, pricing, positioning).
   - Substitutes, including doing nothing and in-house.
   - Incumbents who could ship this as a feature.
   - Customer complaints about existing options (G2, Reddit, app reviews).
4. **Funding landscape**
   - Rounds in the last 24 months (company, amount, stage, lead investor, date).
   - Notable shutdowns or down rounds.
   - Capital needed to reach first revenue; can it bootstrap?
5. **Copycat moat**: check each moat type in the rubric; name which ones apply and how they'd be built.
6. **AI future-proofing**: answer Replace / Commoditize / Amplify with evidence
   (recent AI product launches in this space, what model providers are shipping).

If a CRM or company-data connector is available (Crunchbase, Clay, Attio),
use it for competitor and funding data and say so in the sources.

## Score
Score each lens 1–5 strictly against the rubric. Give a confidence (High /
Medium / Low) and a one-line reason. Compute the weighted total out of 100
and the verdict (Pursue / Explore / Pass). Flag any lens scored 1.

## Write the report
Save to `ideas/<idea-slug>.md` using `ideas/_template.md`. Keep it scannable:
the verdict and scorecard sit at the top, and the evidence goes below.

## Update the dashboard
Open `dashboard/index.html`. Between the lines `/* IDEAS:START */` and
`/* IDEAS:END */` is a JavaScript array. Add (or replace, matching on `id`)
one object:

```js
{
  id: "idea-slug",
  name: "Idea name",
  pitch: "One-line pitch",
  date: "YYYY-MM-DD",
  example: false,
  scores: { market: 4, fit: 5, competition: 3, funding: 3, moat: 3, ai: 4 },
  confidence: { market: "Medium", fit: "High", competition: "Medium", funding: "Low", moat: "Medium", ai: "Medium" },
  notes: { market: "...", fit: "...", competition: "...", funding: "...", moat: "...", ai: "..." },
  risk: "Biggest risk in one sentence",
  nextStep: "Cheapest test to run next",
  report: "ideas/idea-slug.md"
}
```

Remove the example entries (`example: true`) the first time a real idea is added.

## Reply to the user
Keep the chat reply short: verdict + score, the scorecard as a 6-row table,
the biggest risk, and the single cheapest next test (e.g. "5 discovery calls
with VPs of Sales in your network; here's who"). Point to the report file.
Then commit the report and dashboard change.
