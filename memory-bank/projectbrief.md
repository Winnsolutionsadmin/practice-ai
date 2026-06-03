---
name: project brief — practice-ai
description: What this project is, why it exists. Populated over time, not at scaffold.
type: project
---

# practice-ai

**Created:** 2026-06-02 (initial build; scaffold retrofitted 2026-06-03)
**Category:** landing-site / go-to-market package (published)

## Purpose

**PracticeAI** is a complete go-to-market package for a spec/concept product — an AI practice-management automation service for independent medical and dental practices. The pitch: eliminate the administrative burden (no-shows, insurance verification, intake paperwork, recall/follow-up) that keeps small healthcare practices from doing actual healthcare. Positioned as a done-for-you managed service + software platform at $999/mo (Foundation) / $1,999/mo (Full Practice) / Custom, wedge on no-show elimination, targeted at owner-operator practices (1–8 providers, $500K–$5M revenue) in Sacramento / Placer / El Dorado counties.

The repo packages everything needed to take that offering to market plus the live front door.

## What this is (type + status + tech)

- **Type:** landing-site (published). The shipped, live artifact is the landing page.
- **Status:** Published / live. Landing page deployed on GitHub Pages (status `built`) at https://winnsolutionsadmin.github.io/practice-ai/. Git history is 2 commits ("Initial build: PracticeAI — Wave 3 Night 1" + "Add root index.html for GitHub Pages") — a fast build exercise; no iteration since. Appears dormant.
- **Key tech:** Single-file static landing page (`index.html`, 1021 lines; mirrored at `website/index.html`) using Tailwind via CDN + three.js (r128) for visuals, Fraunces / DM Sans / DM Mono fonts, navy + sapphire + teal clinical theme. No build step, no package.json, no backend. Hosted on GitHub Pages from `main` `/`.

## Repo contents

- `index.html` / `website/index.html` — the landing page (identical copies; root copy serves Pages)
- `BRAND.md` — brand identity (name, tagline, palette, voice)
- `PRODUCT-SPEC.md` — product & technical delivery spec (systems, pricing, contract terms)
- `MARKETING.md` — go-to-market strategy, ICP, positioning
- `ADS.md` — ad creative (Google RSAs, etc.)
- `OUTREACH.md` — cold-email / outreach sequences
- `PROSPECT-CRITERIA.md` — prospect-discovery search criteria (geography, query strings)

## Context not obvious from files

<!--
Things that only exist in Jarred's head right now:
- Why this AT ALL (real offering vs. build exercise / "Wave 3 Night 1" suggests a timed/practice build)
- Whether PracticeAI is being actively pursued or is archived
- What "done" looks like
- What "out of scope" looks like
-->

- The commit message "Wave 3 Night 1" suggests this was produced as part of a structured build exercise/sprint rather than (necessarily) a live commercial venture — confirm before treating it as an active offering.
