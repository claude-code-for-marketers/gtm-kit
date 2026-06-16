# Newsletter Radar — GTM Kit

The go-to-market knowledge repository for **Newsletter Radar**: newsletter sponsorship intelligence for
the buy side. We help brands and advertisers see where competitors advertise in newsletters and decide
where to spend next.

This repo is Newsletter Radar's persistent GTM context for Claude Code — company profile, ICP, signals,
positioning, competitor battlecards, and personas. Fill the context once; run AI-powered GTM tasks from a
one-line prompt without rebuilding context every session.

> Built on [The Revenue Architects' GTM Starter Kit](https://github.com/KarlRaf/gtm-starter-kit) (MIT).
> **Status: pre-launch** — many fields are marked `[inferred]` and should be confirmed by the founder.

---

## How It Works

Claude Code reads `CLAUDE.md` automatically at the start of every session — the summary layer of our
company overview, ICP, signals, personas, and current priorities. The full context lives in `context/`.
Once filled in, run any task with a one-line prompt:

```
Read skills/account-research/SKILL.md and research figma.com
```

Claude reads our ICP, signals, and personas from the repo and produces a full account research brief —
no pasted context.

---

## What's Inside

```
gtm-kit/
├── CLAUDE.md                       ← Summary context layer. Read every session.
├── context/                        ← Newsletter Radar's GTM institutional knowledge
│   ├── profile.md                  ← Company overview, product, market context
│   ├── icp-definition.md           ← Buy-side ICP: brands/advertisers, tiers, anti-ICP
│   ├── signal-library.md           ← Buying signals (incl. our own index as a signal source)
│   ├── positioning.md              ← Value pillars, messaging matrix, what not to say
│   ├── competitor-radar.md         ← Battlecards: Who Sponsors Stuff, SponsorGap, Appeared.in, Paved Radar
│   └── personas/                   ← Head of Growth, Founder/marketing lead
├── skills/                         ← Claude executes these from one-line prompts
│   ├── setup/ · account-research/ · icp-scoring/ · signal-to-sequence/ · weekly-update/
├── workflows/                      ← How the team operates (enrichment, signal routing, campaign build)
├── playbooks/                      ← Step-by-step guides (new-signal response, competitor switch)
├── sync/                           ← Scripts to pull live data into the repo
└── outputs/                        ← All skill outputs land here
```

**Skills vs. Workflows:** Skills are for Claude to execute (you run them with a prompt). Workflows
document how the team operates — reference docs for humans.

---

## The Wedge

Every established tool in this category — Who Sponsors Stuff, SponsorGap, Appeared.in, Paved Radar — is
sold to newsletter **publishers** as a prospecting database to find advertisers. Newsletter Radar points
the same data at the **advertiser**:

1. **Reverse lookup** — "Where has this company advertised?" → a brand's full newsletter footprint.
2. **Recommendations** — "Which newsletters should we sponsor?" → a ranked plan from competitor + lookalike spend.

See `context/competitor-radar.md` for full battlecards and `context/positioning.md` for the messaging.

---

## Getting Started

```bash
cd gtm-kit
claude .
```

**First: confirm the inferred fields.** This repo was bootstrapped pre-launch, so founder-specific
fields (pricing, exact ICP cut, stack, priorities) are marked `[inferred]`. Run a refinement pass to
replace them with real answers, then start running skills:

```
# Research a target advertiser
Read skills/account-research/SKILL.md and research [company.com]

# Score a list of brands against our ICP
Read skills/icp-scoring/SKILL.md and score these companies: [paste list]

# Build a campaign from a signal
Read skills/signal-to-sequence/SKILL.md.
Build a Tier 2 campaign for accounts triggering [signal name]. Target [persona].
```

All outputs land in `outputs/` — `outputs/YYYY-MM-DD-[type]-[name].md`.

---

## Keeping It Current

Run the weekly-update skill (`skills/weekly-update/SKILL.md`) regularly. Update
`context/competitor-radar.md` after every competitive deal, and review `context/icp-definition.md`
quarterly (log changes in its ICP evolution log).

## What Not to Put in This Repo

- Customer or prospect contact lists (never commit to git)
- API keys / credentials (use environment variables)
- Raw transcripts (synthesize into the relevant context file)
- Commercial pricing terms

---

## License

MIT (inherited from the GTM Starter Kit).
