---
name: swarna-carousel
description: Builds a 6-to-8 slide Instagram carousel for Swarna Griha — slide-by-slide copy, visual direction, caption and hashtags — built around buyer-education topics that earn saves and shares rather than project spam. Use this skill whenever the user asks for an Instagram post, carousel, social post, reel script, content for the page, or says things like "we need to post something this week", "what should we put on Instagram", or gives a raw idea or voice note to turn into a post.
---

# Swarna Griha Instagram Carousel

## The rule that makes this work

Four out of five posts teach. One sells. A page that only posts inventory gets
followed by nobody and shared by nobody. A page that teaches people how to buy
property in our city gets saved, and the saves are where enquiries come from.

## Before writing anything

1. Read `${CLAUDE_PLUGIN_ROOT}/reference/business.md` for the buyer profile and the real
   objections — most good carousel topics are just an objection answered
   honestly in public.
2. Read `${CLAUDE_PLUGIN_ROOT}/reference/brand.md` for colours, fonts and voice.
3. If the post references a specific project, read `${CLAUDE_PLUGIN_ROOT}/reference/projects.md`
   and follow every compliance rule below.
4. If the owner hands you a voice note, transcript or half-formed idea, work
   from that — it will beat anything invented from scratch.

## Topic types that work for us

- **Buyer education** — "What to check in the RERA portal before you pay a
  booking amount", "Carpet vs built-up vs super built-up, in plain numbers"
- **Local knowledge** — "What ₹X per sq ft actually gets you in [area] right now"
- **Objection, answered publicly** — take objection #1 and answer it straight
- **Process demystified** — "The seven documents to ask for before booking"
- **Project post (one in five)** — one project, one strong reason, one CTA

## Structure

- **Slide 1 — the hook.** One specific claim or question. A number beats an
  adjective. If it could sit on a competitor's page unchanged, it's too generic.
- **Slides 2–6/7 — one idea per slide.** Maximum 25 words per slide. If a slide
  needs a paragraph, it's two slides.
- **Final slide — the next step.** Follow, save, or DM us for the checklist.
  One ask, not three.

For every slide give: the on-slide text, and a one-line visual direction.

Then the **caption**: first line must survive truncation and work alone, then
2–4 short lines expanding the idea, then the CTA. Then 8–12 hashtags mixing
city-level, category-level and buyer-intent tags.

## Visual direction

- Use brand colours and fonts from `system/brand/`.
- Text-led graphic slides are where AI image generation is fine — abstract
  backgrounds, typography, icons, festival creatives.
- **Property imagery is never AI-generated.** Real photography or approved
  renders from `system/brand/<project>/`, renders labelled as artist's
  impression. If the shot doesn't exist, say which photo needs taking rather
  than generating one.
- Keep text well inside the safe area — Instagram crops edges on some devices.

## Compliance

If a specific project, price or project feature appears anywhere in the
carousel or caption: RERA number in the caption, numbers sourced from
`projects.md`, no return or appreciation claims, renders labelled.

## Output

Save to `output/carousels/<topic-slug>-<YYYY-MM-DD>.md` with slides, visual
direction, caption and hashtags ready to hand to a designer or an image tool.
If images are generated, save them alongside as `slide-1.png` … `slide-n.png`.
