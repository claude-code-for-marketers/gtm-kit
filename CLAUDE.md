# CLAUDE.md

This file is the persistent context layer for Newsletter Radar's GTM repository. Claude Code reads it
automatically at the start of every session. The full context lives in `context/` — this is the summary
layer with pointers to deeper files.

**Status: pre-launch (early access).** Marketing site lives in the sibling repo `../newsletter-radar-site`.
A few founder-specific fields are still marked `[inferred]`/`[TBD]`.

---

## Company

**Newsletter Radar** is the **newsletter advertising intelligence platform**: see where any company
advertises across newsletters, who advertises on any newsletter, and — by tracking how long advertisers
keep sponsoring — which newsletters are actually worth buying. Both directions; built for advertisers.
Thesis: **retention reveals what works — follow the repeat money** (`context/sponsorship-decision-framework.md`).

Stage: pre-launch / early access | HQ: `[TBD]` | Website: newsletterradar.com | Contact: hello@newsletterradar.com
GTM motion: early-access / design partners now (one vertical at a time) → self-serve **paid** subscription at GA
Pricing: paid only, **no free tier / no freemium** (Pro ~$99/mo annual 1 seat, Team ~$299/mo annual up to 10 seats, Agency custom)
Data: our own crawl, **1,000+ newsletters** at launch across tech, AI, business, finance (+ adjacent)
Scope: **pure intelligence** — no contacts, no outreach (deliberately not a lead list)

---

## ICP

Full definition: `context/icp-definition.md`

**Who we sell to:** Funded B2B SaaS, AI/dev-tools, fintech, and business/productivity brands (20–500
employees) that run paid acquisition and advertise (or want to) in tech/AI/business/finance newsletters —
i.e. the verticals we crawl. The buy side.

**Tier 1:** Already advertising in newsletters (detected in our own index) + has a growth function + a competitor is also active
**Tier 2:** Heavy on other paid channels, recently funded, in a vertical we cover
**Tier 3:** 20+ employees, marketing function, in a covered vertical, some paid motion

**Never target:**
- Newsletter publishers / creators — that's the incumbents' market; we're buy-side only
- Companies with no paid-acquisition motion — nothing to plan
- Brands whose audience isn't in tech/AI/business/finance newsletters (outside our coverage)

---

## Personas

Full profiles: `context/personas/`

| Role | Title(s) | Primary concern | Best channel |
|------|----------|----------------|-------------|
| Champion + buyer | Head of Growth / Performance Marketing | Rising CAC; finding channels that work, with data to defend spend | Email + LinkedIn + communities |
| Buyer (small team) | Founder / Solo Marketing Lead | Fast, cheap channel wins without trial-and-error | Email, DMs, founder communities |

---

## Positioning

Full document: `context/positioning.md`

**Three pillars:** (1) bidirectional visibility — who advertises where, both directions; (2) retention &
tenure intelligence — who keeps coming back; (3) the buy decision — fit × proof → a ranked shortlist.

**We win when:** The advertiser wants evidence (retention/tenure) and broad coverage to decide where to spend.
**We lose when:** They just want a name list, a narrow panel is enough, or they're a publisher selling slots.

**Lead with:** the platform + the retention thesis ("subscriber count tells you reach; retention tells you
whether it works"). **Don't make the pitch about our competitors** — battlecards in `competitor-radar.md`
are for live-deal objections only. Real edges: coverage breadth (1,000+ crawl) + retention-based recommendation.

**Voice:** Direct, concrete, evidence-led, lightly technical (terminal/CLI brand). Lead with retention proof
and specific footprints, never generic "newsletter ads are hot." Never sound like a prospecting/lead-gen tool.

---

## Signals

Full library: `context/signal-library.md`

**Act immediately (Tier 1):**
1. Active newsletter advertiser detected in our own index — they're spending, no plan (our strongest, proprietary signal)
2. Direct competitor starts/scales newsletter advertising — peak benchmarking demand
3. Hired a Head of Growth / Performance Marketing — new channel mandate + budget

**Add to sequence (Tier 2):**
1. Recent funding round (last 12 months)
2. Scaling other paid channels (Meta/Google/podcast)

---

## Stack

Signal source: **our own sponsorship index (proprietary crawl)** + Crunchbase (funding) + LinkedIn/Trigify (job changes)
CRM: `[TBD]` | Enrichment: `[Clay/Apollo TBD]` | Outbound: `[Smartlead/Instantly TBD]` | Export: CSV / Google Sheets

---

## Team

| Name | Role | Owns |
|------|------|------|
| `[TBD]` | Founder | Product, the crawl/index, positioning, first sales |

---

## This Week

- [ ] Turn early-access requests (via `../newsletter-radar-site`) into design-partner advertisers
- [ ] **Sharpen differentiation vs. SponsorSignals** — lead on coverage breadth (1,000+ crawl vs their 170) + the placement plan, since "buy-side" no longer differentiates
- [ ] **Rethink pricing vs. their $100 7-day pass** — consider adding a cheap one-time pass as our entry rung (not a free tier)
- [ ] **Treat MCP/Claude access as launch table stakes** — they've shipped it
- [ ] Confirm remaining `[TBD]` fields (HQ, founder/team, ACV)
- [ ] Prioritize crawl coverage by the verticals requesters ask for

---

## Quick Commands

```
# Research an account (an advertiser/brand)
Read skills/account-research/SKILL.md and research [company.com]

# Score a list of brands against our ICP
Read skills/icp-scoring/SKILL.md and score these accounts: [paste list]

# Build a campaign from a signal
Read skills/signal-to-sequence/SKILL.md — build a Tier 2 campaign for
accounts that triggered [signal name], targeting [persona title]
```
