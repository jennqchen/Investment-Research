# Investment Research: how to run this repo

This repo is a business-idea research desk for a founder who does not code.
The user talks to Claude in plain English; Claude does the research, writes
the files, and keeps the dashboard current.

## Files
- `profile/my-profile.md`: the founder's background, skills, network, constraints, weights. Read before any ideation or scoring.
- `framework/scoring-rubric.md`: the six lenses, 1–5 scale definitions, weights, verdict bands. The single source of truth for scoring.
- `.claude/skills/ideate/`: brainstorm ideas that fit the profile.
- `.claude/skills/vet-idea/`: full researched diligence on one idea.
- `ideas/`: one report per vetted idea (`<slug>.md`) and brainstorm logs.
- `dashboard/index.html`: visual scorecard of all vetted ideas. Data lives between `/* IDEAS:START */` and `/* IDEAS:END */`.

## Profile interview
When the user says "interview me" / "set up my profile", ask the profile
questions **a few at a time** (3–4 per message, conversational), then write
answers into `profile/my-profile.md` and change its status line to
`_Status: filled in <date>._`. If Granola, Gmail or Drive are connected, offer
to pull context from them (e.g. past client work) and confirm before writing.

## Conventions
- Plain language. The user has never coded: no jargon about files, git or code in replies unless asked. Use analogies and tables.
- Every number is labelled Sourced / Estimated / Assumption.
- Be a skeptic. A "Pass" with clear reasons is a good outcome.
- Commit after each vetting or profile update with a short descriptive message.
