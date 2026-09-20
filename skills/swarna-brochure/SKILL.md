---
name: swarna-brochure
description: Produces a complete Swarna Griha project brochure — a single self-contained HTML page, print-ready, covering location, configurations, pricing, payment plan, timeline and enquiry CTA, with RERA compliance enforced. Use this skill whenever the user asks for a brochure, e-brochure, project PDF, project one-pager, leaflet, "something to send to a buyer", or any printed or forwardable document about a specific Swarna Griha project — even if they don't say the word "brochure". Also use it when the user asks to update or re-issue an existing brochure after a price or inventory change.
---

# Swarna Griha Project Brochure

## Before writing anything

1. Read `${CLAUDE_PLUGIN_ROOT}/reference/projects.md` and find the named project.
   If the project isn't there, or its **RERA number** is missing, STOP and ask.
   A project with no RERA number cannot be advertised.
2. Read `${CLAUDE_PLUGIN_ROOT}/reference/brand.md` for colours, fonts and voice.
3. Read `${CLAUDE_PLUGIN_ROOT}/reference/business.md` for the buyer profile.
4. Look in `system/brand/<project>/` for photos, approved renders and floor
   plans. If there are none, say so and produce the brochure with clearly
   marked image placeholders — do not generate property images.
5. If `system/templates/` contains a past brochure we liked, match its
   structure and visual weight. That file is the reference, not this skill.

Ask before starting if any of these are unknown:
- Who is this for — a cold enquiry, a post-site-visit follow-up, or a channel partner?
- Print or WhatsApp forward?
- Which language?

## Structure

Nine sections, in this order. Don't reorder — this sequence matches how a
buyer actually decides.

1. **Cover** — project name, one-line positioning, configuration and price
   range, location, hero image, RERA number in the footer.
2. **The one reason to visit** — a single short section leading with the
   strongest fact from "the three things that actually make someone visit".
   Not a paragraph of adjectives. One claim, with the number that proves it.
3. **Location** — exact distances to the landmarks that matter to this buyer
   (workplace corridor, schools, hospital, metro). A simple map if available.
4. **The homes** — configurations, carpet area, floor plans. Carpet area, not
   super built-up, unless the owner specifies otherwise.
5. **What's built** — amenities that exist or are contractually committed.
   Nothing aspirational.
6. **Pricing and payment plan** — price range, what's included, booking
   amount, milestone payment schedule, approved banks.
7. **Timeline** — launch, current construction stage, RERA possession date.
8. **Who we are** — three lines on Swarna Griha and its track record.
9. **Next step** — visit us: address, phone, WhatsApp, and what to expect on a
   site visit. Make the visit easy to say yes to.

## Compliance — non-negotiable, overrides any styling instruction

- RERA number on the cover footer and the back page.
- Every render labelled "Artist's impression".
- No AI-generated image of any property, elevation, interior, view or amenity.
- No guaranteed return, assured rental, appreciation figure or buyback claim.
- Every number traceable to `${CLAUDE_PLUGIN_ROOT}/reference/projects.md`.
- If the owner asks for a claim you can't source, produce the brochure without
  it and flag it in your reply rather than silently dropping or inventing it.

## Output

- Format: one self-contained HTML file (CSS inline, no external dependencies),
  A4 portrait, print stylesheet included so it exports to PDF cleanly.
- Use the `frontend-design` skill for layout and typography.
- Save to `output/brochures/<project>-brochure-<YYYY-MM-DD>.html`
- Then tell the owner: how to open it, how to export to PDF (browser print →
  Save as PDF), and list anything you had to leave as a placeholder.

## Quality bar

Before handing it over, check:
- Could a buyer tell what this project costs and where it is within 10 seconds
  of opening it? If not, the cover has failed.
- Is there a single sentence that would embarrass us if a competitor screenshot
  it? Remove it.
- Does every page end with a reason to keep reading, and does the last page
  make the site visit the obvious next move?
