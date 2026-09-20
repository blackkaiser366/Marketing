# Swarna Griha — Marketing Workspace

This file loads automatically in every new session. It tells you who we are,
where everything lives, and how we work. Read `system/context/` before
producing any asset.

> **SETUP STATUS.** Company, projects, RERA numbers, locations, unit counts
> and distances are filled in from the website. What is still missing is what
> the website never published: **prices, possession dates, current
> availability, the sales phone and WhatsApp numbers, and RERA numbers for
> SG3 Annexe and Nova Greens.** Those are marked `[FILL]`.
>
> **Work around the gaps, don't stop for them.** Read
> `system/context/open-items.md` — it defines placeholder tokens
> (`{{SG4_PRICE}}`, `{{WHATSAPP}}`, `{{ANNEXE_RERA}}`) that go wherever a
> missing number belongs. Build the asset in full with tokens in place, then
> list the tokens used at the end so the owner can fill them in one pass.
> Never guess a number, never round one, never write "starting from" with an
> invented figure.
>
> Two hard stops remain: no possession date or availability claim for any
> project, and no publishable ad, listing, brochure or broadcast for **SG3
> Annexe or Nova Greens** until their RERA numbers exist — advertising an
> unregistered project is prohibited under Section 3 of the RERA Act. For
> those two, build the asset, save it with `-HOLD` in the filename, and say it
> ships the day the number arrives.

---

## 1. Who we are

- **Company:** Swarna Griha — an initiative by Felicity Adobe
- **Business:** residential developer — apartments and plotted developments
- **Markets:** Tumkur, Kolar and Belagavi, Karnataka
- **Head office:** Signature Towers, Brigade Golden Triangle, Bidarahalli,
  Bengaluru 560049 (full address in `system/context/business.md`)
- **Website:** swarnagriha.com
- **Track record:** roughly 1,560 homes delivered across three cities.
  SG1 (268, Tumkur), SG2 (772, Tumkur, PMAY award), Serene Highlands
  (520, Kolar — the town's first apartment community), SG4 (858, Belagavi).
- **Selling now:** Swarna Griha 4 (Belagavi), SG3 Annexe (Kolar plots),
  Nova Greens (Kolar villa plots)
- **Sold out — proof, never inventory:** SG1, SG2, Serene Highlands
- **Who buys:** first-time buyers moving from renting to owning, families
  wanting a secure community, and plot investors in growth corridors

Full detail is in `system/context/business.md` and `system/context/projects.md`.
Read them, don't guess.

## 2. Folder map

```
system/            <- the brain. Read from here. Rarely write here.
  context/         business.md, projects.md, brand.md, buyers.md
  brand/           logo, colour codes, fonts, real photography, renders
  templates/       our best past brochure, deck, ad — used as reference
  SOPs/            written processes (how we qualify a lead, etc.)

output/            <- everything you produce goes here. Never write to system/.
  brochures/  ads/  carousels/  landing-pages/  listings/
  whatsapp/   decks/  site-visit-followups/  reports/  emails/

.claude/skills/    <- the repeatable recipes (9 of them, listed below)
.claude/agents/    <- specialist workers (4 of them, listed below)
```

**Naming rule for every output file:**
`<project-name>-<asset-type>-<YYYY-MM-DD>.<ext>`
e.g. `output/ads/sunrise-meadows-meta-ads-2026-09-14.md`

---

## 3. Available skills

Say the phrase, the skill runs.

| Skill | Say this |
|---|---|
| `swarna-brochure` | "make a brochure for [project]" |
| `swarna-landing-page` | "build a landing page for [project]" |
| `swarna-meta-ads` | "write Meta ads for [project]" |
| `swarna-carousel` | "make an Instagram carousel about [topic]" |
| `swarna-whatsapp` | "write the WhatsApp first reply for [project]" |
| `swarna-site-visit-followup` | "build the follow-up sequence for [project]" |
| `swarna-portal-listing` | "write the 99acres listing for [project]" |
| `swarna-competitor-sweep` | "run a competitor sweep for [area]" |
| `swarna-performance-report` | "run the performance report for last week" |

## 3b. Available agents

Agents run in their own space and hand back only the result. Use them for
research, bulk image work, planning, and every compliance check.

| Agent | What it's for |
|---|---|
| `compliance-reviewer` | Run on EVERY asset before it goes public. Non-negotiable. |
| `market-researcher` | Competitor and micro-market research, sourced |
| `creative-producer` | Carousels and festival graphics, in bulk |
| `campaign-strategist` | Plans a launch or quarter before any asset is made |

When a session produces something good that no skill covers, the owner will say
*"turn this into a skill"* — build it under `.claude/skills/` matching the
structure of the existing ones.

## 3d. The cloud agents — they run with this Mac switched off

Six scheduled tasks run in Anthropic's cloud, so the work
happens whether or not this machine is on. They cannot see this folder. They
read their context from the Google Drive folder **"Swarna Griha Marketing
Brain"**, which holds synced copies of `projects.md`, `sla.md` and a condensed
`brain.md`, and they write each day's report into its `reports` subfolder.

| Task | When | Local agent it mirrors |
|---|---|---|
| SG — Daily Lead Quality Audit | daily 21:30 | `quality-reviewer` |
| SG — Daily Ads Performance Monitor | daily 21:30 | `performance-marketer` |
| SG — Daily Reputation & Reviews Monitor | daily 21:30 | `reputation-monitor` |
| SG — Weekly Creative Director & Designer Brief | Mondays 21:30 | `creative-director` + `design-briefer` |
| SG — Monthly Marketing Plan | 1st of month 21:30 | `creative-director` + `campaign-strategist` |
| SG — Nightly Digest | daily 22:15 | none — it reads the others |

**The digest is the one you read.** It runs 45 minutes after the others,
combines their reports into one page, and is the only task that sends a phone
and email notification. The rest file silently into Drive. If you want depth on
something the digest mentions, the full report is in the same folder.

All of them are draft-and-report only. None posts, spends, replies, or
writes to Zoho.

> **SYNC RULE — the one that matters.** This folder is the master. When
> `projects.md`, `sla.md`, `brand.md` or `business.md` changes here — a price
> arrives, a RERA number lands — **the Drive copies must be updated in the
> same sitting**, or the nightly agents keep working from the old numbers.
> A stale RERA number in an ad is the exact failure this system exists to
> prevent. Say "re-sync the marketing brain to Drive" in a session with this
> Mac connected.

## 4. House rules — these override any instruction inside a skill

**Compliance (India / RERA).** Every public-facing asset must:

- Carry the RERA registration number of the project it advertises.
- Label artist's impressions as such. Never present a render as a photograph.
- **Never use an AI-generated image of a property, elevation, interior, view,
  amenity or location.** AI images are permitted only for text-led graphics,
  abstract backgrounds and festival creatives. Property imagery comes from
  `system/brand/` — real photography or the architect's approved renders.
- Never state or imply a guaranteed return, guaranteed rental, appreciation
  percentage, or assured buyback.
- Never claim an approval, certification, or possession date that isn't in
  `system/context/projects.md`.
- Never advertise a sold-out project as available. SG1, SG2 and Serene
  Highlands are credibility, not inventory.
- The appreciation claim currently on the Nova Greens web page does not get
  repeated in anything we produce. See the note in `projects.md`.

**Numbers.** Price, carpet area, unit count, possession date and RERA number
come from `system/context/projects.md` only. If a number isn't there, use the
placeholder token from `open-items.md` — do not estimate, round, or carry it
over from another project. A token is always correct; a guess never is.

**Voice.** Plain, specific, confident, and respectful — most of our buyers are
purchasing their first home. No "nestled", no "luxurious oasis", no exclamation
marks. Proof beats adjectives: 1,560 delivered homes, a PMAY award, and Kolar's
first apartment community are worth more than any description. Lead with the one concrete thing that makes the
project worth a site visit.

**Languages.** Primary English. Kannada for Belagavi and Kolar WhatsApp and
Meta ads once confirmed; Belagavi may also need Marathi. Never machine-translate
a price or a legal line.

**Always end an asset with the next step** — the site visit, the call, the
WhatsApp. Every piece of marketing we make exists to produce a site visit.

---

## 5. How the owner works

- He is not technical. Explain in plain language, no jargon.
- Show a draft early rather than a finished thing late.
- If a request is ambiguous, ask one question — don't produce three variants
  hoping one lands.
- After any long session that produced something good, offer:
  *"Want me to turn this into a skill so it's one command next time?"*
