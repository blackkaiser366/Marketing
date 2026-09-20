# Setup

Two halves. The plugin gives you the agents and skills on demand. The
scheduled tasks make them run every night whether or not your computer is on.

---

## 1. Install the plugin

Open the `.plugin` file in Claude Cowork and press install. The nine agents
and nine skills become available immediately.

Check it worked: ask **"what skills and agents do I have?"** — you should see
nine of each.

---

## 2. Connect the tools the agents need

| Agent | Needs |
|---|---|
| `quality-reviewer` | Zoho CRM (read access is enough — it never writes) |
| `performance-marketer` | Meta Ads, Google Ads |
| `reputation-monitor` | Web search; Meta for comments and DMs |
| everything else | nothing beyond the reference files |

If a connector is missing the agent will say so rather than reporting on
partial data. That is deliberate.

---

## 3. Put the reference files where the scheduled tasks can reach them

This is the step people skip, and it is the one that breaks everything.

A scheduled task runs in the cloud. **It cannot see your computer's files.**
If the agents are to run overnight with your laptop shut, their reference
material has to live somewhere the cloud can read — a Google Drive folder is
the straightforward choice.

1. Create a Drive folder. Call it something obvious, e.g.
   *"Marketing Brain"*.
2. Upload `reference/projects.md` and a condensed context file into it.
   Create a `reports` subfolder for the agents' daily output.
3. Note the file IDs — the long string in each file's Drive URL. The
   scheduled-task prompts reference files by ID, so you must replace the IDs
   in the supplied prompts with your own.

> **The sync rule.** Whichever copy you edit by hand is the master; the other
> will go stale. When a price or a RERA number arrives, update **both** in the
> same sitting. A stale RERA number in a live ad is the exact failure this
> whole system exists to prevent.

---

## 4. Create the six scheduled tasks

Each file in `scheduled-tasks/` holds one task's schedule and its complete
prompt. For each one: create a new scheduled task, paste the prompt, set the
cron expression given at the top of the file.

**Before pasting, replace every Drive file ID in the prompt with your own.**
The IDs in the supplied prompts point at the original workspace and will fail
for anyone else.

Schedules as shipped (cron is UTC; these are 21:30 and 22:15 India time):

| Task | Cron (UTC) |
|---|---|
| Daily Lead Quality Audit | `0 16 * * *` |
| Daily Ads Performance Monitor | `0 16 * * *` |
| Daily Reputation & Reviews Monitor | `0 16 * * *` |
| Weekly Creative Director & Designer Brief | `0 16 * * 1` |
| Monthly Marketing Plan | `0 16 1 * *` |
| Nightly Digest | `45 16 * * *` |

The digest runs 45 minutes after the other three so it has their output to
read. It is the only one that notifies you — the rest file silently into
Drive. One ping a night, not six.

---

## 5. Turn on automatic approval — do not skip this

Each scheduled task has its own approval setting. Left off, the task stops
mid-run waiting for permission, and at half past nine at night nobody is
there to give it. You get nothing.

Open each task's settings and switch on **Automatically approve**. All six.

This is safe here because none of these agents can post, spend, reply or
write to the CRM. Automatic approval lets them read and report; it does not
let them act.

---

## 6. Verify

Fire one task manually — the Lead Quality Audit is the best test, since it
exercises the reference files, the CRM connection and the Drive write in one
run. A successful run leaves a dated report in your Drive `reports` folder.

If it stalls, the usual causes in order: automatic approval still off; a Drive
file ID that wasn't replaced; a connector not authorised.

---

## Known gaps in the shipped configuration

Carried over honestly rather than hidden:

- **Three CRM fields are unpopulated** in the source Zoho instance:
  `First_Contact_Due_By`, `Assigned_Date_and_Time`, and `SLA_Status` (which
  still holds Zoho's default "Option 1 / Option 2" placeholders). The audit
  computes deadlines itself and ignores `SLA_Status`. But because
  `Assigned_Date_and_Time` is empty, **assignment lag is invisible** — a delay
  caused by routing gets attributed to whoever eventually owned the lead. Fix
  that field first if you fix anything.
- **`reference/projects.md` carries `[FILL]` markers** for every price, for
  the RERA numbers of two projects, and for availability. This is intentional:
  the system is designed to produce complete work around missing numbers
  rather than stall. Fill them in and re-sync.
- **`reference/brand.md` has no colour codes or fonts yet.**
- **`reference/lead-qualification.md`** still has four open items: the
  disqualification budget threshold, who leads are assigned to, and who
  reviews the untouched-lead list daily.
