---
name: swarna-meta-ads
description: Writes a complete Meta (Facebook and Instagram) ad set for a Swarna Griha project — five angle-based copy variants with primary text, headline, description and CTA, plus targeting notes, creative direction and the WhatsApp reply that catches the lead. Use this skill whenever the user asks for Facebook ads, Instagram ads, Meta ads, ad copy, campaign copy, lead-gen ads, boosted post copy, or says something like "we need to run ads for [project]" or "the ads aren't getting leads, rewrite them" — even if they don't name the platform.
---

# Swarna Griha Meta Ads

## Before writing anything

1. Read `${CLAUDE_PLUGIN_ROOT}/reference/projects.md` for the project. **No RERA number, no
   ads.** Stop and ask.
2. Read `${CLAUDE_PLUGIN_ROOT}/reference/business.md` — specifically the buyer profile and the
   real objections list. The objections are where the good angles come from.
3. Read `${CLAUDE_PLUGIN_ROOT}/reference/brand.md` for voice and language.
4. Check `system/templates/` for past ads that performed well. Match what
   worked; don't reinvent.

Ask before starting:
- Objective — lead form, WhatsApp, calls, or traffic to a landing page?
- Budget and duration, roughly?
- Any offer running, or is this plain project promotion?

## Produce five variants, one per angle

Not five rewrites of the same idea. Five genuinely different reasons to click.

| # | Angle | What it leads with |
|---|---|---|
| 1 | **Location** | The commute. The exact distance to where this buyer works. |
| 2 | **Price clarity** | The number, stated plainly, with what's included. Most competitors hide it — we won't. |
| 3 | **Scarcity (only if true)** | Real remaining inventory from `projects.md`. Never invent urgency. |
| 4 | **Objection reversal** | Take the #1 objection from `business.md` and answer it in the ad. |
| 5 | **Possession / progress** | Construction stage and RERA possession date. Aimed at buyers burned by delays. |

For each variant write:

- **Primary text** — 2 versions: one short (under 125 characters, for mobile
  feed where the rest gets truncated), one long (up to ~600 characters, for
  a considered buyer who expands it).
- **Headline** — under 40 characters.
- **Description** — under 30 characters.
- **CTA button** — the exact Meta button name (e.g. `WHATSAPP_MESSAGE`,
  `LEARN_MORE`, `BOOK_NOW`).
- **Creative direction** — what image or video to pair it with, drawn from
  what's actually in `system/brand/<project>/`. Never generate property
  imagery; if the right shot doesn't exist, say which photo needs taking.
- **Why this should work** — one line tying the angle to the buyer profile.

Then add, once for the whole set:

- **Targeting notes** — geography, age band, interests and behaviours worth
  testing, and what to exclude. Note that Meta restricts detailed targeting
  for housing ads in some markets; flag anything that may be limited.
- **The WhatsApp first reply** — the message that goes out the second a lead
  lands. Written to book a site visit, not to dump information. This is where
  most real estate ad spend dies.
- **What to watch** — which two numbers tell us in 72 hours whether this is
  working.

## Compliance — overrides everything above

- RERA number in the primary text of every ad, not just the landing page.
- No guaranteed returns, assured rent, appreciation percentage or buyback.
- No AI-generated property imagery. Real photos or approved renders only,
  renders labelled as artist's impression.
- No claim about approvals, schools, metro lines or infrastructure that isn't
  confirmed in `projects.md`. "Proposed metro station" is not "metro station".
- Prices must state inclusions.

## Output

Save to `output/ads/<project>-meta-ads-<YYYY-MM-DD>.md`, formatted so the copy
can be pasted straight into Ads Manager field by field. Then summarise in chat:
which angle you'd run first and why, and what creative is missing.
