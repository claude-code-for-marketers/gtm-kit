# Signal Library — Newsletter Radar

*Signals are observable events that predict an advertiser is ready to buy newsletter-ad intelligence.
This library is the source of truth for all signal-based outreach. Every campaign in this repo traces
back to at least one signal here.*

Last updated: 2026-06-12 · Status: **pre-launch** · All point values `[inferred]` until we have conversion data.

> Our unfair advantage: **our own product data is a signal source.** We can see which brands are
> advertising in newsletters before they tell us — that's the strongest buying signal we have.

---

## Signal Scoring Model

| Score | Tier | Action |
|-------|------|--------|
| 80–100 | Hot | Founder/AE alert within 2 hours. Research brief within 24 hours. Outreach within 48 hours. |
| 60–79 | Warm | Trigger Tier 2 sequence within 48 hours. |
| 40–59 | Cool | Add to Tier 3 automated sequence. |
| 0–39 | Cold | Log and monitor. No outreach. |

---

## Tier 1 Signals — Act Immediately

### Signal: Active newsletter advertiser detected in our index
**Category:** Behavioral / Intent
**Points:** 40 `[inferred]`
**Source:** Newsletter Radar's own sponsorship index (proprietary)
**Refresh cadence:** Real-time / daily

**Definition:** A target company is detected sponsoring 2+ newsletters (or running repeat placements) in our index.

**Why it predicts fit:** They're already spending real money on the channel — they have the budget and
the pain (planning, benchmarking, measuring it) that Newsletter Radar solves. No education needed.

**Detection method:**
```
Query our index for brands with >=2 distinct newsletter placements in trailing 90 days.
Cross-reference against CRM to exclude existing users.
```

**Message hook:** "Noticed you're running in [Newsletter A] and [Newsletter B] — want to see where the
rest of your category is advertising and where the gaps are?"

---

### Signal: Direct competitor starts or scales newsletter advertising
**Category:** Intent / Competitive
**Points:** 35 `[inferred]`
**Source:** Newsletter Radar's own index (competitor footprint detection)
**Refresh cadence:** Daily

**Definition:** A known competitor of the target appears as a *new* newsletter sponsor, or materially
increases placement frequency.

**Why it predicts fit:** Advertisers benchmark obsessively. A competitor showing up in newsletters is
the exact trigger that makes a brand want to see "where are they, and where should we be."

**Detection method:**
```
Maintain competitor sets by vertical. Diff weekly index snapshots for new/expanded sponsors.
When a competitor of an ICP account fires, flag the account.
```

**Message hook:** "[Competitor] just started advertising across [N] newsletters in your space — here's the full footprint."

---

### Signal: Hired a growth / performance-marketing leader
**Category:** Organizational
**Points:** 30 `[inferred]`
**Source:** LinkedIn / job-change alerts (Trigify or similar)
**Refresh cadence:** Daily

**Definition:** Target hires a Head of Growth, Performance Marketing, Paid Media, or Demand Gen leader.

**Why it predicts fit:** New channel-owners arrive with a mandate to diversify acquisition and a budget
to test. Newsletters are a natural next channel — and they need data to plan it.

**Detection method:**
```
Monitor job-change feeds for ICP accounts: titles matching
(Head|Director|VP) of (Growth|Performance Marketing|Paid Media|Demand Gen).
```

**Message hook:** "Congrats on the new role — if newsletters are on your channel roadmap, here's where your competitors already spend."

---

## Tier 2 Signals — Add to Active Sequences

### Signal: Recent funding round
**Category:** Firmographic / Intent
**Points:** 20 `[inferred]`
**Source:** Crunchbase / funding news
**Refresh cadence:** Weekly

**Definition:** Target raised a seed–Series C round in the last 12 months.

**Why it predicts fit:** Fresh capital → new-channel experimentation and bigger acquisition budgets.
SponsorGap explicitly surfaces this for a reason.

---

### Signal: Scaling other paid channels
**Category:** Behavioral
**Points:** 15 `[inferred]`
**Source:** Ad-library / SimilarWeb-style intelligence `[inferred — confirm tooling]`
**Refresh cadence:** Weekly

**Definition:** Growing presence in Meta/Google/podcast ads, or public hiring/comments about diversifying paid acquisition.

**Why it predicts fit:** Advertisers maxing out saturated channels look to newsletters next — and want to plan it with data.

---

## Tier 3 Signals — Monitor

- New product launch or market expansion (+5) — new launch → new acquisition push
- Job posting mentioning "newsletter," "media buying," or "sponsorships" (+5) — explicit channel intent
- Engaging newsletter-ad communities / content (+5) — researching the channel
- Listed as a sponsor on a single newsletter (+5) — early/experimental spend (becomes Tier 1 at 2+)

---

## Signal Combinations

| Combination | Combined Score | What it means | Action |
|-------------|----------------|---------------|--------|
| Active advertiser + competitor scaling | +15 bonus | Spending *and* under competitive pressure — peak intent | Hot. Founder-led, lead with side-by-side footprint |
| New growth hire + recent funding | +10 bonus | New owner with fresh budget and a mandate | Warm. Sequence the new hire directly |
| Scaling paid channels + competitor advertising | +10 bonus | Ready to diversify and has a benchmark to chase | Warm. Lead with the gap analysis |

---

## Suppression Rules

- Account is an existing customer → suppress all outreach
- Account is a newsletter publisher (anti-ICP) → suppress; route to a future publisher list
- Contact has unsubscribed in last 90 days → suppress email
- Active opportunity in CRM → suppress automated sequences

---

## Signal Decay

| Signal age | Score multiplier |
|------------|-----------------|
| 0–30 days | 100% |
| 31–60 days | 75% |
| 61–90 days | 50% |
| 91–180 days | 25% |
| 180+ days | 0% (signal expires) |

Run a weekly batch to recalculate scores with decay applied. Accounts that drop below tier thresholds
are downgraded automatically. Note: the "active advertiser" signal should refresh continuously — if a
brand stops appearing in the index, decay it faster.

---

## Signal Performance Log

*Empty — pre-launch. Update after every campaign.*

| Signal | Outreach sent | Replies | Meetings | Pipeline | Notes |
|--------|--------------|---------|----------|----------|-------|
| Active advertiser detected | | | | | |
| Competitor scaling | | | | | |
| New growth hire | | | | | |
| Recent funding | | | | | |
| Scaling paid channels | | | | | |
