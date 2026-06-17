# Workflow: Contact Sales Enrichment

*How a contact-sales submission becomes an enriched account preview. Run this before scoring, CRM sync, or outreach.*

---

## Purpose

Turn a website contact-sales request into a reviewable account and contact brief without exposing API keys,
committing raw lead data, or enrolling anyone in outreach automatically.

This checkpoint uses the public site as the workflow trigger:

```text
/contact-sales form
-> POST /api/enrichment
-> Orthogonal Run API
-> Apollo people match + organization enrichment
-> /enrichment-result preview
-> human review
```

The result page is illustrative and temporary. Until a database or CRM is selected, enrichment output stays
in the browser session only and is not written to `gtm-kit/outputs`.

---

## Input

The website collects:

| Field | Purpose |
|---|---|
| Company email | Identifies the requester and derives the company domain for enrichment. |
| Name | Gives Apollo an additional people-match signal. |
| Phone number | Captures sales follow-up context; not used to reveal phone data from Apollo. |
| Message | Preserves the buyer's stated need for human review. |

Reject obvious personal email domains such as Gmail, Yahoo, Outlook, iCloud, and Proton. The workflow
needs a company domain to enrich the account.

---

## Enrichment Step

The site calls Orthogonal from a server route only:

```text
POST https://api.orth.sh/v1/run
Authorization: Bearer $ORTHOGONAL_API_KEY
```

The API key lives in `newsletter-radar-site/.env.local` and is documented in `.env.example`. Never put
real API keys in git.

Run these Apollo endpoints through Orthogonal:

| Endpoint | Method | Input |
|---|---|---|
| `/api/v1/people/match` | POST | email, parsed first/last name, derived domain |
| `/api/v1/organizations/enrich` | GET | derived domain |

The site combines both responses into one preview payload:

```text
submittedLead
person
organization
warnings
price
raw
```

If Apollo or Orthogonal fails, the site may return visibly labeled demo fallback data so the workshop can
continue. Demo fallback must never be presented as verified enrichment.

---

## Review Gate

Before any follow-up, a human reviews:

- whether the company fits Newsletter Radar's buy-side ICP
- whether the requester appears to be a growth, marketing, founder, or paid acquisition buyer
- whether the company operates in a vertical covered by the crawl
- whether the message names a competitor, channel problem, or newsletter buying intent
- whether Apollo data looks current enough to trust

This checkpoint does not create CRM records, outbound sequences, or committed Markdown artifacts.

---

## Data Handling Rules

- Keep raw lead data out of git.
- Keep `ORTHOGONAL_API_KEY` out of git.
- Do not persist the preview result until a database or CRM is selected.
- Do not auto-enroll contacts in outreach.
- Label demo fallback data clearly.
- Treat `raw` JSON as debugging context, not the customer-facing brief.

---

## Future Extension

When persistence is introduced, save only reviewed and sanitized artifacts:

```text
gtm-kit/outputs/enrichment/YYYY-MM-DD-account-name.md
```

The saved artifact should summarize the account, contact, ICP fit, source data, open questions, and
recommended next action. It should not contain unnecessary raw vendor response payloads.
