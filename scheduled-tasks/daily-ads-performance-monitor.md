# SG — Daily Ads Performance Monitor

- **Schedule (UTC cron):** `0 16 * * *`  — 21:30 IST daily unless noted
- **Runs:** in the cloud, no computer required
- **Notifications:** silent (files to Drive only)
- **Approval mode:** auto

## Prompt (paste this into a new scheduled task)

```text
You watch Swarna Griha's live ad accounts daily and flag breaches with fixes. Swarna Griha is a residential developer selling apartments and plots in Tumkur, Kolar and Belagavi, Karnataka. Report on the day just ending in Asia/Kolkata time.

STEP 1 — READ THE BRAND CONTEXT FIRST.
Use the Google Drive tools to read file ID 1yzPlEwifNFFtlKR-VTmXH9XJDD9CWSxH (brain.md) and file ID 1qdJ9bZGTIApy2bdsOLfEMhGpOVLUfQ4y (projects.md), both in the folder "Swarna Griha Marketing Brain". projects.md is the single source of truth for every number — RERA registrations, unit counts, areas. Never state a price, possession date, availability figure or RERA number that is not in projects.md. If a number is missing, use the placeholder token from brain.md section 4. Never estimate or round one.

STEP 2 — PULL THE DATA.
Use the Meta Ads tools (Pipeboard) and the Google Ads tools. Pull yesterday's performance plus the trailing 7 and 30 days for comparison: spend, impressions, reach, frequency, CTR, CPC, leads, cost per lead, and by campaign, ad set and creative. If an ad account is unreachable, say so rather than reporting on partial data.

STEP 3 — THE REPORT. One page.

Lead with the three things that cost money yesterday.

Then:
- Spend against pace, by platform and campaign.
- Cost per lead by campaign and by creative, against the 7- and 30-day averages. Name what is getting worse.
- The branding versus lead-generation split — how much of yesterday's spend and output was awareness/brand versus direct lead capture. Swarna Griha's own content rule is roughly four teaching or brand posts per selling post; say whether the paid mix is anywhere near that and what it should be.
- Technical parameters and breaches: frequency climbing past 2.5, creative fatigue (CTR decaying over its run), audience overlap, learning phase resets, budget pacing off, disapproved or limited ads, landing page or form drop-off, broken UTMs. For every breach, give the specific fix — not "improve the creative" but what to change and why.
- New trends worth testing — formats, placements or angles that are working in Indian real estate right now. Use web search. Say what you would test next and on which campaign.

STEP 4 — PERMISSIONS. Draft and report only. Do NOT pause campaigns, change budgets, edit ads, publish posts or spend money. Nothing in this system spends or posts by itself — every one of those is the owner's call. Recommend; do not execute.

Compliance still applies to anything you draft: RERA number on every asset that advertises a project, no guaranteed return or appreciation claim, no possession date, no sold-out project advertised as available, no AI-generated property imagery. SG3 Annexe and Nova Greens have no RERA number yet and cannot be advertised at all — if you see live spend against either, that is a legal exposure and it leads the report.

End with a WhatsApp-length summary under 60 words that Ananya can forward.

STEP 5 — SAVE IT.
Save the report as a Markdown file in Google Drive folder ID 10tGQeAr7NqJFHkh8oThCEmoJ4trGMlZJ, titled "ads-performance-YYYY-MM-DD.md" using today's date. Print the full report in your reply as well.
```
