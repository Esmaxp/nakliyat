# Task: Build an SEO-friendly, semantic, well-designed one-page website for a local moving company

## Business context

**Karamanlı Nakliyat** — a home/office moving and intercity transport
business run by Hümmet Karamanlı, operating a Ford Transit box truck.
"Karamanlı" is also the name of a real district (ilçe) of Burdur, Turkey —
the business name doubles as the location, which matters for local SEO.

Two source materials are provided:
1. A promotional flyer (image) establishing the existing brand identity:
   navy blue + amber/gold + white color scheme, bold condensed display
   type, the tagline **"GÜVENLİ • HIZLI • EKONOMİK"**, and a photo of the
   actual Ford Transit box truck (asset available separately — use it, it's
   the real vehicle, not a stock photo).
2. A WhatsApp exchange giving the client's exact, deliberately minimal
   content requirements (translated below) — **follow these literally, do
   not add sections or content beyond what's listed.** The client explicitly
   said "that's it, no need for other fluff" (*"bu kadar yani başka öyle
   teferruata gerek yok"*).

## Exact required content (from the client's own instructions — non-negotiable)

- Company name shown as: **"Karamanlı Nakliyat"** only — no invented legal
  suffixes (no "Ltd. Şti.", no "A.Ş.", nothing not given).
- **Two phone numbers**: the father's number and the client's own number.
  ⚠️ **Only one number was actually provided in the source materials:
  `0536 334 97 26` (Hümmet Karamanlı).** Do not invent a second number.
  Build the contact section with two clearly-labeled call buttons/slots
  (e.g. "Hümmet Karamanlı" and a second labeled slot), using the known
  number for the first and a visibly-marked placeholder
  (`[İKİNCİ TELEFON NUMARASI — buraya eklenecek]`) for the second, so it's
  obvious what still needs to be filled in before launch.
- Service description: **"Evden Eve Şehirler Arası Nakliyat"** (home-to-home,
  intercity moving) must appear prominently.
- **Truck cargo box (kasa) dimensions** must be shown — this was explicitly
  requested as a required content item.
  ⚠️ **The actual dimensions were never provided.** Do not fabricate a
  specific number (moving companies advertising wrong cargo capacity
  misleads real customers). Build a dedicated, well-designed spec/dimensions
  section with a clearly-marked placeholder (e.g.
  `[UZUNLUK] m x [GENİŞLİK] m x [YÜKSEKLİK] m — Kasa ölçüleri eklenecek`)
  that's easy to fill in once the real measurements are supplied — see the
  design direction below for how to make this section a strong visual
  moment even with placeholder numbers.
- Additional service to include: **"Mobilya imalat ve kurulumu"**
  (furniture manufacturing and installation).
- Full service list, exactly as the client dictated (use as the basis for
  the services section, don't trim or embellish it): şehir içi ve şehirler
  arası nakliye, ev/ofis/parça eşya taşıma, mobilya imalat ve kurulum,
  güvenlik, hızlı ve zamanında teslimat.
- From the flyer (compatible with the above, keep it): eşyaya özenli taşıma,
  güvenli taşıma garantisi, uzman ekip, zamanında teslimat.
- **No fabricated content beyond this list** — no invented customer
  testimonials, no made-up review counts/ratings, no fake "since 19XX"
  founding dates, no team headcount claims that weren't given. If a section
  like testimonials would normally strengthen trust, either leave it out or
  replace it with something truthful and verifiable instead (e.g. the
  guarantee/trust badges the client did give you).

## Technical requirements (SEO + semantics)

- Single, self-contained, semantic HTML5 page (`<header>`, `<nav>`,
  `<main>`, `<section>`, `<article>`, `<footer>` used for their actual
  meaning, not `<div>` soup). One `<h1>`, logical heading hierarchy below it.
- `<title>` and `<meta name="description">` targeting realistic local search
  intent: e.g. "Karamanlı Nakliyat | Evden Eve ve Şehirler Arası Nakliyat —
  Hümmet Karamanlı" — work in "Karamanlı nakliyat", "evden eve nakliyat",
  "şehirler arası nakliyat", "Burdur nakliyat" naturally into copy and
  metadata, not keyword-stuffed.
- Open Graph / Twitter Card meta tags (title, description, image — use the
  truck photo) so it previews well when shared on WhatsApp (relevant given
  how this business actually gets referrals, per the chat screenshot).
- JSON-LD structured data using `schema.org/MovingCompany` (falls back to
  `LocalBusiness` if `MovingCompany` fields don't fit) — name, telephone,
  areaServed, description. Only include fields you actually have real data
  for; omit `aggregateRating`/`review` entirely rather than fabricating them.
- `alt` text on the truck image describing it factually (Ford Transit box
  truck, company livery), `lang="tr"` on `<html>`.
- Mobile-first responsive layout — this audience is calling from a phone
  half the time; tap targets for the phone numbers should be large and use
  `tel:` links.
- Fast-loading: plain HTML/CSS with minimal vanilla JS (no heavy framework
  needed for a one-pager like this). Respect `prefers-reduced-motion`.
  Visible keyboard focus states throughout.

## Design direction

Follow the studio brief mindset: make deliberate, specific choices grounded
in *this* subject — moving trucks, cargo, routes, delivery — not a generic
template. Some starting material, not a strict spec — push it further:

- The flyer's existing navy/amber/white identity is a real hint (this is
  the client's own brand), but don't just re-skin the flyer — find a more
  distinctive execution of the same identity. Consider leaning into a
  **cargo/freight/logistics vernacular**: waybill or manifest-style
  itemized lists for services, dimension lines and callouts (like a
  technical spec drawing) for the cargo box section, a stamped/sealed badge
  treatment for the "güvenli taşıma garantisi" guarantee.
- **Suggested signature element**: since the client explicitly wants cargo
  box dimensions front and center, consider rendering that section as an
  actual technical blueprint/spec diagram of the truck's box (dashed
  measurement lines, arrow callouts for length/width/height, drafting-style
  annotations) rather than a plain text stat block — this makes the one
  piece of information the client most wanted included also the visual
  centerpiece of the page, and gives the design a genuine reason for its
  one bold move instead of a decorative default.
- Typography: pair a bold, condensed/industrial display face (signage,
  stencil, or heavy grotesk register — matching the flyer's blocky
  headline feel) with a clean, legible body face, and consider a
  monospace/utility face specifically for the measurement callouts and
  phone numbers (reinforces the "precise, technical, trustworthy" feel).
- Avoid the generic AI-design defaults: no cream-background/terracotta-accent
  look, no near-black-with-neon-accent look, no broadsheet/newspaper-hairline
  look — none of those fit a working-class local logistics business anyway.
- Use the real truck photo as the hero image, not a stock illustration.
- Keep it to one real risk, executed well, everywhere else disciplined and
  quiet — this is a trust-driven local service business, not a flashy
  startup landing page; overly elaborate motion or decoration would work
  against the brief.

## Page structure (content only, don't add beyond this)

1. Hero — company name, tagline, truck photo, primary phone CTA
   (`tel:` link), short one-line value proposition grounded in the client's
   own words (evden eve / şehirler arası nakliyat).
2. Services — the itemized list above, manifest/waybill styled.
3. Cargo box dimensions — the spec-diagram signature section, with the
   placeholder clearly marked as noted above.
4. Trust/guarantees — eşyaya özenli taşıma, güvenli taşıma garantisi, uzman
   ekip, zamanında teslimat (from the flyer, all consistent with the chat).
5. Contact — both phone numbers (one real, one placeholder as noted),
   `tel:` links, large tap targets, WhatsApp link using the known number.
6. Footer — company name, service area (Karamanlı / Burdur and
   intercity), phone number repeated.

## Deliverable

A single HTML file (plus the truck image as a separate asset file
referenced by a relative path) ready to preview and, once the two
placeholders are filled in with real data, ready to deploy as-is.