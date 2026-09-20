# Open Items — and how to work without them

Four things are missing. This file says exactly how to work around each one so
the system is fully usable today.

## The placeholder token rule

When an asset needs a number we don't have, insert a token in double braces —
never a guess, never a rounded figure, never "starting from" with an invented
number.

| Token | What it stands for |
|---|---|
| `{{SG4_PRICE}}` | Swarna Griha 4 price range |
| `{{SG4_BOOKING}}` | Swarna Griha 4 booking amount |
| `{{ANNEXE_PRICE}}` | SG3 Annexe plot pricing |
| `{{NOVA_PRICE}}` | Nova Greens plot pricing |
| `{{ANNEXE_RERA}}` | SG3 Annexe RERA number |
| `{{NOVA_RERA}}` | Nova Greens RERA number |
| `{{POSSESSION_DATE}}` | RERA possession date for the project |
| `{{AVAILABILITY}}` | units or plots currently available |
| `{{PHONE}}` | sales phone number |
| `{{WHATSAPP}}` | WhatsApp business number |
| `{{SITE_ADDRESS}}` | site office address for that project |

At the end of every asset, list the tokens it contains, so the owner can see in
one glance what to fill before it ships. When the numbers arrive, one
find-and-replace finishes the asset — no rewriting.

## 1. Prices — workaround: build price-free assets

Price-free marketing is normal and legitimate in this segment. Where a price
would go, use the strongest non-price hook instead:

- **EMI framing is not permitted without the price.** Do not compute or imply
  an EMI from a guessed price.
- Use instead: "Price on request", "Share your budget and we'll tell you
  honestly if this fits", or lead with PMAY eligibility where it applies.
- The qualifying question does the work a price would: asking a buyer their
  comfortable budget on WhatsApp is better lead qualification than publishing
  a number anyway.

Assets that work fully without price: brochures (with `{{SG4_PRICE}}` in the
pricing panel), all educational carousels, competitor sweeps, the entire
follow-up and objection-handling system, portal listing copy except the price
field, and every landing page section except the pricing block.

## 2. RERA numbers for SG3 Annexe and Nova Greens — no workaround

Under Section 3 of the RERA Act, a project that requires registration cannot be
advertised, marketed, booked or sold before it is registered. This is a legal
prohibition on the advertisement itself, and the penalty runs up to 10% of
project cost. It is not a stylistic rule and this system does not route around
it.

**What Claude does instead of refusing:**
- Build the asset in full with `{{ANNEXE_RERA}}` / `{{NOVA_RERA}}` in place.
- Save it to the normal output folder with `-HOLD` appended to the filename.
- State plainly in the reply: ready to publish the moment the number is supplied.

So the work gets done now and ships the day the number arrives.

**What Claude will not do:** publish, or prepare for immediate publication, an
ad, listing, brochure or broadcast for these two projects with the RERA line
removed, softened, or replaced with "RERA registration in process".

If the projects are in fact registered and the website simply doesn't show it,
this clears in one message. If they are not yet registered, the owner needs to
know that before spending on ads, not after.

## 3. Availability and possession dates — workaround: don't claim either

- Never state scarcity we can't evidence. No "few units left", no "closing soon".
- Where availability would appear, write `{{AVAILABILITY}}` or leave it out
  entirely — an asset with no availability claim is complete; one with a made-up
  one is a liability.
- Never state a possession date. For SG4, "Phase 1 completed" is a true,
  publishable, and genuinely strong fact — use that instead.

## 4. Phone and WhatsApp numbers — workaround: tokens

Every CTA ends with `{{WHATSAPP}}` / `{{PHONE}}`. The website contact form URL
(swarnagriha.com/contact) is real and can be used as the fallback CTA today.

---

## What we can produce right now, in full

- Everything for **Swarna Griha 4** except the price and possession blocks
- **All educational and brand content** — carousels, blogs, buyer guides
- The **complete sales system** — qualification, scripts, objection handling,
  follow-up sequences, WhatsApp templates
- **Competitor sweeps** across Belagavi, Kolar and Tumkur
- **Performance reports** off the ad accounts and CRM
- **Credibility content** built on the delivered record: 1,560 homes, PMAY
  award, Kolar's first apartment community

That is most of a marketing department. The gaps affect the pricing line of
three documents, not the system.
