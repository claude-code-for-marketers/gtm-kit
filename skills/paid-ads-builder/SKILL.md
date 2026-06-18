---
name: paid-ads-builder
description: Generate paid advertising campaign artifacts for Newsletter Radar from a campaign goal, persona, and landing page. Use when Codex is asked to create Google Ads, Google Ads Editor CSV uploads, responsive search ad variants, LinkedIn ad copy, paid social image prompts, ad QA, campaign-specific ad briefs, or System Build 3 ad automation outputs using the GTM Kit context.
---

# Skill: Paid Ads Builder

**Duration:** 30-60 minutes per campaign
**Output:** `outputs/ads/YYYY-MM-DD-[campaign-slug]/`

---

## Quick Start

```
Read skills/paid-ads-builder/SKILL.md.
Build a paid ads campaign for [campaign goal].
Target [persona].
Use landing page [URL].
```

The first version creates Google Ads Editor template CSV files for human upload. The LinkedIn extension
creates ad copy, image prompts, and generated PNG assets. Never push directly to an ad account from this skill.

---

## Purpose

Turn Newsletter Radar positioning into reviewable paid-ad assets that can be uploaded, checked, and
improved. This skill is not just ad copy generation. It creates a campaign brief, constrained platform
assets, Google template CSV files, creative prompts, and QA notes tied to the GTM repo.

Use this workflow to teach and run System Build 3:

```text
campaign goal + persona + landing page
-> GTM context
-> Google Search ad variants
-> Google Ads Editor template CSV files
-> LinkedIn copy + generated images
-> QA against claims, character limits, and audience fit
```

---

## Required Context

Read these files before creating ads:

- `context/profile.md`
- `context/icp-definition.md`
- `context/positioning.md`
- `context/sponsorship-decision-framework.md`
- `context/personas/head-of-growth.md`
- `context/personas/founder-marketing-lead.md`

Use `context/competitor-radar.md` only if the campaign is explicitly about competitor footprints,
comparison, category whitespace, or objections.

Use `../newsletter-radar-site/app/page.tsx` or another supplied landing page path/URL as source
material when the campaign sends traffic to the site.

---

## Inputs

Required:

- Campaign goal
- Target persona
- Landing page URL

Optional:

- Campaign name
- Budget
- Geography
- Keyword themes
- Competitor angle
- CTA

If optional inputs are absent, default to:

- Campaign name: derived from the goal
- Persona: Head of Growth / Performance Marketing
- Geography: United States
- Campaign status: `Paused`
- Ad group status: `Paused`
- Ad status: `Paused`
- CTA: request access or run a sample lookup
- Landing page: `https://newsletterradar.com`
- Networks: `Google Search`
- Language: `en`

Do not invent budgets, customer logos, conversion metrics, trial offers, or coverage guarantees.

---

## Messaging Rules

Use Newsletter Radar's approved story:

- Newsletter Radar is the newsletter advertising intelligence platform.
- It helps advertisers see where companies advertise across newsletters and who advertises on any newsletter.
- Retention and tenure reveal which placements are worth considering.
- The product supports planning decisions; it does not measure conversions.

Allowed angles:

- Competitor footprint visibility
- Newsletter sponsorship planning
- Retention and repeat-sponsor proof
- Avoiding trial-and-error media buying
- Evidence-based shortlist creation
- Category whitespace

Avoid:

- "Free trial", "free tier", or "freemium"
- Direct ROI, conversion-rate, or attribution claims
- Complete-coverage claims
- Lead-gen, prospecting, publisher sales, or "sponsor database" framing
- Generic newsletter-ad trend copy
- Vague hype such as best, leading, ultimate, groundbreaking, robust, or game-changing

---

## Process

### Step 1: Build The Ad Brief

Define:

- Campaign name
- Date
- Campaign goal
- Target persona
- Audience stage
- Landing page
- CTA
- Geography
- Keyword themes
- Core angle
- Claim boundaries
- Success metric to review later

Choose 3-5 distinct angles before writing copy. Good default angles for Newsletter Radar:

| Angle | Use When |
|---|---|
| Competitor footprint | The buyer wants to know where rivals are spending |
| Retention proof | The buyer needs evidence before sponsoring newsletters |
| Budget protection | The buyer wants to avoid bad placements |
| Channel planning | The buyer is adding newsletters to a paid media mix |
| Category whitespace | The buyer wants untapped newsletter opportunities |

### Step 2: Create Google Search Assets

Create one Google Search campaign with 1-3 ad groups. Each ad group should have:

- 8-15 RSA headlines
- 3-4 RSA descriptions
- 5-15 keywords
- 3-8 negative keywords when useful
- Display paths
- Final URL with UTM parameters

Character limits:

- Headline: 30 characters max
- Description: 90 characters max
- Path 1: 15 characters max
- Path 2: 15 characters max

RSA mix:

- At least 2 keyword/intent headlines
- At least 2 benefit headlines
- At least 2 CTA headlines
- At least 1 brand headline
- At least 1 retention/thesis headline

Every headline must make sense independently because Google may combine assets in any order.

### Step 3: Create Google Ads Editor Template CSVs

Save Google upload artifacts to:

```text
outputs/ads/YYYY-MM-DD-[campaign-slug]/google/
├── campaign.csv
├── ad_group.csv
├── responsive_search_ad.csv
├── keyword.csv
└── ad_group_negative_keyword.csv
```

Target Google Ads Editor template CSV import, not live Google Ads API mutation. Do not create one
combined CSV. Google supplied separate templates for campaign, ad group, responsive search ad, keyword,
and ad group negative keyword uploads, and the output must match those templates.

Use these exact header orders.

`campaign.csv`:

```csv
Row Type,Action,Campaign status,Campaign ID,Campaign,Campaign type,Networks,Budget,Delivery method,Budget type,Bid strategy type,Bid strategy,Campaign start date,Campaign end date,Language,Location,Exclusion,Devices,Label,Target CPA,Target ROAS,Display URL option,Website description,Target Impression Share,Max CPC Bid Limit for Target IS,Location Goal for Target IS,Tracking template,Final URL suffix,Custom parameter,Inventory type,Campaign subtype,Video ad formats,EU political ads
```

`ad_group.csv`:

```csv
Row Type,Action,Ad group status,Campaign ID,Campaign,Ad group ID,Ad group,Ad group type,Ad rotation,Default max. CPC,CPC%,Max. CPM,Max. CPV,Target CPA,Target CPM,TrueView target CPV,Label,Tracking template,Final URL suffix,Custom parameter,Target ROAS
```

`responsive_search_ad.csv`:

```csv
# Assets can be shown in any order, so make sure that they make sense individually or in combination, and don't violate our policies or local law.
# IMPORTANT: For each responsive search ad, provide at least 5 distinct headlines that do not repeat the same or similar phrases. Providing redundant headlines will restrict our ability to generate combinations.
Row Type,Action,Ad status,Campaign ID,Campaign,Ad group ID,Ad group,Ad ID,Ad type,Label,Headline 1,Headline 2,Headline 3,Headline 4,Headline 5,Headline 6,Headline 7,Headline 8,Headline 9,Headline 10,Headline 11,Headline 12,Headline 13,Headline 14,Headline 15,Description 1,Description 2,Description 3,Description 4,Headline 1 position,Headline 2 position,Headline 3 position,Headline 4 position,Headline 5 position,Headline 6 position,Headline 7 position,Headline 8 position,Headline 9 position,Headline 10 position,Headline 11 position,Headline 12 position,Headline 13 position,Headline 14 position,Headline 15 position,Description 1 position,Description 2 position,Description 3 position,Description 4 position,Path 1,Path 2,Final URL,Mobile final URL,Tracking template,Final URL suffix,Custom parameter
```

`keyword.csv`:

```csv
Row Type,Action,Keyword status,Campaign ID,Campaign,Ad group ID,Ad group,Keyword ID,Keyword,Type,Label,Default max. CPC,Max. CPV,Final URL,Mobile final URL,Final URL suffix,Tracking template,Custom parameter
```

`ad_group_negative_keyword.csv`:

```csv
Row Type,Action,Keyword status,Level,Campaign ID,Campaign,Ad group ID,Ad group,Keyword ID,Negative keyword,Type
```

CSV rules:

- Use `Action` = `Add` for new rows.
- Keep campaign, ad group, keyword, and ad statuses `Paused` unless the user explicitly asks otherwise.
- Use `Row Type` values from the templates: `Campaign`, `Ad group`, `Ad`, `Keyword`, `Negative keyword`.
- Use `Campaign type` = `Search`, `Networks` = `Google search`, `Budget type` = `Daily`, and `EU political ads` = `No` for basic Search campaigns.
- Use `Ad type` = `Responsive search ad`.
- Use keyword match types exactly as the template expects: `Exact match`, `Phrase match`, or `Broad match`.
- Use negative keyword `Level` = `Ad group` unless the user asks for campaign-level negatives.
- Leave ID fields blank for create rows.
- Leave fields blank when they do not apply to that row.
- Put the ad copy only in `responsive_search_ad.csv`.
- Put keyword targets only in `keyword.csv`.
- Put negative keywords only in `ad_group_negative_keyword.csv`.
- Use UTM parameters in final URLs or final URL suffixes: `utm_source=google&utm_medium=paid_search&utm_campaign=[slug]&utm_content=[ad-group-slug]`.

### Step 4: Create LinkedIn Ads

Save LinkedIn copy to:

```text
outputs/ads/YYYY-MM-DD-[campaign-slug]/linkedin/linkedin-ads.md
```

Create 3-5 single-image ad variants. Each variant should include:

- Angle
- Intro text
- Headline
- Description
- CTA
- Landing page URL
- Image concept
- Image prompt

Default LinkedIn copy limits:

- Intro text: 150 characters recommended, 600 max
- Headline: 70 characters recommended, 200 max
- Description: 100 characters recommended, 300 max

Stay near recommended limits unless the user explicitly asks for longer copy.

### Step 5: Generate LinkedIn Images

Save prompts to:

```text
outputs/ads/YYYY-MM-DD-[campaign-slug]/linkedin/image-prompts.md
```

Generate PNG image assets directly through the agent's available image-generation capability. Do not
require SVG source files, rasterization scripts, image API keys, or third-party creative tools for the
core workflow.

Generate at least:

- One square variant
- One landscape variant

Image guidance:

- Use visual metaphors tied to sponsorship intelligence, radar, competitive footprints, newsletters,
  media planning, or retention over time.
- Keep text minimal or absent in the image itself; put copy in the ad fields.
- Make visuals polished enough for a B2B paid social test, not a decorative blog illustration.
- Avoid fake UI screenshots unless clearly stylized and not presented as a real product screen.
- Avoid logos, trademarks, customer names, or unverifiable metrics.

If image generation is unavailable in the current environment, still write `image-prompts.md` and mark
the PNG files as blocked in `qa.md`.

### Step 6: Run QA

Save QA notes to:

```text
outputs/ads/YYYY-MM-DD-[campaign-slug]/qa.md
```

Before finalizing, check:

- [ ] Campaign targets buy-side advertisers, not newsletter publishers.
- [ ] Copy does not frame Newsletter Radar as a lead-gen or prospecting database.
- [ ] Copy does not claim direct ROI, conversions, or attribution.
- [ ] Copy does not imply a free tier or free trial.
- [ ] Copy does not claim complete newsletter coverage.
- [ ] Google headlines are 30 characters or fewer.
- [ ] Google descriptions are 90 characters or fewer.
- [ ] Google paths are 15 characters or fewer.
- [ ] Google output is five separate template-matched CSV files, not one combined CSV.
- [ ] CSV files use the exact header orders for campaign, ad group, responsive search ad, keyword, and ad group negative keyword templates.
- [ ] Responsive search ad copy is in `google/responsive_search_ad.csv`.
- [ ] Keywords are in `google/keyword.csv`.
- [ ] Negative keywords are in `google/ad_group_negative_keyword.csv`.
- [ ] Final URLs include UTM parameters.
- [ ] LinkedIn copy stays within stated limits.
- [ ] Image prompts avoid fake proof, unverifiable metrics, and trademark issues.
- [ ] Generated PNG assets exist and are readable, or image generation is clearly marked blocked.
- [ ] All ads point to one clear CTA.

If any item fails, revise before marking the output ready.

---

## Output Structure

Create this folder structure:

```text
outputs/ads/YYYY-MM-DD-[campaign-slug]/
├── brief.md
├── qa.md
├── google/
│   ├── campaign.csv
│   ├── ad_group.csv
│   ├── responsive_search_ad.csv
│   ├── keyword.csv
│   └── ad_group_negative_keyword.csv
└── linkedin/
    ├── linkedin-ads.md
    ├── image-prompts.md
    └── images/
        ├── [campaign-slug]-square.png
        └── [campaign-slug]-landscape.png
```

Use this brief structure:

```markdown
# Paid Ads Brief: [Campaign Name]
Date: [YYYY-MM-DD]
Status: Draft ready for review

## Inputs
[campaign goal, persona, landing page, CTA, geography, budget if supplied]

## Audience
[persona and buying situation]

## Angles
[3-5 angles with rationale]

## Google Search Plan
[campaign, ad groups, keyword themes, negatives, URL plan]

## LinkedIn Plan
[variants and image concepts]

## Claim Boundaries
[what the ads must not say]
```

---

## You Do Extensions

Offer students two tracks after the core build.

### Track A: Campaign Landing Page

Recommended for most students. Create a campaign-specific landing page in `../newsletter-radar-site`,
for example:

```text
app/ads/newsletter-sponsorship-intelligence/page.tsx
```

Requirements:

- Reuse the same campaign angle and CTA as the generated ads.
- Keep the page focused on one offer.
- Add a route-specific headline, proof/logic section, and request-access CTA.
- Run the site lint/build checks.
- Update `qa.md` with the landing page route and message match notes.

### Track B: Third-Party Image Generation API

Advanced. Wire in a third-party image generation API behind a server-side script or route.

Requirements:

- Keep API keys in `.env.local`.
- Document required variables in `.env.example`.
- Do not commit secrets, generated raw API responses, or provider-specific account data.
- Fail clearly when the key is missing.
- Save final PNGs under the same `linkedin/images/` path.
- Update `qa.md` with the provider used and the safety checks performed.

---

## Platform References

Google Ads Editor CSV import:

- Prepare a CSV file: `https://support.google.com/google-ads/editor/answer/56368`
- CSV file columns: `https://support.google.com/google-ads/editor/answer/57747`

Use current official platform docs for LinkedIn image dimensions before launching live ads.
