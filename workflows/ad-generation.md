# Workflow: Ad Generation

*How we turn a campaign goal into reviewable Google and LinkedIn ad artifacts.*

---

## Purpose

Paid ads should be constrained assets, not loose copy ideas. This workflow connects Newsletter Radar's
GTM context to upload-ready Google Search ads, LinkedIn ad variants, generated image assets, and QA.

The goal is a human-reviewed ad package:

```text
campaign goal + persona + landing page
-> ad brief
-> Google Ads Editor template CSVs
-> LinkedIn copy + generated PNGs
-> QA
-> human upload / launch decision
```

This workflow does not push directly to ad platforms.

---

## Phase 1: Campaign Definition

Define the campaign in writing before generating ads:

```markdown
Campaign goal: [early access / sample lookup / launch offer / competitor lookup]
Persona: [Head of Growth / Founder Marketing Lead]
Landing page: [URL]
CTA: [request access / run sample lookup]
Geography: [default US]
Budget: [optional]
Keyword themes: [optional]
Competitor angle: [yes/no; details]
```

Quality gate:

- [ ] The target is a buy-side advertiser.
- [ ] The campaign maps to a real Newsletter Radar use case.
- [ ] The landing page can support the promise in the ad.
- [ ] The CTA is one action.

---

## Phase 2: Run The Paid Ads Skill

Run:

```text
Read skills/paid-ads-builder/SKILL.md.
Build a paid ads campaign for [campaign goal].
Target [persona].
Use landing page [URL].
```

Expected outputs:

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

---

## Phase 3: Google Ads Review

Review the Google CSV files before importing into Google Ads Editor.

Check:

- [ ] The Google output uses five separate template-matched files: `campaign.csv`, `ad_group.csv`, `responsive_search_ad.csv`, `keyword.csv`, and `ad_group_negative_keyword.csv`.
- [ ] Each file uses the exact header order from the Google-provided template.
- [ ] Campaign, ad group, ad, and keywords are paused.
- [ ] Headlines are 30 characters or fewer.
- [ ] Descriptions are 90 characters or fewer.
- [ ] Path fields are 15 characters or fewer.
- [ ] Final URLs include UTM parameters.
- [ ] The keyword themes match the landing page and buyer intent.
- [ ] Negative keywords suppress publisher/sell-side searches where relevant.

Do not upload if the ad implies a free tier, conversion tracking, complete coverage, or publisher
lead-generation use.

---

## Phase 4: LinkedIn Review

Review `linkedin/linkedin-ads.md`, `linkedin/image-prompts.md`, and generated PNGs.

Check:

- [ ] Intro text, headline, and description fit stated LinkedIn limits.
- [ ] The visual concept matches the ad angle.
- [ ] The PNGs are readable and polished.
- [ ] The image avoids fake product screens, fake metrics, customer logos, and trademarked assets.
- [ ] Copy sounds professional and specific, not consumer hype.
- [ ] The CTA and landing page match the Google campaign.

Use current official LinkedIn specs for dimensions before launching live ads.

---

## Phase 5: Launch Decision

Before launch, decide:

| Situation | Decision | Action |
|---|---|---|
| Copy passes QA and landing page matches | Launch test | Import Google CSVs or create LinkedIn ads manually |
| Copy passes but landing page mismatch exists | Hold | Create or revise landing page |
| Claims fail QA | Rewrite | Fix before upload |
| Image generation unavailable | Hold LinkedIn image ads | Use prompts later or run Google-only test |
| Budget/targeting unknown | Draft only | Keep paused until media plan is approved |

Archive all artifacts under `outputs/ads/` even if the campaign does not launch. Failed or held ads
become useful context for future campaign work.

---

## Phase 6: Iterate From Results

After a campaign has enough data, append performance notes to `qa.md` or a new review artifact:

```markdown
## Performance Review
Date:
Spend:
Impressions:
Clicks:
CTR:
CPC:
Leads or access requests:
Top headline:
Weak headline:
Decision: continue / iterate / retire
```

Use the `paid-ads-builder` skill again to generate the next test batch from what worked.
