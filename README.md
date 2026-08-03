# marketing-automation-skill

This repo hosts two Claude skills:

- [`marketing-automation/`](#marketing-automation) (root-level files) — a generic, tool-agnostic playbook for designing and running marketing automation.
- [`meiseki-growth-scout/`](meiseki-growth-scout/README.md) — a daily growth-intelligence and BD research workflow for Meiseki, a Business Strategy / Growth Intelligence / Business Transformation consultancy.

Each skill is self-contained in its own set of files — upload them separately as distinct Claude skills.

## marketing-automation

A Claude skill: a generic, tool-agnostic playbook for designing and running marketing automation — lifecycle stages, segmentation, lead scoring, nurture/drip sequences, campaign types, and automation logic (triggers, conditions, actions).

## What it covers

- **Lifecycle model** — awareness → nurture → conversion → retention/onboarding → advocacy
- **Automation logic** — triggers, conditions, actions, and the exit-condition mistakes that cause most broken sequences
- **Sequence design process** — a step-by-step method for building any nurture, onboarding, re-engagement, or win-back sequence
- **Segmentation & lead scoring** — fit vs. engagement axes, decay logic, common scoring mistakes
- **Campaign types reference** — welcome/onboarding, nurture/drip, abandonment, re-engagement, win-back, lifecycle/milestone, transactional-adjacent
- **Metrics & reporting** — what to measure per lifecycle stage, and how to report results credibly rather than as vanity metrics

This is intentionally platform-agnostic — the same strategy applies whether execution happens in HubSpot, Marketo, ActiveCampaign, Klaviyo, Customer.io, Braze, Zapier/Make, or a custom system.

### Files

- `SKILL.md` — the main playbook. Start here.
- `templates.md` — sequence structures and copy skeletons by campaign type (generic placeholders — fill in brand/product specifics before sending)
- `segmentation-scoring.md` — segmentation frameworks and lead scoring model design
- `metrics.md` — what to measure per lifecycle stage, benchmark ranges, and reporting discipline

### How to use

Before applying this to a specific product, establish (from the user or the conversation) what's in `SKILL.md` Section 1: what's being sold and how it's bought, what trigger data is actually available, and which platform (if any) will execute the automation.

Upload the four root-level files (`SKILL.md`, `templates.md`, `segmentation-scoring.md`, `metrics.md` — keep them together, flat, no subfolder) as a skill in Claude, or point Claude at this repo directly.

## meiseki-growth-scout

A Claude skill: daily growth-intelligence and BD research workflow for Meiseki. See [`meiseki-growth-scout/README.md`](meiseki-growth-scout/README.md) for details and usage.
