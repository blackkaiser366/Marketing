---
name: swarna-performance-report
description: Produces the Swarna Griha weekly or monthly marketing report — spend, leads and cost per lead by channel and campaign, lead quality cross-checked against CRM outcomes, site visits and bookings, what changed, and the three things to do next. Use this skill whenever the user asks how the ads are doing, what the cost per lead is, which campaign is working, for a weekly or monthly report, or asks where the marketing money is going.
---

# Swarna Griha Performance Report

## Before starting

Ask the period (default: last 7 days versus the 7 before) and which projects.

Pull what's connected — Meta Ads, Google Ads, the CRM. If a connector isn't
available, say which numbers are missing rather than filling the gap with an
estimate. A report with an honest hole is useful; a report with a guessed
number is dangerous.

## The one thing this report exists to do

Ad platforms report leads. They cannot report lead *quality*. The value here is
joining platform spend to CRM outcomes, so the owner can see which campaigns
produce cheap junk and which produce expensive buyers. Always do that join if
the CRM data is available.

## Structure

**Headline** — four numbers: spend, leads, cost per lead, site visits booked.
Each against the previous period, with the direction of change.

**By channel** — Meta, Google, portals, referral, walk-in. Spend, leads, cost
per lead, and what share of site visits each produced.

**By campaign** — the same, ranked by cost per site visit rather than cost per
lead. Flag any campaign whose cost per lead rose more than 20% period on period.

**Lead quality** — of the leads each source produced, how many were contactable,
qualified, visited, booked. This is the section that changes decisions.

**Funnel leaks** — leads untouched beyond 24 hours, visits with no follow-up
logged, leads stuck in one stage beyond 7 days. Count them and name the cost.

**What changed** — two or three sentences of plain explanation, not a chart.

**Do these three things** — ranked, specific, each with the expected effect.
"Pause ad set X, it produced 40 leads and zero visits at ₹Y each" beats
"optimise targeting".

## Rules

- Never present a platform-reported conversion as a booking.
- Small numbers are noisy: with under ~30 leads in a period, say so rather than
  computing a confident rate off nine data points.
- Recommend pausing or shifting spend, but never change a live campaign,
  budget or bid yourself. The owner acts on the report.

## Output

Save to `output/reports/performance-<period>-<YYYY-MM-DD>.md`, with a
WhatsApp-length summary at the top the owner can forward to the sales head.
