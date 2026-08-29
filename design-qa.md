# Design QA — Tourist Card landing page

## Comparison target

- Source visual truth: `assets/travel-card-reference.png` (489 × 489 px), supplied Travel Card reference.
- Implementation: in-app browser capture of `https://htmlpreview.github.io/?https://github.com/parisaqomi/t.card/blob/7d3930e/index.html`.
- Desktop review viewport: 1440 × 900 CSS px, density 1×. Hero product frame: 400 × 400 CSS px; displayed source image: 376 × 376 CSS px.
- Mobile/default viewport was also checked. The product card stays contained and does not clip.
- State: Hero at rest; primary CTA was clicked and scrolled to `#lead-form`.

## Comparison evidence

The Hero uses the supplied card artwork directly rather than an HTML, CSS, or SVG approximation. The implementation screenshot was captured in the in-app browser during review; its rendered image resolved to the committed `assets/travel-card-reference.png` at its native 489 × 489 px resolution. The review also verified the original source asset visually before implementation.

## Required fidelity surfaces

- **Fonts and typography:** Vazirmatn remains the RTL reading font; the Hero has a single, clear title weight and standard paragraph rhythm.
- **Spacing and layout rhythm:** the desktop Hero has a two-column 773 / 571 px grid, with a 400 px product frame and clear separation between product and message.
- **Colors and tokens:** restrained navy background, red CTA, and the supplied card’s red product art retain the brand contrast without animated color effects.
- **Image quality and asset fidelity:** source card artwork is direct raster content, correctly proportioned, sharp, and placed on its intended neutral gray background. No CSS-art or custom SVG card replacement remains.
- **Copy and content:** the current Persian Hero copy, navigation, CTA, form fields, features, and FAQ render coherently.

## Interaction and console checks

- Primary Hero CTA changes the hash to `#lead-form` and scrolls to the lead form.
- The lead form exposes two input fields and a submit button.
- Browser console: no warnings or errors during review.

## Findings

No actionable P0, P1, or P2 issues in the scoped redesign. The full page had no matching visual reference beyond the supplied card asset, so QA judged the rest of the page against the user’s stated requirement for a calmer, less effect-heavy presentation.

## Follow-up polish

- P3: replace the remaining inline SVG feature icons with a single production icon set if branded icons become available.

final result: passed
