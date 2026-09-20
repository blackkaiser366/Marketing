---
name: swarna-competitor-sweep
description: Runs a competitor and micro-market sweep for Swarna Griha — new launches nearby, competitor pricing and offers, what they are advertising, portal listing counts, and local infrastructure or RERA news that moves buyer sentiment, ending in what we should change this month. Use this skill whenever the user asks about competitors, what others are charging, new launches in the area, market conditions, "why are we losing deals to X", or wants a market update.
---

# Swarna Griha Competitor Sweep

## Before starting

Read `${CLAUDE_PLUGIN_ROOT}/reference/business.md` for our micro-markets and the named
competitors, and `${CLAUDE_PLUGIN_ROOT}/reference/projects.md` for our own current pricing —
you cannot judge a competitor's price without ours in front of you.

Ask which micro-market, unless the owner names one.

## What to gather

1. **New and upcoming launches** in our micro-markets — developer, project,
   configurations, quoted price per sq ft, possession date, RERA number.
2. **Named competitors** from `business.md` — current quoted price, any offer
   running, inventory movement, construction stage.
3. **What they're advertising** — check the Meta Ad Library for their page and
   note the angles they lead with, how long ads have been running (long-running
   ads are usually working ones), and what they promise.
4. **Portal presence** — roughly how many listings they hold on the major
   portals for our configurations, and how their pricing is presented.
5. **Sentiment movers** — metro or road announcements, RERA actions, delivery
   delays or handover news, anything a buyer would have read this month.

Cite a source for every price and date. Portal-quoted prices are asking prices,
not transacted ones — label them as such.

## What to conclude

Not a data dump. End with four short sections:

- **Where we're priced** — us versus each competitor on a comparable basis.
- **What they're saying that we're not** — the angles we're leaving on the table.
- **What changed this month** that actually matters.
- **Three actions** for us, ranked, each with the reason.

Flag anything that contradicts a claim in our own live marketing.

## Output

Save to `output/reports/competitor-sweep-<micro-market>-<YYYY-MM-DD>.md`.
Keep the summary under one page; put the detail below it.
