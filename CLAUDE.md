# CLAUDE.md

This file is the persistent context layer for Newsletter Radar's GTM repository. Claude Code reads it
automatically at the start of every session. The full context lives in `context/` — this is the summary
layer with pointers to deeper files.

**Status: pre-launch (early access).** Marketing site lives in the sibling repo `../newsletter-radar-site`.
A few founder-specific fields are still marked `[inferred]`/`[TBD]`.

---

## Company

**Newsletter Radar** helps brands and advertisers see where their competitors advertise in newsletters —
and get a ranked plan of where to spend next. Newsletter sponsorship intelligence for the **buy side**,
not for publishers selling ad slots. *"Every newsletter your competitor sponsors, in one query."*

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

**We win when:** The buyer is an advertiser who wants competitor footprint + a placement plan + fresh data.
**We lose when:** They only need raw "who's spending" signal, the newsletter they care about isn't covered, or they're actually a publisher.

vs. **SponsorSignals** (⚠ closest competitor — already serves advertisers): we're buy-side *only* + ship a ranked placement plan, not just intelligence; watch them weekly
vs. Who Sponsors Stuff: Buy-side workflow + freshness vs. a historical seller's directory
vs. SponsorGap: A media *plan*, not a real-time lead list (and we don't do free search)
vs. Appeared.in: Explicit buy-side benchmarking (publisher-framed today)
vs. Paved Radar: Neutral advertiser tool, not a publisher lead feed tied to a marketplace

> Don't say "the only buy-side tool" — SponsorSignals also serves advertisers. Lead with focus + the plan.

**Voice:** Direct, concrete, buy-side, lightly technical (terminal/CLI brand). Lead with specific competitor
footprints, never generic "newsletter ads are hot." Never sound like a prospecting/lead-gen tool.

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
- [ ] Confirm remaining `[TBD]` fields (HQ, founder/team, ACV)
- [ ] Validate launch pricing (Pro/Team) with the first design partners
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
