# ViBIM Homepage — Semantic HTML SPEC

## Source of truth

- Content: `projects/vibim/content/05-humanized/2026-06-21_humanized-homepage-revit-bim-modeling.md`
- UI source: `LongDZ1204/home-page-demo` (`index.html`, cloned for implementation review)
- Client context: `projects/vibim/context.md`
- Semantic standard: `projects/vibim/outputs/onpage-design/2026-07-13_semantic-html-code-standard.md`

## Page role

- Type: Homepage with commercial service-hub behavior.
- Central entity: Revit BIM modeling services / BIM outsourcing services.
- Primary conversion: free trial model + fixed quote within 12–24 hours.
- Primary audience: survey firms, reality-capture firms, AEC practices and BIM consultancies.
- Visual constraint: preserve the current demo's layout, colors, motion and content; make surgical semantic changes only.

## Query-to-section routing

| Query family | Page owner / section | Implementation rule |
|---|---|---|
| `3d revit bim modeling services`, `revit bim modeling services`, `revit modeling services` | H1 + service overview | Use naturally in primary copy; do not repeat variants in headings. |
| `revit modeling outsourcing services`, `revit modeling outsourcing`, `revit bim outsourcing services`, `revit model outsourcing` | Outsourcing section + process/CTA | Keep as supporting commercial language; link to the relevant service destination where available. |
| `revit bim modeling service provider` | Services introduction + Why Choose ViBIM | Use as provider/entity wording, not as a repeated card label. |
| `3d bim modeling services`, `revit 3d bim modelling services` | Industries section + service overview | Use once in visible prose where it clarifies the broader 3D modeling scope. |

## Semantic decisions

1. Exactly one site `<header>`, one `<main id="main-content">`, and one `<footer>`.
2. Primary navigation gets `aria-label="Primary navigation"`; footer navigation gets its own label.
3. Hero becomes a section with an explicit heading relationship; the H1 remains unchanged.
4. Service, project, specialist, industry and guide cards become self-contained `<article>` blocks where their copy can stand alone; the ordered process is represented by `<ol>` and `<li>`.
5. The services group remains a `<section>`; the five Why Choose panels remain contextual sections/accordion items, not standalone service articles.
6. The process remains an ordered `<ol>` because step order is meaningful.
7. FAQ remains native `<details>/<summary>` with FAQ microdata hooks; no JS-only content dependency.
8. Internal service/project/blog links remain real `<a href>` links. UI controls remain buttons or fragment controls; no fake SEO links are created for sliders, lightboxes or tooltips.
9. Primary CTAs remain crawlable fragment links to `#quote`; external proof links use real anchors with `noopener noreferrer`.
10. Use `<strong>` for semantic emphasis. Keep visual styling in CSS rather than using heading or `<b>` tags as formatting.
11. JSON-LD stays a separate concern. Do not copy keyword variants into `WebSite.alternateName`; use only verified Organization/WebSite/FAQ data when the demo is promoted to production.

## Content map lock

1. Hero: H1, full intro, six benefit claims, two CTAs, point-cloud/Revit comparison.
2. As Seen On: six press references.
3. Client reviews: email proof tab and written review tab.
4. By the Numbers: six verified metric claims.
5. All Revit BIM Modeling Services: eight service articles.
6. Service CTA.
7. Standards & Quality Control: two-layer QC, five checks, US/UK standards, LOD.
8. Featured Projects: six project articles.
9. Why Choose ViBIM: five contextual differentiators.
10. Specialists: five team profile articles.
11. Dedicated-team CTA.
12. Industries: nine industry articles/cards.
13. Quote, Free Trial & Pricing: three process articles and CTA.
14. Market coverage: five markets.
15. FAQ: five question/answer items.
16. Guides & Insights: five guide articles.
17. Final quote form.
18. Footer navigation and contact information.

## Acceptance gates

- Heading tree has one H1, no H2→H4/H3→H5 skips, and no card titles using H4 under an H2 without an H3 layer.
- All target content sections remain in the rendered DOM, including collapsed/revealed content.
- Core internal links are real anchors with descriptive text; UI controls are not counted as internal SEO links.
- All form controls have labels; interactive comparison, accordions, sliders and lightbox controls remain keyboard-addressable.
- Render is checked at 1280px and 430px; no horizontal overflow or console errors.
- Content parity is checked against the humanized markdown before handoff.
