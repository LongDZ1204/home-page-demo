# ViBIM homepage image map

Source content: `projects/vibim/content/05-humanized/2026-06-21_humanized-homepage-revit-bim-modeling.md`.

Implementation target: `home-page-demo/index.html` after the geo-tagged image package is returned and revalidated.

## Shared client reviews

Reuse the eight files in `geo-tag-pending/shared/email-reviews/` for the `What Clients Say About Our BIM Services` email-review tab. The same physical assets can be used on the Scan to BIM service page; do not create another compressed derivative unless the final component requires a different crop.

The customer-message tab remains sourced from the current live homepage and is outside this image-download package.

## Discipline and deliverable service cards

| Homepage content heading | Final filename | Source | Alt text | Caption |
|---|---|---|---|---|
| Scan to BIM | `homepage-scan-to-bim-services.jpg` | Current ViBIM homepage service image | Point cloud overlaid with coordinated Scan to BIM MEP model | None - the adjacent card copy already explains the service. |
| Architectural BIM Modeling | `homepage-architectural-bim-modeling.jpg` | Current ViBIM homepage service image | Architectural Revit model of an existing school building exterior | None |
| Structural BIM Modeling | `homepage-structural-bim-modeling.jpg` | Current ViBIM homepage service image | Structural Revit truss model aligned with laser scan geometry | None |
| MEP BIM Modeling | `homepage-mep-bim-modeling.jpg` | Current ViBIM homepage service image | MEP BIM model of mechanical equipment and connected pipework | None |
| Topography BIM Modeling | `homepage-topography-bim-modeling.jpg` | Current ViBIM homepage service image | Topography BIM model showing roads parking areas and site contours | None |
| As-Built BIM and Drawings | `homepage-as-built-bim-drawings.jpg` | Current `home-page-demo` service-card asset | As-built BIM model showing coordinated building systems and roof layout | None |
| Revit Family Creation | `homepage-revit-family-creation.png` | ViBIM Revit Family Creation service page | Parametric Revit window family with adjustable dimension constraints | None |
| BIM for Facility Management | `homepage-bim-facility-management.jpg` | ViBIM BIM for Facility Management service page | Revit mechanical equipment family with facility management asset parameters | None |

## Production HTML contract

- Keep the original `width` and `height` attributes from the final files to prevent layout shift.
- Use `loading="lazy"` and `decoding="async"` for these service-card images.
- Do not add `figcaption` inside the cards because the visible heading and description already supply the context.
- Preserve the filename and alt text mapping above after geo-tagging.
- Use local asset paths in production; do not hotlink WordPress uploads or Postimg URLs.

## Source URLs used for the new homepage package

- `https://vibimglobal.com/wp-content/uploads/2025/07/point-cloud-scan-to-bim-services.jpg`
- `https://vibimglobal.com/wp-content/uploads/2025/07/architecture-scan-to-bim-services.jpg`
- `https://vibimglobal.com/wp-content/uploads/2025/07/structural-scan-to-bim.jpg`
- `https://vibimglobal.com/wp-content/uploads/2025/07/mep-scan-to-bim.jpg`
- `https://vibimglobal.com/wp-content/uploads/2025/07/topography-scan-to-bim.jpg`
- `https://vibimglobal.com/wp-content/uploads/2025/10/revit-3d-bim-modelling-services.jpg`
- `https://vibimglobal.com/wp-content/uploads/2025/06/bim-revit-family-design.png`
- `https://vibimglobal.com/wp-content/uploads/2025/06/scan-to-bim-for-facility-management.jpg`
