---
name: swarna-site-visit-followup
description: Builds the Swarna Griha sales follow-up system — call scripts and openers, objection handling for price, location and possession pushback, a dated post-site-visit sequence, negotiation one-pagers, and lead qualification questions. Use this skill whenever the user asks what to say to a buyer, how to handle "you are too expensive" or "the project next door is cheaper", why leads go cold, what to send after a site visit, scripts for the sales team, or anything about converting enquiries into bookings.
---

# Swarna Griha Site Visit and Follow-up

## Before writing

Read `${CLAUDE_PLUGIN_ROOT}/reference/business.md` — the objections list and the "why buyers say
yes" list are the raw material. Read `${CLAUDE_PLUGIN_ROOT}/reference/projects.md` for numbers
and the project's honest weaknesses. Read `${CLAUDE_PLUGIN_ROOT}/reference/lead-qualification.md`.

Ask which project, and whether this is a walk-in, a paid lead, a referral or a
channel partner lead — they behave differently.

## What to produce

**Qualification questions** — five, in order, each with what a good and a bad
answer sound like: budget comfort, timeline, funding, decision makers, what
else they're seeing.

**The site visit itself** — what to show first, what to say at each point,
which question to ask while they're standing in the unit, and the one thing to
leave unsaid so there's a reason for a second visit.

**The follow-up sequence** — dated, not vague. Day 0 evening, day 2, day 5,
day 10, day 21. Each touch carries a new reason to talk: a photo, a document,
a milestone, an inventory change. Never "just checking in".

**Objection handling** — for each real objection in `business.md`: what they're
actually worried about underneath it, the response, the proof to show, and the
question that moves it forward. Never write a rebuttal that denies a true
weakness — acknowledge it, then reframe against what we genuinely do better.

**Negotiation one-pager** — what we can flex (payment schedule, floor rise,
parking, registration timing) and what we don't, with the order to give things
away in. Never invent a discount authority the owner hasn't given.

## Rules

- No false deadlines or invented scarcity. Real inventory numbers only.
- No return, rental or appreciation promises, including verbally on a call.
- Scripts are a spine, not a recital — write them so a salesperson still
  sounds like themselves.

## Output

Save to `output/site-visit-followups/<project>-followup-<YYYY-MM-DD>.md`,
formatted so it can be printed and handed to the sales team.
