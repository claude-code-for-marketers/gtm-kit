# Company Profile — Newsletter Radar

*High-level context about the company, product, and GTM motion. This is the first thing Claude reads when working on anything in this repo.*

Last updated: 2026-06-15 · Status: **pre-launch (early access)** · Sibling repo: `../newsletter-radar-site` (Next.js marketing site).

---

## The Company

**Name:** Newsletter Radar
**Founded:** 2026
**HQ:** `[TBD]`
**Website:** newsletterradar.com (pre-launch — early-access landing page live)
**Contact:** hello@newsletterradar.com

**What we do:**
Newsletter Radar is newsletter sponsorship intelligence built for the **buy side** — the brands and
advertisers spending money on newsletter ads, not the publishers selling slots. Enter a company and see
every newsletter it sponsors (recency, frequency, and the actual creative); benchmark share-of-voice
across a competitive set; and get a ranked plan of which newsletters to sponsor next.

**What makes us different:**
Most tools in this category — Who Sponsors Stuff, SponsorGap, Appeared.in, Paved Radar — are built and
marketed for newsletter publishers prospecting for advertisers to pitch. Newsletter Radar points the
same data the other way: at the brand deciding where to spend. Tagline: *"Every newsletter your
competitor sponsors, in one query."*

> **Caveat (important):** **SponsorSignals** already ships a full buy-side product in our exact verticals,
> so "buy-side" is **not** our differentiator. Our real edges are **coverage breadth** (1,000+ automated
> crawl vs. their 170 manually verified) and the **ranked placement plan/gap analysis**. The marketing
> site's "every other tool sells to publishers" line is an overclaim worth revisiting. See
> `context/competitor-radar.md` (SponsorSignals card) for the full, frank picture.

---

## Product

**Core product:** Newsletter Radar — an advertiser-facing search + analytics tool over a continuously
crawled index of newsletter sponsorships. Terminal/CLI-inspired brand (`radar footprint`, `radar gaps`).

**Key capabilities:**
- **Competitor footprint** — enter a company, get every newsletter it sponsors, ranked by share-of-voice, with the actual ad creative
- **Placement plan** — given category, competitors, and budget, a ranked shortlist of newsletters to test next, with the gaps competitors own flagged
- **Freshness** — who *started* advertising recently and what's live this week, not a historical archive

**Scope (v1):** Pure intelligence. No contact data and no outreach tooling — deliberately not a lead
list. (Possible later expansion; out of scope for launch.)

**Pricing model:** Paid subscription, **no free tier and no freemium.** Top-of-funnel is a no-signup
*sample lookup* (marketing teaser, not a product tier) plus early-access onboarding.

> **Recommended launch pricing** *(proposal — validate with design partners):* annual-first SaaS.
> - **Pro** — $99/mo billed annually ($1,188/yr), or $129 month-to-month. 1 seat. Full index, reverse
>   lookup, competitor footprints, share-of-voice, freshness alerts, up to ~10 tracked competitors.
> - **Team** — $299/mo billed annually ($3,588/yr), or $349 monthly. **Up to 10 seats** (set to match
>   and undercut SponsorSignals' $5k/10-seat annual). Unlimited tracked competitors, share-of-voice
>   dashboards, exports, priority coverage requests.
> - **Agency** — from $799/mo, custom. Multiple client workspaces, more seats, API access (future).
>
> No free tier, so de-risk the first purchase with a **14-day money-back guarantee** (or a paid pilot
> for design partners) rather than a trial. Rationale: a saved bad placement or one found competitor
> gap pays for a year — anchor on value, keep entry friction low for the founder/solo-marketer persona.
>
> **Competitive benchmark — SponsorSignals (verified 2026-06-15):** value ladder of free teaser
> (search + demo dashboard, no account) → **$100 one-time / 7-day Validation Pass** → **$1,000 / 3-month
> Pilot** → **$5,000/yr, up-to-10-seat Annual**. Implications for us:
> - ⚠ **The $100 7-day pass is the real threat to our pricing.** It's positioned for "a startup marketer
>   deciding where to advertise this quarter" — exactly our buyer — at a fraction of our $99/mo. A one-time
>   looker buys their $100 pass, not our subscription. **Recommendation: add a cheap one-time/short pass**
>   (e.g. $79–$149 for 7–14 days) as our entry rung. It's *not* a free tier, so it's consistent with the
>   no-freemium rule, and it neutralizes their cheapest on-ramp. Revisit the subscription-only stance.
> - Team is 10 seats at $3,588/yr, which beats their $5k/10-seat annual on price — keep this.
> - ⚠ **MCP/Claude access is already shipped by them** (Pilot + Annual), not a future edge. Given our
>   CLI/terminal brand, treat MCP as **table stakes for launch**, not a roadmap nice-to-have.

**Integrations that matter for GTM:** CSV / Google Sheets export for media planning. `[Others TBD]`

---

## GTM Motion

**Primary motion (now):** Early-access, founder-led, onboarding **design-partner advertisers one
vertical at a time.** The site collects access requests ("tell us your category + one competitor to
look up first") so coverage can be prioritized per requester.

**Primary motion (at GA):** Self-serve paid subscription (no free tier) + sales-assist on Team/Agency
seats. Top-of-funnel hook = the no-signup sample lookup → request access / purchase.

**Typical deal flow:** Sample lookup → request access → design-partner onboarding (vertical prioritized) → paid subscription
**ACV range:** `[inferred]` ~$1.2k–$4k self-serve (Pro/Team annual); higher for Agency
**Sales cycle:** Short — self-serve / founder-led
**Expansion motion:** Seat expansion as more of an advertiser's marketing team adopts it; Agency multi-client plans

---

## Team

**GTM team size:** Founder-led, pre-launch.

| Name | Role | Owns |
|------|------|------|
| `[TBD]` | Founder | Product, the crawl/index, positioning, first sales |

---

## Current GTM Priorities

*Update monthly. Shapes how Claude prioritizes tasks.*

**This quarter's focus:**
1. Convert early-access requests into design-partner advertisers, vertical by vertical
2. Hold crawl coverage at 1,000+ newsletters across tech, AI, business, and finance — deep enough for credible competitor lookups
3. Validate launch pricing (Pro/Team) against design-partner willingness to pay

**Key campaigns active:** Early-access waitlist via the marketing site (`../newsletter-radar-site`)

**Blockers:** `[inferred]` Crawl coverage depth per vertical; converting "request access" interest into paying design partners

---

## Market Context

**Category:** Newsletter sponsor (ad) intelligence — re-pointed at the advertiser/buy side
**Market size:** `[inferred — TBD; tied to total newsletter ad spend, growing with the newsletter economy]`
**Key trends driving demand:**
- Newsletter advertising is now a real performance channel; brands need to plan it like paid social
- Advertisers expect competitor benchmarking (à la SimilarWeb / SensorTower) for every channel
- Incumbent data exists but is locked behind publisher-prospecting framing

**Primary competitors:** *(full battlecards in `context/competitor-radar.md`)*
| Competitor | Their strength | Our edge |
|------------|---------------|----------|
| **SponsorSignals** ⚠ | Fully shipped buy-side product, MCP/Claude access, our exact verticals (170 newsletters, manual) | **Coverage breadth (1,000+ automated crawl vs their 170)** + the ranked placement plan |
| Who Sponsors Stuff | Deepest historical archive + ad images | Buy-side framing, freshness |
| SponsorGap | Real-time spend signal | Advertiser workflow vs. lead list |
| Appeared.in | Rich brand profiles, modern UX | Competitor-footprint depth for buyers |
| Paved Radar | 15,000+ newsletter coverage | Neutral; not tied to a marketplace |

---

## Data & Coverage

- **Sourcing:** Our own crawl of newsletters (proprietary index) — not licensed/partner data.
- **Launch coverage:** 1,000+ newsletters.
- **Primary verticals:** tech, AI, business, finance (plus adjacent: crypto, and more — expanding by vertical on request).
- **Honesty stance (mirror the site):** coverage is finite for everyone; we show spend & presence, not conversions; it's a planning tool, not a lead list.

---

## Reference Customers

*None yet — pre-launch. Populate with design partners and first logos as they sign.*

| Customer | Industry | Why they bought | Can reference publicly? |
|----------|----------|----------------|------------------------|
| `[TBD]` | | | |
