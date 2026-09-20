---
name: swarna-whatsapp
description: Writes Swarna Griha WhatsApp messages — the instant first reply to a new lead, qualification questions, broadcasts to past enquiries, launch and price-revision announcements, and re-engagement messages for cold leads, in English and local languages. Use this skill whenever the user mentions WhatsApp, broadcasts, "what do I message the lead", first response, follow-up message, reviving old leads, or announcing something to a buyer list.
---

# Swarna Griha WhatsApp

## The principle

A WhatsApp message has one job: book the site visit. It is not a brochure.
Information given on WhatsApp removes the reason to visit. Give enough to
qualify and intrigue, then ask for the visit.

Speed beats polish. The first reply should go out within five minutes — in
real estate, whoever replies first usually wins the deal.

## Before writing

Read `${CLAUDE_PLUGIN_ROOT}/reference/business.md` (buyer, objections) and
`${CLAUDE_PLUGIN_ROOT}/reference/projects.md` (the only source for any number you state).
Ask which project, which stage of the funnel, and which language.

## The message types

**1. Instant first reply (new lead)** — under 45 words. Their name, the project
they enquired about, one concrete fact, one qualifying question, one offer of a
visit slot. No price list.

**2. Qualification follow-up** — three questions maximum, asked one at a time
across messages, not as a form: budget comfort, timeline, loan or self-funded.

**3. Site visit confirmation** — date, time, exact map pin, what to expect, who
they'll meet, one line on what to look for. Sent the evening before.

**4. Broadcast — launch or new inventory** — under 60 words. One reason it
matters to them, one number, one CTA. Only to people who enquired.

**5. Re-engagement — cold leads** — a genuine reason to reopen: construction
milestone, price revision, a configuration that just opened up. Never "just
following up".

**6. Post-visit follow-up** — reference something specific from their visit,
handle the objection they actually raised, one clear next step with a date.

## Rules

- Short lines, no walls of text, at most one emoji, never in a price line.
- Any message quoting a price carries the RERA number and states inclusions.
- No guaranteed return, rental or appreciation claims — a casual WhatsApp line
  is held to the same standard as a printed ad.
- Never broadcast to a list that didn't opt in.
- Machine-translated price or legal lines get flagged for human review.

## Output

Save to `output/whatsapp/<project-or-purpose>-<YYYY-MM-DD>.md`, each message
copy-paste ready, with a one-line note on when to send it.
