# practice-ai

## COLD-START RITUAL (read on the first message of every session)

1. Read this entire file.
2. Read `memory-bank/activeContext.md` for the live state — what the last session did, where artifacts live, what open questions are blocking, what's next.
3. If working on a deliverable, also read `memory-bank/lessons.md` for any folder-specific dos/don'ts.
4. If `memory-bank/activeContext.md` and this file conflict, trust `activeContext.md` for state and trust this file for rules / standing instructions.
5. At session end, run `/wrap-session` to refresh `memory-bank/activeContext.md` and audit in-flow captures.

> Behavior rules (how to act, response style, honesty protocol) come from the macro global fileset — they are NOT restated here. This file is project-local context only.

## What this is

**PracticeAI** — a complete go-to-market package for a spec/concept product: an AI practice-management automation service for independent medical and dental practices (no-show elimination, multi-channel reminder cascades, insurance pre-verification, digital intake, recall automation). Pricing tiers spec'd at $999–$1,999/mo + setup, targeted at owner-operator practices in the Sacramento / Placer County area.

The repo is a "business-in-a-box": brand identity (`BRAND.md`), product/technical delivery spec (`PRODUCT-SPEC.md`), GTM strategy (`MARKETING.md`), ad creative (`ADS.md`), cold-outreach sequences (`OUTREACH.md`), prospect-discovery criteria (`PROSPECT-CRITERIA.md`), plus a polished single-file landing page (`index.html`, mirrored at `website/index.html`; Tailwind CDN + three.js, navy/sapphire clinical theme).

**Type:** landing-site (published) — the landing page is the live shipped artifact.
**Status:** Published / live. The landing page is deployed on GitHub Pages (status `built`) at https://winnsolutionsadmin.github.io/practice-ai/. Git history is two commits ("Initial build: PracticeAI — Wave 3 Night 1" + "Add root index.html for GitHub Pages"), indicating a fast build exercise; no working session since. Appears not actively iterated.

## Memory

Project state and history live in `memory-bank/`:
- `memory-bank/activeContext.md` — where the last session left off (read first)
- `memory-bank/projectbrief.md` — what this is, type, status, tech
- `memory-bank/lessons.md` — accumulated dos/don'ts for this repo
- `memory-bank/progress.md` — what works / what's broken / what's queued
- `memory-bank/decisions/` — ADRs
