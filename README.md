# veganalysis-web

Public-facing landing page for [Veganalysis](https://veganalysis.com)
(iOS / Android), published by Skyline Trail Computing LLC (Colorado,
USA).

## What this is

Single-page static site at `veganalysis.com`. Mirrors the
[`veganalysis-legal`](https://github.com/skylinetrailcomputing/veganalysis-legal)
pattern (per-app repo, GitHub Pages, custom domain via Cloudflare DNS) —
chosen for the same per-app-portability reason laid out in
`claude-workspace-2026/knowledge/aws/organization.md`.

## Contents

- `index.html` — the landing page. Plain HTML + inline CSS, no build
  step.
- `CNAME` — GitHub Pages custom-domain marker for `veganalysis.com`.

## Source of truth for copy

All on-page copy is sourced from
`bradleypmartin/veganalysis:_private/app-store-listing-copy.md` (the
App Store listing draft). Do not author parallel marketing copy here —
update the listing copy first, then mirror the wording change to
`index.html` to keep the two in sync.

The audited subtitle, three-state verdict descriptions, and Privacy
section phrasing are copied verbatim from the listing draft's
guardrail-audited blocks.

## Deferred / follow-ups

- **Favicons + Open Graph image + wordmark** — tracked in
  [`bradleypmartin/veganalysis#134`](https://github.com/bradleypmartin/veganalysis/issues/134),
  blocked by app-icon polish in `#108`. v0 of this page ships without
  these; browser tab will show a default icon until #134 lands.
- **App Store / TestFlight CTA buttons** — placeholder "private beta"
  copy today. Replace with App Store badge + TestFlight join link once
  the F&F TestFlight invite period opens publicly.
- **`veganalysis.app` → `veganalysis.com` 301** — Cloudflare Page Rule;
  see [`bradleypmartin/veganalysis#132`](https://github.com/bradleypmartin/veganalysis/issues/132)
  comment for the disposition.
- **App Store Marketing URL** — wire `https://veganalysis.com` into the
  App Store Connect Marketing URL field once the page is live; today
  that field is intentionally blank per
  `_private/app-store-listing-copy.md:191-195`.

## Cross-references

- [`bradleypmartin/veganalysis#132`](https://github.com/bradleypmartin/veganalysis/issues/132)
  — the tracking Issue for this work.
- [`skylinetrailcomputing/veganalysis-legal`](https://github.com/skylinetrailcomputing/veganalysis-legal)
  — sibling per-app repo (Privacy Policy + EULA), same Pages pattern.
- `bradleypmartin/veganalysis:_private/app-store-listing-copy.md` —
  canonical source for all on-page copy strings.
