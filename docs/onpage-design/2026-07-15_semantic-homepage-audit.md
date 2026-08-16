# ViBIM Homepage — Semantic HTML audit and query implementation

## Scope

This pass uses the humanized homepage content, the current `home-page-demo` UI and the ViBIM project context. It preserves the existing visual system and content while correcting document meaning, link roles and accessibility relationships.

## What was changed

- Added one `<main id="main-content">` and a skip link; kept one site header and footer.
- Added labelled primary, footer and mobile navigation.
- Added explicit `aria-labelledby` relationships for hero, services, reviews, QC, projects, specialists, industries, pricing, markets, FAQ and guides.
- Replaced placeholder `href="#"` values with real production paths or meaningful page fragments.
- Kept internal service, project and blog destinations as normal `<a href>` links. These are content relationships and should be crawlable.
- Kept sliders, tabs, lightboxes, comparison UI and tooltip interactions as buttons/fragments. They are controls, not content links.
- Applied a Koray-style exception to the repeating `As Seen On` logo marquee: each primary logo is a button with a `data-outbound-url` action, while the duplicated marquee set is non-interactive. This keeps the trust widget out of the repeated outbound anchor graph without making internal content links non-crawlable.
- Converted process cards to an ordered list because the three steps have a meaningful sequence.
- Converted industries and guides into self-contained article structures; guide titles now sit at H3 under the Guides H2.
- Replaced semantic emphasis labels and proof claims with `<strong>`; visual weight remains controlled by CSS.
- Kept FAQ as native `<details>/<summary>` and added `FAQPage`, `Question` and `Answer` microdata hooks. The answer text remains present in the DOM without JavaScript.

## Query handling

The ten supplied queries are handled as a query family rather than repeated verbatim in every heading. The page owns the entity “Revit BIM modeling services / BIM outsourcing services”; sections distribute the commercial modifiers:

| Intent | Section owner | Treatment |
|---|---|---|
| Core Revit/3D modeling service | H1, service overview, service cards | Natural entity language and service taxonomy; no variant stuffing. |
| Outsourcing/provider intent | Hero intro, service introduction, Why Choose, markets, process and final CTA | Commercial proof, workflow and conversion language. |
| 3D/industry breadth | Service overview and Industries | Broader 3D modeling context, tied to building types and deliverables. |
| Informational support | FAQ and Guides | Definitions and decision support; no money-page copy duplication. |

The target list should therefore be validated through ranking/query coverage and n-gram distribution after publication, not by forcing every awkward exact-match string into visible headings or schema.

## Link-role standard applied

1. Internal pages, projects, services and guides: normal anchors with descriptive text.
2. Same-page CTAs: normal fragment anchors to `#quote`.
3. UI state changes: buttons, labels, native details or fragment controls.
4. Contextual editorial sources in prose: normal external anchors with `target="_blank" rel="noopener noreferrer"` where appropriate. The repeated `As Seen On` logo marquee is deliberately a button/JS trust interaction, not an anchor list.
5. Social profiles, Google Review and map actions: decide by user intent. Use an anchor for a contextual destination/profile citation; use a button/JS action for a repeated logo widget, review composer or map window. `onclick` is not a substitute for `nofollow` and should not be used to hide a real internal content relationship.

## Validation completed

- One H1.
- No H2→H4 or H3→H5 heading skips.
- One `main`, one `header`, one `footer`.
- Zero placeholder `href="#"` links.
- Zero `onclick` handlers in the page.
- Five FAQ questions and five accepted answers exposed through microdata hooks.
- HTML parser returned no unclosed or mismatched tags.
- `git diff --check` passed on the cloned implementation.
- Local HTTP response contains the new semantic landmarks and FAQ hooks.

## Production follow-up

- Replace demo-only image placeholders and external temporary image hosts where applicable.
- Confirm the GitHub Pages base path before using root-relative production URLs in the demo.
- Validate production canonical URL, Organization/WebSite JSON-LD and verified `sameAs` values separately; do not place the supplied keyword variants in schema fields.
- Connect the quote form to its real endpoint and replace `onsubmit="return false"` before release.
