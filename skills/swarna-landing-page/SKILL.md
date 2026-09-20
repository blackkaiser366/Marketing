---
name: swarna-landing-page
description: Builds a single-page, mobile-first landing page for a Swarna Griha project, designed to convert paid traffic into site visits — hero, proof, location, pricing, floor plans, FAQ, enquiry form and WhatsApp CTA, with RERA compliance enforced. Use this skill whenever the user asks for a landing page, microsite, campaign page, "a page for the ad to go to", a project website, or says the ads are getting clicks but no enquiries.
---

# Swarna Griha Landing Page

## Before writing

1. `${CLAUDE_PLUGIN_ROOT}/reference/projects.md` — no RERA number, no page. Stop and ask.
2. `${CLAUDE_PLUGIN_ROOT}/reference/business.md` — buyer profile and the real objections.
3. `${CLAUDE_PLUGIN_ROOT}/reference/brand.md` — colours, fonts, voice.
4. `system/brand/<project>/` — real photos, approved renders, floor plans.
5. Ask: where is the traffic coming from (Meta / Google / portal), and does the
   enquiry go to a form, WhatsApp, or a call?

Match the page's opening line to the ad that sent them. A buyer who clicked a
"6.5 km from Electronic City" ad must land on a page that says that first.

## Structure

1. **Hero** — project name, the one strong claim, configuration + price range,
   location, primary CTA.
2. **The three reasons** — from `projects.md`. Short. Numbers, not adjectives.
3. **Location** — exact distances to the landmarks this buyer cares about.
4. **The homes** — configurations, carpet areas, floor plans, availability.
5. **Pricing** — range, what's included, booking amount, payment milestones,
   approved banks. Stating price openly outperforms hiding it for us.
6. **Construction and possession** — current stage, RERA possession date,
   recent site photos with dates on them.
7. **FAQ** — answer the real objections from `business.md` head on, including
   the honest weaknesses in `projects.md`. Buyers trust a page that admits
   something.
8. **Enquiry** — name, phone, configuration interest, preferred visit day.
   Four fields. Every extra field costs leads.
9. **Footer** — RERA number, company details, address, disclaimer.

Sticky WhatsApp / call button on mobile throughout.

## Compliance

RERA number in the footer and near the hero price. Renders labelled "artist's
impression". No AI-generated property imagery. No return, rental or
appreciation claims. Every number from `projects.md`.

## Output

One self-contained HTML file, CSS inline, mobile-first, fast on a poor 3G
connection — no heavy frameworks, compress images. Use the `frontend-design`
skill for layout and typography.

Save to `output/landing-pages/<project>-lp-<YYYY-MM-DD>.html`, then tell the
owner how to preview it and what still needs wiring up (form endpoint,
WhatsApp number, pixel or conversion tag).
