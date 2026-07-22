# Sequence & Copy Templates

Generic structures for the campaign types in `SKILL.md` Section 6. Fill in brand voice, product specifics, and real data before sending — nothing here should go out with placeholders still in it.

---

## 1. Welcome / Onboarding Sequence

**Goal:** get a new signup/customer to their first real "aha" moment as fast as possible.

| Step | Timing | Purpose | Exit condition to check |
|---|---|---|---|
| 1. Confirm | Immediately | Confirm signup/purchase, set expectation for what's next | N/A |
| 2. First value | Within 24h | One clear action that gets them a result, not a feature tour | Did they complete it? If yes, skip to step 4. |
| 3. Nudge | Day 2–3 | Remove the most common blocker to step 2 (short how-to, or offer help) | Only sends if step 2 action still incomplete |
| 4. Expand | Day 5–7 | Introduce one adjacent feature tied to their stated goal | Only if step 2 completed |
| 5. Check-in | Day 10–14 | Human touch or feedback ask; route to sales/CS if signals warrant | Ends sequence either way |

**Email 2 (first value) skeleton:**
```
Subject: [specific action] takes about [X minutes] — here's how

Hi [name],

The fastest way to see [product] work is [specific single action].

[1-2 sentence walkthrough or a single screenshot/gif]

[CTA button: Do the thing]

Questions? Just reply — a person reads this inbox.
```

---

## 2. Nurture / Drip Sequence

**Goal:** stay useful and top-of-mind for someone not yet ready to buy — earn the next conversation, don't force it.

Arc (4-6 emails, spaced 5-10 days apart — widen spacing as the sequence progresses):
1. Useful, standalone content (no pitch) — something valuable even if they never buy
2. Light social proof — a customer story or result, framed as "here's what became possible," not "buy now"
3. Address the most common objection directly and honestly
4. Comparison/education content that positions your approach without naming competitors negatively
5. Soft CTA — invite a next step (demo, trial, consult), not a hard close
6. Re-permission ("still want to hear from us?") if no engagement by the end — protects deliverability and respects attention

**Objection-handling email skeleton:**
```
Subject: "[Common objection, in their words]"?

We hear this a lot: [objection].

Here's the honest answer: [direct, non-defensive response — concede what's true, clarify what's not]

[Optional: one proof point]

If that's still a concern, reply and let's talk it through — no pitch, just answers.
```

---

## 3. Abandonment Sequence (cart / browse / form)

**Goal:** recover a specific, recent, incomplete action — speed matters more than polish here.

| Step | Timing | Content |
|---|---|---|
| 1 | 1 hour | Simple reminder — what they left, one-click return path |
| 2 | 24 hours | Add a reason to act now (answer an objection, show urgency if genuine — don't fabricate scarcity) |
| 3 | 3 days | Final nudge, optionally with an incentive if margin allows |

Exit immediately on completed action — check this in real time, not just at send time, since a same-day completion is common.

---

## 4. Re-engagement / Win-back Sequence

**Goal:** get a lapsed contact to take one small action before writing them off or suppressing them.

1. **Acknowledge the gap.** "It's been a while" — honest, not guilt-tripping.
2. **Remind them of value already realized** — reference something specific and true (a past purchase, a feature they used) rather than a generic pitch.
3. **New-and-relevant hook** — what's changed since they left that might matter to them specifically.
4. **Last-chance / preference message** — give an explicit choice: re-engage, or opt down/out. Respect the answer — a forced re-permission that ignores "no" damages sender reputation.

**Last-chance skeleton:**
```
Subject: Should we stop emailing you?

Hi [name],

We haven't heard from you in a while, so before we assume you've moved on:

[Single most relevant update/offer]

If this isn't useful anymore, no hard feelings — [one-click unsubscribe/preference link].
If it is, [single clear CTA].
```

---

## 5. Lifecycle / Milestone Message

**Goal:** reinforce value at a moment the contact already cares about (renewal approaching, usage milestone, anniversary).

- Lead with **their** milestone/data ("you've done X"), not a generic company update.
- Tie the message to a forward-looking action (renew, upgrade, refer) only after acknowledging the milestone itself.
- Keep it short — this is a relationship-reinforcement moment, not a sales pitch.

---

## General Copy Principles

- **One CTA per message.** Multiple competing CTAs reduce action on all of them.
- **Subject lines describe the specific value inside**, not a generic tease — specificity outperforms cleverness in automated sends at scale.
- **Write for the person mid-lifecycle**, not a first-time reader — reference where they actually are (signed up, trialing, lapsed), since automated messages read as tone-deaf when they ignore context the system already has.
- **Always include an honest, working opt-out/preference path** — required for deliverability and, in most jurisdictions, for compliance.
