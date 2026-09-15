# Design QA

## Comparison target

- Source visual truth: `src/static/imgx-1.png` (1513 × 1040, hero) and `src/static/imgx-2.png`, `src/static/imgx-3.png`, `src/static/imgx-4.png` (each 1536 × 1024, case-study imagery).
- Implementation: browser-rendered `http://localhost:3000/` in the Codex in-app browser, desktop viewport 1312 × 823 CSS px at device scale factor 1.
- State: desktop home route, entrance animation completed; contact form anchor and submitted state were also tested.
- Density normalization: none required. Source artwork is displayed as responsive, cropped imagery rather than a pixel-for-pixel full-page mockup.

## Full-view comparison evidence

The hero uses `imgx-1.png` as the full-bleed visual with the copy deliberately positioned in its supplied left-side negative space. The selected-work cards use `imgx-2.png` through `imgx-4.png` without substitutions. The dark navy shell, blue accents, sharp square controls, and restrained spacing preserve the supplied assets' enterprise technology direction.

Focused comparison was required for the hero and case cards because they are the supplied visual truth. Browser inspection confirmed all four images render with the intended `object-cover` crop and accessible Chinese alt text.

## Required fidelity surfaces

- **Fonts and typography:** System sans-serif typography uses a high-contrast editorial hierarchy. Large hero and section headings preserve readable wrapping at the tested desktop width; small labels use a restrained tracked uppercase style.
- **Spacing and layout rhythm:** A `max-w-7xl` content frame, consistent 24/32 section spacing, and a three-column case grid create an orderly B2B presentation. No clipping or persistent-control overflow was observed.
- **Colors and visual tokens:** The implementation uses deep navy surfaces, low-opacity white dividers, bright blue accents, and a pale-blue inquiry section to align with the supplied technology visual palette.
- **Image quality and asset fidelity:** All supplied raster assets are used directly. No generated placeholders, improvised SVGs, CSS drawings, or substitute imagery are present.
- **Copy and content:** The copy consistently positions 智寻科技 as an enterprise website design and deployment partner; labels, CTAs, and form placeholders are in Chinese for the intended market.

## Findings

No actionable P0, P1, or P2 visual differences were found for the defined asset-led homepage direction.

## Primary interactions tested

- “获取方案” scrolls to the inquiry section.
- The required company, contact, and project-brief fields accept input.
- Submitting the local demo form shows the confirmation state.
- Browser console contained no errors during verification.

## Implementation checklist

- [x] Use all four supplied image assets.
- [x] Provide working anchor navigation and project-inquiry path.
- [x] Verify production build and ESLint.
- [x] Verify desktop rendering and local form state in browser.

## Follow-up polish

- [P3] Add the final 智寻科技 brand logo when available.
- [P3] Connect the inquiry form to an email, CRM, or database endpoint before public launch.

final result: passed
