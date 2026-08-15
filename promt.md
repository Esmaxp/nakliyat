Task: Fix a real visual bug and do a desktop-width visual QA pass on
index.html (single-file static site)

Confirmed bug (screenshot evidence)
In the "Kasa Ölçüleri" section, hovering/interacting near the SVG blueprint
diagram (id="cizim-baslik" / id="cizim-aciklama") triggers the browser's
native SVG <title> tooltip, which renders as a plain white box reading
"Kasa ölçü föyü — yan ve arka görünüş" that visually overlaps the
kasa-arkadan photo below it — it looks like a broken/floating UI element,
not an accessibility label.
Fix: remove reliance on native title-hover tooltips for this SVG entirely.
  - Keep the SVG accessible via aria-labelledby pointing at the section's
    existing <h2 id="kasa-baslik"> and the existing <p class="lede"> (or a
    single concise visually-hidden <span> if more detail is needed) instead
    of <title>/<desc> children, since those are exactly the elements that
    produce hover tooltips in most browsers.
  - Do NOT just shorten the tooltip text — the fix is removing the
    hover-tooltip mechanism, not making the box smaller.
  - Verify after the fix: hovering anywhere over the blueprint SVG must
    produce no visible tooltip box in the rendered page.

Desktop visual QA pass (this is the main ask — verify by actually
rendering, not by reading the CSS)
The CSS/markup reads as reasonable on paper, but the user reports the
desktop rendering looks disorganized. Render index.html in a real browser
(e.g. via Playwright/Puppeteer if available in this environment, headless
Chromium at 1280px, 1440px, and 1920px widths) and take full-page
screenshots of each section: hero, hizmetler (manifest list), kasa
(blueprint + specs + photo), güvence (trust cards + photo + stamp),
iletişim. For each screenshot, check specifically for:
  - Any element overlapping another (text over photo, tooltip over content,
    absolutely-positioned decorative elements — the truck__frame::after
    accent bar, blueprint__scrollhint, guarantee stamp — landing on top of
    unrelated content instead of their intended spot).
  - Inconsistent vertical rhythm between sections — compare the
    eyebrow/h2/lede spacing pattern across all 5 sections; they should feel
    like the same system, not five slightly different gaps.
  - The two-column areas (.hero__grid, .kasa__alt) — confirm columns stay
    vertically aligned/balanced at each of the three widths, not one column
    trailing far below the other.
  - Photo framing: for each <figure class="shot">/.truck figure, confirm
    object-fit:cover isn't cutting off a photo's meaningful content (license
    plate, company lettering, the cargo box's structural detail) at any of
    the three widths — if it is, adjust object-position per image rather
    than changing the aspect-ratio wholesale.
  - The manifest (waybill-style services list), blueprint (technical spec
    drawing), stamp (wax-seal guarantee badge), and dashed truck frame are
    four distinct visual motifs on one page — confirm they read as one
    coherent identity (shared stroke weights, shared corner/border
    treatment, shared color use for accents) rather than four different
    styles stitched together. If any one of them clashes, adjust its
    detailing (border weight, corner radius, accent color usage) to match
    the others — don't remove the motif, tighten its execution.

Deliverable
- The tooltip fix applied.
- A short written list (in your response, not a new file) of every visual
  issue actually found in the rendered screenshots at 1280/1440/1920px,
  each with the fix applied directly to index.html.
- Do not touch content, copy, phone numbers, or the JSON-LD — visual/layout
  only.