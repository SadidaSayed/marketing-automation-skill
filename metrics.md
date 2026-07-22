# Metrics & Reporting

What to measure per lifecycle stage, and how to report it so it's credible rather than vanity.

---

## 1. Metrics by Lifecycle Stage

Match the metric to what that stage is actually trying to accomplish (see `SKILL.md` Section 2) — a single generic dashboard reused across every stage hides whether each one is working.

| Stage | Primary metric | Supporting metrics |
|---|---|---|
| **Awareness** | Opt-in/signup completion rate | Source quality (downstream conversion by acquisition channel, not just volume) |
| **Nurture** | Progression rate to next stage (e.g. lead → MQL, subscriber → trial) | Engagement rate (opens/clicks) as a leading indicator only — not the goal itself |
| **Conversion** | Conversion rate (trial→paid, cart→purchase, MQL→SQL→closed) | Time-to-conversion, sequence-attributed conversions vs. baseline |
| **Retention/Onboarding** | Activation rate (% reaching defined "first value" milestone) | Time-to-activation, churn/renewal rate |
| **Advocacy/Expansion** | Referral rate, expansion/upsell revenue | NPS/CSAT, review volume |

---

## 2. Message-Level Metrics (any campaign type)

- **Delivery rate** — did it arrive at all; a deliverability problem invalidates every metric downstream of it.
- **Open rate** — directional only; increasingly unreliable due to privacy features (e.g. image-blocking, auto-open by mail clients) that inflate it artificially. Don't optimize sequences around open rate alone.
- **Click-through rate** — stronger signal than opens; measures actual interest in the CTA.
- **Click-to-conversion rate** — of those who clicked, how many completed the target action; isolates message quality from landing/offer quality.
- **Unsubscribe/complaint rate** — a leading indicator of list fatigue or a mismatched segment; a spike here after a specific send is a signal to revisit that message's targeting or frequency, not just its copy.
- **List growth vs. decay** — net change, not just new adds; a list bleeding unsubscribes/bounces as fast as it grows isn't actually growing.

---

## 3. Attribution & Reporting Discipline

- **Report against a comparison, not an absolute number.** "22% open rate" means little alone — "22% vs. 18% last quarter" or "vs. a 15% no-automation control group" is what makes a number actionable.
- **Use holdout/control groups when testing a new automated sequence**, where feasible — send to a small % holdout with no automation (or the old version) to isolate the sequence's actual lift rather than crediting it with conversions that would've happened anyway.
- **Attribute to the sequence, not just the channel.** "Email drove the sale" is less useful than "the day-3 win-back email drove the sale" — attribute at the message/step level when the platform supports it, so you know which steps in a sequence are pulling weight and which are dead weight.
- **Segment every report.** An aggregate "average" campaign performance can hide that one segment loves it and another is unsubscribing because of it.

---

## 4. Benchmark Ranges (directional only)

Actual benchmarks vary enormously by industry, list health, and send frequency — treat any published benchmark as a rough sanity check, not a target:
- Transactional/triggered emails (order confirmation, receipt) typically far outperform bulk/nurture sends on opens and clicks — this is normal, not a sign the nurture sequence is failing.
- Win-back/re-engagement sequences typically have the lowest engagement of any campaign type by design — they're targeting an already-cold segment; judge them on incremental reactivation, not against nurture-sequence benchmarks.
- Sequence step performance usually declines across steps (step 1 outperforms step 4) — a sequence that doesn't follow this pattern is worth investigating (is step 1 mistargeted, or are later steps actually adding value you'd otherwise miss?).

When in doubt, ask the user for their actual historical numbers before recommending a target — a generic industry benchmark is a starting sanity check, not a substitute for their own baseline.
