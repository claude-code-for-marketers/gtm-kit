# The Newsletter Radar Method — How to Decide Which Newsletters to Sponsor

*The analytical thesis the product encodes and the narrative the GTM leans on. This is both the buyer-facing
decision methodology and the spec for the metrics Newsletter Radar computes.*

Last updated: 2026-06-15

---

## The Problem With How Advertisers Pick Newsletters Today

The usual inputs are subscriber count, open rate, and a media kit — all **seller-reported and
unverifiable**, and none of which tell you whether the audience actually *converts* for a brand like yours.
So advertisers test by spending real money, and learn the hard way.

## The Insight: Retention Is the ROI Signal

**Advertisers don't keep paying for placements that don't work.** What an advertiser *keeps doing with its
budget* is the most honest signal available — far better than anything a publisher reports about itself.

So instead of asking "how big is this newsletter?", ask **"do advertisers like me keep coming back here?"**
We can't see their conversion rates — but we can see that they renewed for 14 straight months, which tells
you more than any media kit. **Follow the repeat money.**

---

## The Three Questions for Any Candidate Newsletter

### 1. Fit — "Do companies like me advertise here?"
The *type mix* of sponsors reveals who the audience converts for. A newsletter sponsored mostly by
devtools/infra companies is telling you something if you sell devtools.

**Look at:** sponsor breakdown by vertical, business model, company size, funding stage. Density of *your*
category is the fit signal.

### 2. Proof — "Do they keep advertising here?"  ← the decisive one
Tenure and repeat behavior are the closest thing to a public ROI number.

- **Long tenure / high repeat** → the audience converts; smart money keeps paying. **Buy signal.**
- **One-and-done churn** → people tried it and left. **Caution** — weak audience fit or mispriced.
- Always filter this to companies *like you*. "Devtools sponsors here run 9+ months on average" beats a
  blended average across unrelated verticals.

### 3. Position — "Where are my competitors, and where's the whitespace?"
- Competitor present **and** long-tenured → validated channel you're absent from. **Catch up.**
- Competitor present but **churned quickly** → they tried it; it didn't hold. **Learn from the exit.**
- No one in your category yet **but** strong fit + retention from lookalikes → **whitespace; move first.**

---

## The Metrics (spec for what the product computes)

From crawl data — for each `advertiser × newsletter`: first-seen date, last-seen date, placement count,
cadence, and current status (new / active / scaling / reactivated / cooling / churned).

### Per newsletter — the "should I sponsor this?" view
| Metric | Definition | Why it matters |
|--------|-----------|----------------|
| **Sponsor-type mix** | % of sponsors by vertical / model / size / stage | Audience fit for *your* category |
| **Repeat rate** | % of sponsors with ≥2 placements | Did anyone come back at all? |
| **Median sponsor tenure** | Median (last − first) across sponsors | How long the typical advertiser commits |
| **Long-tenure share** | % of sponsors running 6m+ / 12m+ | Density of "anchor" advertisers (strongest signal) |
| **Retention curve** | Of sponsors first seen in month M, % still running at M+3 / +6 / +12 | Does value persist or decay? |
| **Anchor advertisers** | Top sponsors by tenure + placement count | The brands that clearly see ROI here |
| **Churn signal** | % of sponsors now cooled/gone; median time-to-churn | How fast people give up |

### Per advertiser — the "where do my competitors advertise?" view
| Metric | Definition | Why it matters |
|--------|-----------|----------------|
| **Newsletter footprint** | All newsletters they sponsor, with first/last/count/status | Where the budget goes |
| **Tenure per newsletter** | How long they've run in each | Where they're *committed* vs. testing |
| **Scaling vs. churned** | Which placements they grew vs. dropped | Reveals what's working *for them* |

### The recommendation — personalized "worth-it" score
For a given advertiser: **fit** (density of sponsors in your category) × **proof** (retention/tenure of
those category sponsors), optionally weighted by **competitor presence**. Output: a ranked shortlist of
newsletters to sponsor next, plus the whitespace your category hasn't claimed. *(Product surface:
`radar recommend` / the placement plan.)*

---

## Worked Example (illustrative)

> A seed-stage devtools company asks: *where should we run?*
> - **TLDR Dev** — 18 devtools sponsors; median tenure 7 months; 6 anchors running 12m+; two direct
>   competitors active and growing. → **Strong buy** (fit + proof + competitor validation).
> - **A large general-tech newsletter** — huge list, but devtools sponsors churn in ~6 weeks and repeat
>   rate is 14%. → **Skip** (audience doesn't convert for this category, regardless of size).
> - **A niche infra newsletter** — small, but every devtools sponsor that starts is still running 9+
>   months later, and none of your competitors are there yet. → **Whitespace bet.**

The size-ranked media-kit view would have picked the big general-tech newsletter. The retention view
picks the two that actually work.

---

## How This Shows Up in GTM

- **Outbound hook:** "We can show you which newsletters your competitors *keep* sponsoring — the ones
  they renew month after month — and which ones they quietly dropped."
- **Demo moment:** pull a prospect's category, sort newsletters by long-tenure share, reveal the anchors.
- **The line that lands:** "Subscriber count tells you reach. Retention tells you whether it works."
