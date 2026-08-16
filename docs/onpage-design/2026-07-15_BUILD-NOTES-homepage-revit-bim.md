# Build notes — ViBIM homepage semantic pass

## Deliverable

- `2026-07-15_homepage-revit-bim-semantic.html`
- Source clone reviewed from `LongDZ1204/home-page-demo`.

## Implementation boundary

This is a minimal-diff semantic implementation. The current layout, colors, typography, section order, interactions and humanized copy were retained. No GitHub branch or remote was changed.

## Section and link map

- `#services`: eight Revit/BIM service articles and production service URLs.
- `#projects`: six project articles and project detail URLs.
- `#experts`: five specialist profile articles.
- `#industries`: nine industry articles/cards; hover/focus notes remain UI content, not links.
- `#pricing` / `#how-it-works`: ordered quote, free-trial and pricing steps.
- `#faq`: native details plus FAQ microdata.
- `#guides`: five guide articles and blog URLs.
- `#quote`: final conversion form and same-page CTA destination.

## Dev handoff notes

- Root-relative URLs in the file assume the production ViBIM domain. GitHub Pages may need a base-path adapter for visual demo navigation.
- The current quote form intentionally remains a non-submitting demo. Wire its real endpoint, validation and success state before production.
- The repeating `As Seen On` logo marquee intentionally uses button + `data-outbound-url` + JavaScript `window.open`, following the Koray-style separation of a trust widget from the anchor graph. Keep contextual in-copy citations as anchors. For social profiles or Google Review, use an anchor for contextual citation; use a button/action for a repeated widget, review composer or map interaction.
