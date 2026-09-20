# Swarna Griha — Lead Handling SLA

Agreed with Ananya Sharma, 20 September 2026. Defines what counts as a breach
and which Zoho fields hold the data. `quality-reviewer` reads this before every
run and stops if any threshold or field name below still reads [FILL].

This file is the master. A synced copy lives in the Google Drive folder
"Swarna Griha Marketing Brain" so the cloud agents can read it when this Mac
is off. **When you edit this file, the Drive copy must be re-synced or the
nightly audit runs on stale rules.**

All times Asia/Kolkata.

## 1. Field map — Zoho Leads API names

| Meaning | API name |
|---|---|
| Lead arrival (clock starts) | `Lead_Created_Time` (fallback `Created_Time`) |
| First genuine contact | `First_Contacted_At` |
| Owner / Stage / Source | `Owner` / `Lead_Status` / `Lead_Source` |
| Paid sub-source | `Sub_Source_for_Digital_Ads`, `Sub_Source_for_Meta_Ads` |
| Attempts made | `Contact_Attempts_Retries`, `Last_Contact_Attempt_Date`, `Contact_Method` |
| RNR | `RNR_Entered_At`, `RNR_Aging_Bucket`, `RNR_Call_Count`, `RNR_Call_Answered`, `RNR_Call_Not_Answered`, `Consecutive_Call_Not_Answered` |
| Overdue | `Over_Due_Status` |
| Disqualification | `Disqualified_Reason`, `Disqualified`, `Disqualified_Notes` |
| Not converted | `Reason_For_Not_Converted`, `Not_Converted` |
| Site visits | `Visit_Date_And_Time`, `Site_Visit_Count`, `Site_Visit_Attended`, `Site_Visit_Not_Attended` |
| Follow-up | `Under_Follow_Up_Start_Date`, `Follow_Up_Missed`, `Next_Follow_Up_Date_Time` |
| Dormancy / activity | `Dormant_Since`, `Dormant_Reason`, `Last_Activity_Time` |

### Known data-quality limits — verified 20 September 2026

1. **`First_Contact_Due_By` is null on every lead.** No workflow computes it.
   Calculate deadlines from `Lead_Created_Time` plus section 3.
2. **`Assigned_Date_and_Time` is null on every lead.** Assignment lag is
   invisible. A six-hour routing delay will be attributed to whichever owner
   eventually received the lead. State this whenever an owner is named.
3. **`SLA_Status` holds Zoho's default placeholders** ("Option 1", "Option 2",
   "Monitoring"). Meaningless. Do not read or report it.

If any of these starts being populated, revise this section — the agent should
flag the change rather than silently switching source.

## 2. Stages

Raw → Contacted → Qualified → Site Visit Booked → Visited → Negotiation →
Booked → Registered

- **Contacted** — we spoke to a human. Dialling is not contact.
- **Qualified** — budget, timeline and funding known and workable.
- **Visited** — they physically stood on the site.

Zoho `Lead_Status` maps in: Raw = New Lead. Contacted = Attempted to Contact,
Contacted, RNR, Not Reached, Not Responsive, Under Follow-up. Qualified =
Qualification, Qualified, Ready for Site Visit. Site Visit Booked = Site Visit
Scheduled. Visited = Site Visit Completed, all Post Visit – *. Closed = Booked,
Disqualified, Not Qualified, Not Converted, Junk Lead, Lost Lead. Parked =
On Hold, Dormant, Contact in Future Again, Site Visit – No Show.

## 3. Response-time SLA

Clock starts at `Lead_Created_Time`.

| Stage | Target | Breach |
|---|---|---|
| First WhatsApp | 5 min | contact later than 5 min, channel WhatsApp |
| First call | 30 min | `First_Contacted_At` more than 30 min after arrival |
| Untouched | 24 h | no contact at all past 24 business-adjusted hours |

The 24-hour rule is absolute. No lead sits untouched past 24 hours, ever. It
is the most serious category and leads the breach log.

**Severity.** Critical: untouched past 24h, or 48h with no activity in any
stage. Major: first call missed by more than 4x (over 2 hours). Minor: first
call missed, under 2 hours.

## 4. Business hours and the after-hours clock

**Business hours 09:00–20:00 IST, seven days.** The clock pauses outside them.
A lead arriving 23:10 starts at 09:00 next morning. Overnight leads are not
breaches and do not enter the compliance rate.

**They are still reported.** Every report carries an after-hours line: how many
leads arrived 20:00–09:00, and the median real wall-clock wait to first
contact, clock pause ignored.

Baseline before this SLA existed (20 Sep 2026): overnight leads were first
contacted between 10:30 and 11:30 the next morning — 7 to 13 hours of real
wait — while working-hours leads were answered in 6 to 30 minutes. Track
whether that gap moves.

## 5. RNR

**One unanswered call sets `Lead_Status` = RNR.** This matches how the team
works and is NOT a breach.

The report still prints the **attempts-before-parking distribution** every day:
of leads in RNR, how many had 1 attempt, 2, 3, 4+. Reported as a distribution,
never as an accusation.

**Escalation:** five unanswered calls within a rolling 30 days moves the lead
to Disqualified, reason "RNR Multiple Attempts". Under five, it stays RNR.

Flag as process issues: RNR leads with `RNR_Call_Count` = 0 (parked with no
call recorded at all); RNR leads older than 30 days that have neither reached
five attempts nor been disqualified.

## 6. Disqualification

Permitted reasons: Junk, RNR Multiple Attempts, Budget mismatch, Location
mismatch, Requirements mismatch, Lost to competition.

Flag: blank or "-None-" reasons; "Junk" with no `Disqualified_Notes`; any
owner disqualifying above 40% of their assigned leads — with the denominator
shown, framed as a question about lead quality or qualification, never a
verdict on the person.

## 7. Stage hygiene

Any lead in the same `Lead_Status` more than 7 days with no change in
`Last_Activity_Time` is stuck. Group by stage.

**Repeat offenders** — a lead breaching at more than one stage means nobody
owns it. These lead the flags. They are the ones that die.

## 8. Site visits

Daily: booked, completed, no-showed, and **no-show rate by `Lead_Source`**.
A source with a high no-show rate is a lead-quality question, not a
sales-team question.

## 9. Escalation

**Report only.** Named in the next daily report with the owner. Nothing written
to Zoho. No same-day alert. No reassignment. Read-only without exception.

## 10. Clustering

Name the kind of problem, not the count. One hour of the day = staffing.
One source = volume. One owner = training.

## 11. Reporting standard

Process, not person. "Four leads from Tuesday were untouched at 26 hours, all
assigned to one owner" is useful. "X is careless" is not, and is not the
agent's call.

Lead with the three things that cost money yesterday. One page. End with a
WhatsApp summary under 60 words. If the CRM is unavailable, say so rather than
reporting on partial data.
