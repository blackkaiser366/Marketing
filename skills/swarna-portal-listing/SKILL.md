---
name: swarna-portal-listing
description: Writes Swarna Griha listings for property portals such as 99acres, Housing, MagicBricks and NoBroker — title, description, amenity and highlight fields, photo order and caption set, tuned to how portal search and ranking actually work. Use this skill whenever the user mentions 99acres, Housing.com, MagicBricks, NoBroker, portal listings, "put it up on the sites", refreshing a listing, or asks why portal leads are poor quality.
---

# Swarna Griha Portal Listings

## Before writing

Read `${CLAUDE_PLUGIN_ROOT}/reference/projects.md` (numbers, RERA, availability) and
`${CLAUDE_PLUGIN_ROOT}/reference/business.md` (buyer profile). Ask which portal and which
configuration, since field limits differ.

## How portal buyers behave

They are comparing twenty listings in a grid. The photo and the price decide
whether they open yours; the description decides whether they enquire. Write
for the person who has already seen nineteen near-identical listings.

## What to produce

**Title** — configuration, carpet area, project name, micro-market, and the one
differentiator. No capitals, no exclamation marks.

**Description** — three short paragraphs:
1. What the home actually is: carpet area, layout, floor, facing, view.
2. Location in commute terms — distances to the workplace corridor, schools,
   hospital, transit. This is what portal buyers filter on mentally.
3. Commercials and next step — price and inclusions, booking amount, possession
   date, RERA number, how to arrange a visit.

**Structured fields** — fill every one the portal offers. Listings with blank
fields rank lower and get filtered out of searches.

**Photo order** — the sequence to upload in: exterior or hero shot, living
area, a bedroom, kitchen, bathroom, balcony view, amenity, floor plan,
location map. Real photos only. Caption each one.

**Three title variants** to rotate if the listing goes stale.

## Rules

- Carpet area labelled as carpet area. Never present super built-up as carpet.
- RERA number in every listing — portals require it and buyers check it.
- No AI-generated property imagery. If a room has no photo, leave it out
  rather than illustrate it.
- No return, rental-yield or appreciation claims.
- Availability must match `projects.md` — a listing for a sold unit burns trust
  and wastes the sales team's day.

## Output

Save to `output/listings/<project>-<portal>-<config>-<YYYY-MM-DD>.md`, laid
out field by field so it can be pasted straight into the portal form.
