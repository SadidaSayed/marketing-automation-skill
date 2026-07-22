# Segmentation & Lead Scoring

Framework for deciding who gets which automation, and how to prioritize leads for sales or higher-touch nurture.

---

## 1. Segmentation Axes

Segment on more than one axis and combine them — a single axis (e.g. just "industry" or just "opened last email") produces automation that's either too broad or too narrow.

| Axis | Examples | Use for |
|---|---|---|
| **Fit / firmographic** (B2B) or **demographic** (B2C) | Company size, industry, role; age, location, stated preferences | Determines whether they're a viable buyer at all — doesn't predict timing |
| **Lifecycle stage** | New lead, MQL, SQL, customer, at-risk, lapsed | Determines which sequence/stage they belong in — see `SKILL.md` Section 2 |
| **Behavior/engagement** | Email opens/clicks, product usage events, page visits, content downloads | Predicts intent and timing — the strongest signal for "is now the moment" |
| **Value/tier** | Plan level, deal size, purchase frequency | Determines investment level — how much manual/human touch a segment justifies |

**Practical rule:** behavior and lifecycle stage should drive *when* and *what* automation fires; fit/value should drive *how much* investment (fully automated vs. automated-plus-human-handoff) a segment gets.

---

## 2. Lead Scoring Model

Score on two separate axes rather than one blended number — collapsing them hides the difference between "great prospect, not ready yet" and "so-so prospect, very active right now."

### Fit score
Static-ish attributes that answer "is this the kind of contact/account we want at all":
- Firmographic/demographic match to ideal customer profile
- Role/seniority (B2B) or stated need/use case (B2C)
- Source quality (some acquisition channels convert better than others — weight accordingly)

### Engagement score
Dynamic, behavior-based, should **decay over time** without activity:
- Email opens/clicks (weight clicks higher than opens — opens are a weaker signal, easily inflated by image-preloading)
- Website/content engagement (pricing page visit >> blog read, for most B2B models)
- Product usage events, if there's a free trial/freemium motion
- Direct intent signals (demo request, pricing inquiry) — weight far above passive engagement

### Combining them
Use a simple 2x2 rather than a single score for routing decisions:
- **High fit + high engagement** → route to sales/high-touch immediately
- **High fit + low engagement** → nurture, don't route yet; this is where drip sequences do the most work
- **Low fit + high engagement** → still automate (they're getting value from something), but don't spend sales time here
- **Low fit + low engagement** → lowest priority; minimal-frequency nurture or suppress

### Decay
Set an explicit decay rule (e.g. engagement score drops by X% per Y days of inactivity). Without decay, a lead who was highly engaged three months ago and has since gone silent still looks "hot," which misleads whoever acts on the score.

### Calibration against outcomes
A scoring model set once at launch and never revisited drifts out of sync with reality. Periodically check score weights against actual closed-won/closed-lost outcomes: if a firmographic trait or source channel that scores as "high fit" keeps showing up in closed-lost deals, its weight is wrong and should come down; if a trait scored low keeps closing, it should go up. This closed-loop calibration is what keeps a scoring model predictive instead of just plausible-looking — do it on a fixed cadence (e.g. quarterly) rather than only when someone notices a problem.

---

## 3. Common Mistakes

- **Scoring on ease of measurement, not on predictive value.** Email opens are easy to track and a weak signal; pricing-page visits are harder to instrument in some stacks and a strong one. Weight by predictive value, not by what's already in the dashboard.
- **One list, one segment forever.** Contacts should move between segments as behavior changes — a static segment assigned at signup and never revisited stops reflecting reality within weeks.
- **Sales-only or marketing-only ownership of the score.** Both should agree on what "sales-ready" means, or handoffs will keep breaking — marketing hands off leads sales considers premature, or sales never sees the ones that were actually ready.
- **Too many segments to act on.** If a segmentation scheme produces 40 micro-segments but only 3 different automation treatments exist, collapse it back down — segmentation should map to a real difference in what gets sent or who acts.
