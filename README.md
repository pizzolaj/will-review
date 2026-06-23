# Will Review

An interactive prototype for an AI-assisted tool that reviews **Wills and Powers of Attorney** against the CIBC Trust Corporation Reference Guide, with a human reviewer attesting to every finding before a report can be generated.

The prototype is a single, self-contained `Will_Review_Prototype.html` file — no build step, no dependencies to install. Open it in a browser and it runs.

> **Note:** This is a design prototype for evaluating UX and flow. It uses generic, illustrative content and does not perform real document analysis.

## Goal

The product is designed around **reviewer confidence and safety, not speed.** The AI surfaces and explains potential matches, variations, and gaps; the human reviewer reads each one, writes their own conclusion, and explicitly attests to it. A report cannot be produced until every mandatory clause across every document has been reviewed.

## Running it

Open `Will_Review_Prototype.html` in any modern browser (Chrome, Edge, Safari, Firefox). That's it.

- No server, build, or package install required.
- Icons load from the Lucide CDN, so an internet connection makes the icons appear (the prototype still works offline without them).

## The flow

The prototype walks through a three-step workflow:

1. **Upload** — drop in a single file that may contain documents for multiple people (e.g. a couple: one Will each plus property and personal-care POAs). The "Your uploads" library shows what has been added and its review status.
2. **Review** — the core screen. Each document is checked clause-by-clause against the reference guide. Every mandatory clause gets a status, an AI explanation, the matching reference clause, the source location(s) in the uploaded document, and a required attestation.
3. **Report** — once all documents are complete, generate a per-document or combined report.

## Key interactions

- **Per-clause attestation** — the reviewer writes a conclusion in their own words and checks the attest control. Mandatory clauses that aren't an exact match require a comment before they can be attested.
- **Status system** — Exact match (green), Strong similarity (slate), Variation (red), and Missing (red). The reviewer can reclassify any clause.
- **AI explanation** — a "Why this matched / Why this was flagged" callout with its own **See more** expansion for longer reasoning.
- **Reference options** — when the guide offers several acceptable versions of a clause, the AI picks the best fit and the reviewer can expand to see all options.
- **Source locations** — compact, clickable `§` chips link each finding to the exact passages in the source document; clicking a passage in the document reveals its associated finding.
- **Progress + guided path** — a persistent completion summary and a "Next unreviewed" action keep the reviewer moving; a report is hard-gated until everything is reviewed.

## Design system

- **Brand colours:** CIBC red `#C41F3E` and burgundy `#8B1D41`, with slate `#3F5C78` used for the caution/strong-similarity state.
- **Typography:** Whitney (Book / Medium / Semibold).
- **Icons:** [Lucide](https://lucide.dev) throughout (no emoji). See `Lucide_Icon_Spec.md` for the full icon-by-screen mapping.

## Files in this repo

| File | What it is |
|---|---|
| `Will_Review_Prototype.html` | The complete interactive prototype (HTML + CSS + JS in one file). |
| `Lucide_Icon_Spec.md` | Reference list of every Lucide icon used, by screen, size, and colour. |
| `README.md` | This file. |

## Status

Work-in-progress design prototype. Content, copy, and flows are illustrative and subject to change.
