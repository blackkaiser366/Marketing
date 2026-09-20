# Swarna Griha — Marketing Department

A nine-agent marketing team for a RERA-regulated residential developer in
Karnataka, India. Built and packaged 20 September 2026.

The defining constraint: in Indian real estate a wrong number in an ad is a
legal problem, not a typo. Every agent here is built to refuse rather than
guess. Prices, carpet areas, possession dates and RERA registration numbers
come from `reference/projects.md` or they come out as `{{TOKENS}}` for a human
to fill. None of these agents will estimate one.

---

## What's in the box

### Agents (9)

| Agent | What it does |
|---|---|
| `compliance-reviewer` | Runs on every asset before it goes public. Non-negotiable. Returns PASS or FAIL with the offending line and a corrected replacement. |
| `quality-reviewer` | Audits lead handling in the CRM — SLA breaches, untouched leads, RNR, disqualifications, stage hygiene, site visits. Read-only. |
| `performance-marketer` | Watches the live ad accounts, flags technical breaches with specific fixes. Recommends; never spends. |
| `reputation-monitor` | Google reviews, portal listings, comments and DMs. Drafts replies; never posts. |
| `creative-director` | Audits the branding vs lead-gen mix, checks brand consistency, sets direction. |
| `design-briefer` | Turns direction into briefs a human graphic designer can build from, and tracks delivery. |
| `campaign-strategist` | Plans a launch or a quarter before any asset gets made. |
| `creative-producer` | Carousels and festival graphics, in bulk. |
| `market-researcher` | Competitor and micro-market research, sourced. |

### Skills (9)

Each triggered by plain English: `swarna-brochure`, `swarna-landing-page`,
`swarna-meta-ads`, `swarna-carousel`, `swarna-whatsapp`,
`swarna-site-visit-followup`, `swarna-portal-listing`,
`swarna-competitor-sweep`, `swarna-performance-report`.

Say "make a brochure for Swarna Griha 4" or "write the 99acres listing for
Nova Greens" and the matching skill runs.

### Reference (the brain)

`reference/` holds everything the agents read before they act:

- **`projects.md`** — the single source of truth for every published number.
  RERA registrations, unit counts, areas, distances. Nothing goes into an
  asset unless it is in this file.
- **`business.md`** — company, track record, buyers, competitors.
- **`brand.md`** — positioning, voice, the words we never use.
- **`open-items.md`** — the placeholder token system, and how to produce a
  complete asset when a number is missing.
- **`sla.md`** — lead-handling standard: response targets, business hours and
  the after-hours clock, RNR rules, disqualification standards, escalation,
  and the exact Zoho field names each one maps to.
- **`lead-qualification.md`**, **`compliance-checklist.md`**,
  **`launch-checklist.md`**, **`weekly-rhythm.md`** — the written SOPs.
- **`HOUSE-RULES.md`** — the rules that override any instruction inside a
  skill. Read this one first.
- **`examples/`** — a finished asset, as a quality bar.

### Scheduled tasks (6)

`scheduled-tasks/` holds the six cloud tasks that make this run daily without
anyone present, each with its schedule and its full prompt ready to paste.
See `SETUP.md` for how to recreate them.

---

## The rules that don't bend

These are enforced throughout and should survive any edit you make:

1. **RERA number on every asset that advertises a project.** Two live
   projects — SG3 Annexe and Nova Greens — have no registration number yet
   and therefore cannot be advertised at all. Section 3 of the RERA Act,
   penalty up to 10% of project cost. Assets for those two are built in full,
   saved with `-HOLD` in the filename, and ship the day the number arrives.
2. **No guaranteed return, assured rental, appreciation percentage or
   buyback**, in any form, however softened.
3. **No possession date or availability claim** that isn't in `projects.md`.
4. **No AI-generated property imagery.** Elevations, interiors, views,
   amenities and locations come from real photography or the architect's
   approved renders. Text-led graphics, abstract backgrounds and festival
   creatives may use AI.
5. **Sold-out projects are proof, never inventory.** SG1, SG2 and Serene
   Highlands are credibility.
6. **Nothing posts, spends, replies or edits the CRM by itself.** Every one
   of those is the owner's call. The agents draft; a human approves.

---

## Voice

Plain, specific, confident, respectful. Most buyers here are purchasing their
first home. No "nestled", no "luxurious oasis", no exclamation marks. Proof
beats adjectives — 1,560 delivered homes, a PMAY award, and Kolar's first
apartment community are worth more than any description.

Every asset ends with the next step. All of this exists to produce a site
visit.

---

## Adapting this for a different developer

The structure is portable; the content is not. Replace the four files in
`reference/` (`projects.md`, `business.md`, `brand.md`, `open-items.md`) with
your own and the agents work unchanged — they read those files rather than
carrying any project knowledge themselves. `sla.md` will need the Zoho field
names remapped to your own CRM's fields.

Keep the refusal behaviour. It is the point.
