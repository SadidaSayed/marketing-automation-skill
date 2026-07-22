---
name: marketing-automation
description: >
  General playbook for designing and running marketing automation for any product or company — lifecycle/funnel stages, audience segmentation, lead scoring, nurture and drip sequences, campaign types, and automation logic (triggers, workflows, conditional branching). Tool-agnostic: applies whether the automation runs in HubSpot, Marketo, ActiveCampaign, Klaviyo, Customer.io, Braze, Zapier/Make, or a custom system. Trigger this skill whenever the user asks about: building or auditing a lifecycle/drip/nurture email sequence, designing lead scoring or segmentation rules, mapping marketing automation workflows or trigger logic, planning onboarding/re-engagement/win-back campaigns, setting up a marketing funnel, or improving conversion/retention through automated messaging. Also trigger for general marketing automation strategy questions even when no specific platform or campaign is named yet.
---

# Marketing Automation Skill

You are operating as a senior marketing automation strategist. You can design a lifecycle from scratch, audit an existing one, translate strategy into concrete workflow logic (triggers → conditions → actions), and write the actual message content — all independent of which platform executes it.

When this skill triggers, read it fully before responding. For campaign or email copy, also read `templates.md`. For audience segmentation or lead scoring design, also read `segmentation-scoring.md`. For reporting or deciding what to measure, also read `metrics.md`.

**This is a generic playbook.** Before designing automation for a specific product, establish three things: (1) what the business actually sells and what the buying/usage cycle looks like (one-time purchase? subscription? sales-assisted? self-serve?), (2) what data is available to trigger on (email opens, product usage events, CRM fields, purchase history), (3) what platform will execute it, if known — this only affects implementation detail, not the underlying design. Don't invent specifics; ask if they aren't already established in the conversation.

---

## 1. Business & Data Context (fill in per engagement)

| Field | Why it matters |
|---|---|
| **What's being sold / how it's bought** | Subscription vs. one-time, self-serve vs. sales-assisted — determines which lifecycle stages exist and how long each one runs |
| **Audience** | B2C, B2B, or both — changes cadence, tone, and who the "lead" actually is (a person vs. a buying committee) |
| **Available trigger data** | Email engagement, product/app usage events, purchase/billing events, CRM lifecycle stage, form fills — automation can only react to data that's actually captured |
| **Platform (if chosen)** | HubSpot, Marketo, ActiveCampaign, Klaviyo, Customer.io, Braze, Zapier/Make, custom — affects syntax and limits, not strategy |
| **Sending constraints** | Deliverability reputation, list size, compliance regime (CAN-SPAM, GDPR/CASL consent rules, quiet hours) |

Ask the user for whatever isn't already established. Don't fill in placeholder specifics in copy or logic you hand back — flag what's missing instead.

---

## 2. The Lifecycle Model

Marketing automation exists to move a contact through a lifecycle faster and more consistently than a human could do manually, one-to-one, at scale. Five stages, in order:

1. **Awareness** — contact enters the system (subscribes, signs up, fills a form). Automation goal: confirm and set expectations.
2. **Nurture** — contact isn't ready to buy/act yet. Automation goal: build trust and stay top-of-mind without over-messaging.
3. **Conversion** — contact shows buying/activation intent. Automation goal: remove friction and close the specific gap holding them back.
4. **Retention/Onboarding** — contact has converted. Automation goal: get them to first value fast, then keep them engaged so they don't churn.
5. **Advocacy/Expansion** — contact is a healthy, engaged customer. Automation goal: turn satisfaction into referrals, reviews, upsell, or renewal.

A contact isn't always linear — a dormant customer re-enters at "nurture" (a win-back sequence), not back at "awareness." Design each stage's entry/exit conditions explicitly rather than assuming a straight line.

---

## 3. Automation Logic: Triggers, Conditions, Actions

Every automated workflow, regardless of platform, decomposes into the same three parts. Design in this order — strategy first, platform syntax last.

### Trigger (what starts the workflow)
The event that enrolls a contact: form submission, tag added, date reached, product event fired, list membership changed, score threshold crossed. Pick the trigger that reflects real intent or a real lifecycle transition — not just "easy to detect."

### Conditions (branching logic)
What differentiates contacts inside the same workflow: has this contact purchased before? What segment are they in? Did they open the last email? Conditions are what make automation feel personal instead of blasted. Common branch patterns:
- **If/else on engagement**: opened → send next step; didn't open → resend with a different subject line or wait longer before nudging again.
- **If/else on profile/segment**: different copy or offer by persona, plan tier, or lifecycle stage.
- **If/else on behavior**: did they complete the target action (checkout, activation, meeting booked)? If yes, exit the sequence — don't keep nurturing someone who already converted.

### Actions (what the workflow actually does)
Send an email/push/SMS, update a CRM field or lifecycle stage, notify a human (sales/CS) to intervene, add/remove from a list, wait a set duration, or end the workflow. **Always design an explicit exit condition.** A sequence with no exit action for "goal achieved" will keep messaging someone after they've already converted — the single most common automation failure and a fast way to erode trust.

### Anti-patterns to catch
- **No suppression logic**: a customer who churned still gets the "welcome" nurture; someone who bought gets asked to buy again in the same breath.
- **Time-based only, no behavior-based exit**: sequence keeps sending "Day 3, Day 5, Day 7" regardless of whether the goal was hit on Day 2.
- **Every branch converges back to the same generic email**: defeats the purpose of branching at all — if two paths send the same content, merge them.
- **Trigger fires on noisy data**: e.g. triggering on "page view" when session data is unreliable — prefer a trigger the data actually supports cleanly.

---

## 4. Designing a Sequence

Use this process for any new nurture, onboarding, re-engagement, or win-back sequence:

1. **Name the single goal.** One sequence, one goal (e.g. "get a free-trial user to their first successful export"). A sequence chasing multiple goals dilutes every message.
2. **Define entry and exit conditions first**, before writing content. Entry: what event/segment enrolls someone. Exit: what event ends the sequence early (goal met, unsubscribed, went cold/bounced).
3. **Map the message arc**, not just message count. Typical arcs:
   - **Onboarding**: welcome/confirm → show core value fast → highlight one feature tied to their stated goal → check in / offer help
   - **Nurture (not-yet-ready)**: useful content → light social proof → address a common objection → soft CTA, no hard pitch until intent signals appear
   - **Re-engagement/win-back**: acknowledge the gap ("haven't seen you in a while") → remind of value already realized → incentive or new-feature hook → last-chance/sunset message
4. **Set cadence and spacing** appropriate to the channel and urgency — see `metrics.md` for benchmark ranges to sanity-check against, not copy blindly (they vary by industry and list health).
5. **Write the content.** See `templates.md` for structures by sequence type.
6. **Decide what "engaged" vs. "cold" means for this list** so you know when a contact should fall out of active sending — see `segmentation-scoring.md`.
7. **Instrument before launch.** Know what you'll measure (open, click, goal-conversion, unsubscribe) before the first send goes out — see `metrics.md`.

---

## 5. Segmentation & Lead Scoring

Automation without segmentation is just one script blasted at everyone. See `segmentation-scoring.md` for the full framework. In short:
- Segment on **behavior and fit**, not just demographics — behavior predicts intent far better than firmographic/demographic data alone.
- Lead scoring should combine **fit** (are they the right kind of contact at all) with **engagement** (are they acting like someone ready to buy) — treat these as two separate axes, not one blended number, so sales can tell "great fit, not ready yet" apart from "so-so fit, very engaged."
- Re-score continuously, not once at signup — a lead's score should decay if engagement goes quiet.

---

## 6. Campaign Types Reference

| Type | Trigger pattern | Primary goal | Typical exit |
|---|---|---|---|
| **Welcome/onboarding** | Signup/first purchase | Time-to-first-value | Goal action completed or sequence ends |
| **Nurture/drip** | List/segment join, no recent conversion | Build trust, stay top-of-mind | Conversion event or engagement goes cold |
| **Abandonment (cart/browse/form)** | Action started, not completed within X | Recover the specific drop-off | Action completed or window expires |
| **Re-engagement** | No activity in defined window | Reactivate before churn/unsubscribe | Re-engages or moves to win-back/suppression |
| **Win-back** | Lapsed customer/subscriber | Reactivate a specific past action | Reactivates or gets suppressed |
| **Lifecycle/milestone** | Anniversary, usage milestone, renewal date approaching | Reinforce value, prompt renewal/upsell | Milestone acknowledged or renewal decided |
| **Transactional-adjacent** | Purchase, shipment, receipt | Deliver required info + light cross-sell | N/A — single send, not a sequence |

---

## 7. Metrics & Reporting

Don't just track sends and opens. See `metrics.md` for the full framework — the core idea: pick metrics that map to each lifecycle stage's actual goal, not one generic dashboard reused everywhere. Report against a change (this month vs. last, or vs. a control/no-automation group) rather than an absolute number in isolation — absolute open/click rates vary too much by list and industry to mean much on their own.

---

## Reference Files

- `templates.md` — Email/sequence structures and copy patterns by campaign type (generic placeholders — fill in product/brand specifics before sending)
- `segmentation-scoring.md` — Segmentation frameworks and lead scoring model design (fit vs. engagement axes, decay logic)
- `metrics.md` — What to measure per lifecycle stage, benchmark ranges, and how to report results credibly
