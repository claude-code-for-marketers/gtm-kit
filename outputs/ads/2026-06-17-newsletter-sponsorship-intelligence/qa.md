# Paid Ads QA: Newsletter Sponsorship Intelligence
Date: 2026-06-17
Status: Draft ready for review

## Campaign QA

- [x] Campaign targets buy-side advertisers, not newsletter publishers.
- [x] Copy does not frame Newsletter Radar as a lead-gen or prospecting database.
- [x] Copy does not claim direct ROI, conversions, or attribution.
- [x] Copy does not imply a free tier or free trial.
- [x] Copy does not claim complete newsletter coverage.
- [x] CTA points to request early access or sample lookup.

## Google Ads QA

- [x] Google output uses five separate template-matched files.
- [x] `google/campaign.csv` matches the campaign template header.
- [x] `google/ad_group.csv` matches the ad group template header.
- [x] `google/responsive_search_ad.csv` matches the responsive search ad template header and includes the two template comment rows.
- [x] `google/keyword.csv` matches the keyword template header.
- [x] `google/ad_group_negative_keyword.csv` matches the ad group negative keyword template header.
- [x] Campaign, ad group, ad, and keyword rows are paused.
- [x] Google headlines are 30 characters or fewer.
- [x] Google descriptions are 90 characters or fewer.
- [x] Google paths are 15 characters or fewer.
- [x] Final URL includes UTM parameters.
- [x] Negative keywords suppress publisher/sell-side intent.

## LinkedIn QA

- [x] LinkedIn intro text stays near 150 recommended characters and below 600 max.
- [x] LinkedIn headlines stay below 70 recommended characters.
- [x] LinkedIn descriptions stay near 100 recommended characters and below 300 max.
- [x] Image prompts avoid fake proof, fake metrics, customer logos, and trademark issues.
- [x] Generated PNG assets exist and are readable.

## Generated Files

- `brief.md`
- `google/campaign.csv`
- `google/ad_group.csv`
- `google/responsive_search_ad.csv`
- `google/keyword.csv`
- `google/ad_group_negative_keyword.csv`
- `linkedin/linkedin-ads.md`
- `linkedin/image-prompts.md`
- `linkedin/images/newsletter-sponsorship-intelligence-square.png`
- `linkedin/images/newsletter-sponsorship-intelligence-landscape.png`

## Review Notes

- Budget is set to `10.00` as a placeholder in `google/campaign.csv`; review before import.
- Ad copy lives in `google/responsive_search_ad.csv`, not in the campaign, ad group, keyword, or negative keyword files.
- Current LinkedIn dimensions are sample review assets. Confirm current LinkedIn placement specs before launch.
- The campaign should remain paused until landing-page message match is reviewed.
