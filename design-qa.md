# Design QA — Feature-card reference update

## Comparison target

- Source visual truth: `/var/folders/jq/n70bnlmd12d3skdtwstp79lw0000gp/T/codex-clipboard-1a0eee7f-012e-4d4c-bfc0-28200308490e.png` (514 × 152 px).
- Implementation: browser-rendered local preview at `http://127.0.0.1:4173/index.html`, captured in the Codex in-app browser during this review.
- Desktop comparison: 1280 × 900 CSS px viewport; the rendered feature card is 1088 × 152 CSS px.
- Mobile comparison: 390 × 844 CSS px viewport; rendered feature cards are 350 × 142 CSS px.
- State: feature section at rest. The supplied source is a single component reference, so the comparison is focused on that region rather than the whole page.

## Comparison history

### Pass 1 — component structure

- [P1] The feature cards had a boxed icon and vertically centred treatment that did not match the supplied reference.
  - Fix: replaced the icon tile with a small standalone icon on the right; aligned the title and description as a two-line text block; set a full-width white surface, navy outline, 28 px radius, and restrained offset shadow.
  - Post-fix evidence: all four desktop cards measure 152 px high and preserve the reference's right-side icon/title alignment. The mobile variant has no horizontal overflow.

### Pass 2 — fit with the existing landing page

- [P2] The reference-faithful cards still read as visually detached from the landing page: the icon tone and hard outline did not echo the product's navy/red controls or its softer surface elevation.
  - Fix: vertically centred the copy, introduced a small restrained red icon treatment, softened the navy outline, and added the same low-elevation shadow rhythm used by the page's other cards. Hover now only adds a controlled red border and slight lift.
  - Post-fix evidence: the desktop feature card remains 1088 × 152 px; title and copy start 44 px from the top, while the icon begins 39 px from the top. At the 390 px mobile check, every card's copy fits within its 142 px frame and there is no horizontal overflow.

No actionable P0, P1, or P2 mismatches remain for the requested component. The live landing-page width is intentionally wider than the supplied single-card crop.

## Required fidelity surfaces

- **Fonts and typography:** Persian Vazirmatn is retained. The title is 1.28 rem on desktop with a clear title/description hierarchy; mobile scales to 1.16 rem without wrapping or truncation.
- **Spacing and layout rhythm:** desktop cards use 2 rem inset padding and 16 px vertical separation; the centred text block makes the 152 px frame feel balanced. Mobile preserves the icon-to-copy relationship at 1.4 rem inset padding.
- **Colors and visual tokens:** existing white surface, navy content, and red action token are retained. The icon uses a low-contrast red surface and the border/shadow are navy-based; no palette changes were introduced.
- **Image quality and asset fidelity:** the supplied reference contains no raster content to reproduce. Existing feature icons were retained and reduced to match the reference's light standalone icon treatment.
- **Copy and content:** all four existing Persian feature titles and descriptions remain unchanged. The requested hero phrase is absent.

## Interaction and console checks

- The four feature cards render at the intended dimensions on desktop and mobile.
- No horizontal overflow was found at 1280 px or 390 px.
- Browser console: no errors or warnings during the local review.

## Follow-up polish

- P3: if a matched custom icon set becomes available later, replacing the mixed outline icons would make the feature list even more uniform.

final result: passed
