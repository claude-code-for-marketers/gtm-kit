---
name: blog-post-creator
description: Create one context-aware, publishable Markdown blog post for Newsletter Radar from a single topic. Use when Codex is asked to draft blog content, SEO content, thought-leadership posts, or website articles using the GTM Kit context, especially for producing outputs that can be moved into newsletter-radar-site/content/blog.
---

# Skill: Blog Post Creator

**Duration:** 30-60 minutes per post
**Output:** `outputs/content/YYYY-MM-DD-[topic-slug].md`

---

## Quick Start

```
Read skills/blog-post-creator/SKILL.md and write a blog post on: [topic]
```

The skill creates one reviewed blog post, not a full topical cluster. Use the final publishable Markdown
section as the source for `../newsletter-radar-site/content/blog/[slug].md` after human review.

---

## Purpose

Turn one topic or buyer question into a publishable Newsletter Radar blog post that reflects the GTM repo:
ICP, positioning, personas, product truth, and claim boundaries. The output should read like Newsletter
Radar wrote it, not like generic SEO copy.

---

## Required Context

Read these files before drafting:

- `context/profile.md`
- `context/icp-definition.md`
- `context/positioning.md`
- `context/sponsorship-decision-framework.md`
- `context/personas/head-of-growth.md`
- `context/personas/founder-marketing-lead.md`

Use `context/competitor-radar.md` only if the topic is explicitly about competitors or objections.

---

## Inputs

- Topic or buyer question
- Optional target persona
- Optional target keyword
- Optional desired CTA

If optional inputs are absent, default to:

- Persona: Head of Growth / Performance Marketing
- Search intent: practical research by a buyer evaluating newsletter sponsorships
- CTA: request early access or run a sample lookup

---

## Process

### Step 1: Build The Brief

Define:

- Topic
- Working title
- Target audience
- Search intent
- Primary keyword
- Thesis
- Source context from the required files
- Claim boundaries
- CTA

Include a small cluster map:

- Pillar topic
- 3-5 possible supporting posts
- Internal links to include now or later

### Step 2: Draft The Outline

Create an outline with:

- Intro that names the buyer's problem quickly
- 3-5 practical sections
- Newsletter Radar's point of view
- Honest limitation or caveat
- CTA

Prefer concrete headings over clever headings.

### Step 3: Write The Draft

Write in Newsletter Radar's voice:

- Direct
- Concrete
- Evidence-led
- Lightly technical when useful
- Written for advertisers and buyers, not publishers

Use these product truths:

- Newsletter Radar is a newsletter advertising intelligence platform for advertisers.
- It shows where companies advertise across newsletters and who advertises on any newsletter.
- The key insight is retention: advertisers do not keep paying for placements that do not work.
- Newsletter Radar shows presence, tenure, repeat behavior, and competitor footprints.
- It does not claim to measure conversions.

Avoid common AI-writing tells:

- Do not inflate ordinary points into claims about legacy, broader trends, pivotal shifts, or enduring significance.
- Do not add superficial analysis after facts with vague participle phrases like "highlighting," "underscoring," "reflecting," or "contributing to."
- Do not use promotional puffery: avoid words like groundbreaking, robust, vibrant, rich, profound, seamless, diverse array, nestled, showcase, and boasts.
- Do not rely on vague authorities such as "experts argue," "industry reports say," "observers note," or "many sources suggest" unless specific sources are actually named and used.
- Do not overuse generic AI vocabulary: delve, crucial, key, landscape, intricate, pivotal, enhance, foster, valuable insights, testament, underscore, aligns with, or resonates with.
- Do not write filler transitions such as "It is important to note," "Overall," "In conclusion," or "In today's evolving landscape."
- Do not force a rule-of-three list unless the underlying framework actually has three meaningful parts.
- Do not include assistant chatter such as "I hope this helps," "of course," "certainly," "would you like," or references to being an AI model.
- Do not use ornate synonyms where plain verbs work. Prefer wrote, moved, used, tried, and died over authored, relocated, utilized, attempted, and passed away.
- Do not smooth away specific facts into generic importance claims. If a sentence could apply to almost any company, channel, or article, rewrite it with a concrete Newsletter Radar point.

### Step 4: Run Editorial QA

Before finalizing, check:

- [ ] The post is for the buy side, not newsletter publishers.
- [ ] It does not frame Newsletter Radar as a lead-gen or prospecting database.
- [ ] It does not claim direct ROI, conversion rates, or attribution.
- [ ] It does not imply a free tier or free trial.
- [ ] It does not claim complete newsletter coverage.
- [ ] It uses retention, tenure, repeat rate, competitor footprint, or placement planning as the core angle.
- [ ] It gives the reader a useful framework even if they do not buy.
- [ ] The CTA points to request access or a sample lookup.
- [ ] It avoids inflated significance, vague attribution, promotional puffery, generic AI vocabulary, formulaic transitions, and assistant-like phrasing.
- [ ] Every analytical sentence is tied to a concrete buyer problem, product truth, or observable sponsorship signal.

If any item fails, revise the draft before producing the final Markdown.

### Step 5: Save The Output

Save the full skill output to:

```text
outputs/content/YYYY-MM-DD-[topic-slug].md
```

Use this structure:

```markdown
# Blog Post: [Title]
Date: [YYYY-MM-DD]
Topic: [Topic]
Status: Draft ready for review

## Content Brief
[brief]

## Cluster Map
[pillar and supporting ideas]

## Outline
[outline]

## Editorial QA
[checklist with pass/fail notes]

## Publishable Markdown
---
title: "[Title]"
description: "[Meta description]"
date: "[YYYY-MM-DD]"
published: true
---

[final post body]
```

---

## Advanced Extension

This skill creates one post. To scale it into a topical-cluster workflow later, add research sources,
keyword volume and difficulty checks, supporting headline generation, image sourcing, internal-link
planning, and CMS publishing.
