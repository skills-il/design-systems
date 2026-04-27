---
name: Kibbutz
version: 0.2.2
description: 1950s Bezalel poster collectivism, Hebrew-first. Wheat cream, olive ink, dry working palette. Communal, idealistic, hand-set.
colors:
  primary: "#2D2A1F"
  surface: "#F5EFD8"
  tertiary: "#3E5524"
  on-primary: "#F5EFD8"
  on-surface: "#2D2A1F"
  on-tertiary: "#F5EFD8"
  surface-container: "#DDD0AE"
colors-dark:
  primary: "#F5EFD8"
  surface: "#2D2A1F"
  tertiary: "#6B8836"
  on-primary: "#2D2A1F"
  on-surface: "#F5EFD8"
  on-tertiary: "#F5EFD8"
  surface-container: "#3E3B2C"
typography:
  body-lg:
    fontSize: 18px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.6
  body-md:
    fontSize: 16px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.6
  body-sm:
    fontSize: 14px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.55
  label-sm:
    fontSize: 12px
    fontFamily: Assistant, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0.12em
  headline-lg:
    fontSize: 38px
    fontFamily: Assistant, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.15
  headline-md:
    fontSize: 26px
    fontFamily: Assistant, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.25
  headline-display:
    fontSize: 60px
    fontFamily: Assistant, Heebo, sans-serif
    fontWeight: 800
    lineHeight: 1.05
    letterSpacing: -0.02em
spacing:
  lg: 28px
  md: 18px
  sm: 10px
  xl: 44px
  xs: 6px
  2xl: 72px
rounded:
  lg: 16px
  md: 8px
  sm: 4px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.lg}"
    elevation: none
    textColor: "{colors.on-surface}"
    borderWidth: 2px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 10px 14px
    rounded: "{rounded.sm}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-ghost:
    padding: 12px 20px
    rounded: "{rounded.sm}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 12px 22px
    rounded: "{rounded.lg}"
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
---

## Overview

Kibbutz draws from mid-century Bezalel poster art, Yohanan Simon, Asher Hoffman, the cooperative-press aesthetic of the early state. Hand-set type, dry earth palette, poster-flat colors, no shadow. Use Kibbutz for civic-cultural surfaces, museum sites, agricultural co-ops, education, anything with a long memory.

Hebrew-first. Assistant carries display sizes, its humanist sans feel matches the printed-poster character without going kitsch. Heebo carries body. Both bilingual; Latin glyphs match optical weight cleanly.

## Colors

Earth-stained working palette.

- **Primary (#2D2A1F)**: olive-warm ink, the kind a 60-year-old screenprint settles into.
- **On primary (#F5EFD8)**: wheat cream sitting on top of primary.
- **Surface (#F5EFD8)**: wheat cream, the poster paper.
- **On surface (#2D2A1F)**: ink on paper.
- **Surface container (#DDD0AE)**: faded poster background tone, for cards and callouts.
- **Accent (#3E5524)**: deep kibbutz olive, the green of irrigated fields at noon, deepened so it carries on a button without fading into the cream surround.
- **On accent (#F5EFD8)**: cream on olive.

The palette is intentionally muted. If you find yourself reaching for a brighter green, you're outside the system, pick a different system instead.

## Typography

Assistant for display gives Kibbutz its hand-set character. Heebo for body keeps the system bilingual and readable. Both pair without optical break across scripts.

Display tracking is slightly tightened (-0.02em). Body line-height holds at 1.6 for both Hebrew and English.

## Layout

Poster-grid sensibility. 8 point base, container padding 16 on mobile, 64 on desktop. Cards align on a strict 12-column grid; no off-grid floats. The system rewards alignment; misalignment reads as carelessness.

Use logical properties throughout, Kibbutz was authored Hebrew-first but flips cleanly.

## Elevation & Depth

None. Posters do not have shadows; neither does this system. Distinguish layers by tone (`surface` vs `surface-container`) and by 1-pixel ink rules. If you need a card to "lift," tighten its padding instead.

## Shapes

Minimal rounding. 2-pixel radius on buttons, inputs, and chips; 4 pixels on cards. The system is intentionally hard-edged, softness reads as digital and breaks the print metaphor.

## Components

- **Buttons**: primary fills with olive, cream text, 2-pixel rounding. Ghost is cream with an ink border. Hover on primary swaps to ink fill, the olive recedes, the depth steps forward.
- **Cards**: surface-container background, 4-pixel rounding, 24-pixel internal padding. Heading separates from body with a single 1-pixel ink rule, full-width, on the inline-start side.
- **Inputs**: cream background, 1-pixel ink border, 2-pixel rounding, 16-pixel body. Focus ring is a 2-pixel olive outline.

## Do's and Don'ts

Do let the wheat cream carry. Avoid pure white anywhere, it fights the posters.
Do align everything to the 8-point grid. The system rewards discipline.
Do use the olive for one primary action per page; demote secondaries to ghost.

Don't add gradients, shadows, or glass. Posters are flat or they're not posters.
Don't introduce a brighter green. The dryness is the point.
Don't use Hebrew script in italics, it reads as forced.

## Localization

Kibbutz is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

### RTL behavior

- **Text alignment**: default to logical `start` for headlines, body, labels, and lists (right in RTL). Use `center` only for hero subheads and standalone CTA labels. Never hardcode `text-align: left` or `right`.
- **Asymmetric grids mirror**: an "image | text" hero in LTR puts the image on the left; in RTL the image goes on the right (start side). Order via DOM, never via `order` properties; the document order should read naturally in both directions.
- **Button stacks**: primary action goes on the start side (right in RTL); secondary follows toward the end. A "Save | Cancel" pair reads "שמור | ביטול" with שמור on the right.
- **Direction-aware glyphs**: CTA arrows (`←` RTL / `→` LTR), chevrons in disclosure widgets, breadcrumb separators (`›` flips), pagination next/prev, undo/redo, send-message icons. Use `transform: scaleX(-1)` for asymmetric icons or maintain dual SVGs.
- **Drawers and side sheets**: slide in from the start side (right in RTL).
- **Modal close button**: end side (left in RTL), matching Hebrew/Arabic OS convention.
- **Steppers and wizards**: step 1 anchors on the start side (right in RTL); the progress bar fills from start to end (right-to-left).
- **Pagination**: page 1 on the start side; "next" arrow points toward the end (left in RTL).
- **Tables**: first column anchors on the start side. Numeric columns may stay LTR via `<bdi>`-wrapped cells while the table itself flows RTL.
- **Logical CSS only**: `padding-inline-start`, `margin-inline-end`, `inset-inline-start`. Tailwind: `ps-*`, `me-*`, `start-*`. Never `padding-left`, `left:`, `ml-*`.

### Hebrew typography overrides

- **Letter-spacing override**: `headline-display.letterSpacing` is `-0.02em`. Apply this to Latin runs only. For Hebrew display text, override to `0`. Hebrew letterforms have no Latin-style ascenders/descenders, so negative tracking visually crowds them and hurts legibility.
- **Display line-height**: `headline-display.lineHeight` is `1.05`. Hebrew descenders (ק, ץ, ן) clash with the next line at this density. Override to `1.15` minimum for Hebrew display text.
- **font-feature-settings**: keep `kern` and `calt` enabled on every text node. Frank Ruhl Libre's contextual alternates and the kerning table for Heebo/Assistant are needed for proper Hebrew rendering. Never set `font-feature-settings: normal` globally.

### Bidirectional (BiDi) handling

- **Wrap mixed-direction inline content in `<bdi>`**: numerals inside Hebrew flow ("1,200 ₪", "85 מ״ר"), phone numbers ("052-123-4567"), Israeli ID numbers, version strings, file paths, code identifiers. Without `<bdi>` the Unicode BiDi algorithm reorders unpredictably.
- **Code, URLs, and email addresses stay LTR** even inside RTL pages. Wrap with `<bdi>` or apply `direction: ltr` on the containing element. Never let an `@`, `/`, or `.` flip across BiDi boundaries.
- **User-input fields**: apply `unicode-bidi: plaintext` so the typed direction follows the content (a Hebrew name and a Latin URL render correctly in the same input).
- **Code blocks**: `<pre>` and `<code>` always `direction: ltr; text-align: start` even on RTL pages.

### Punctuation

- **Quote marks**: gershayim ״ (U+05F4) for double-quote in Hebrew abbreviations (e.g., צה״ל, ארה״ב). Geresh ׳ (U+05F3) for single-quote and Hebrew apostrophe. Never use ASCII `"` or `'` in Hebrew.
- **Hyphens in compound Hebrew words**: maqaf ־ (U+05BE), not ASCII hyphen. ASCII hyphen is fine inside code spans and Latin-only runs.
- **Em dashes**: never. Use commas, parentheses, periods, or colons instead. This rule is system-wide, not Hebrew-only.
- **Latin runs inside Hebrew**: standard ASCII punctuation works (commas, periods, parens). The mixed-direction display is handled by BiDi.

### Numbers, dates, currency, identifiers

- **Date format (numeric)**: `dd/mm/yyyy` (Israeli convention, not US `mm/dd/yyyy`).
- **Date format (long-form Hebrew)**: `dd ב‎MMMM yyyy` (note the prefix ב for "in", e.g. "12 ביוני 2026"). Hebrew month names: ינואר, פברואר, מרץ, אפריל, מאי, יוני, יולי, אוגוסט, ספטמבר, אוקטובר, נובמבר, דצמבר.
- **Time format**: 24-hour (`14:30`). AM/PM is wrong in Israeli context.
- **Currency**: ₪ (NIS) symbol AFTER the amount with a space: `1,200 ₪`, not `₪1,200`. Use `ש"ח` interchangeably; pick one per surface and stay consistent.
- **Phone numbers**: `0X-XXX-XXXX` for landlines (`03-1234567`), `05X-XXX-XXXX` for mobile (`052-123-4567`). Always wrap in `<bdi>`.
- **Israeli ID (תעודת זהות, ת.ז.)**: 9 digits, displayed LTR-wrapped: `<bdi>123456789</bdi>`. Never break with hyphens or spaces.
- **Week start**: Sunday (יום ראשון), not Monday. Affects calendar pickers, weekly summaries, and day-of-week labels.
- **Hebrew calendar**: surface alongside Gregorian for ceremonial or holiday-aware contexts (Friday Dusk, Mizrach). Format: `ב׳ תשרי תשפ״ז`.

### Accessibility (Hebrew-specific)

- **`<html lang="he" dir="rtl">`**: both attributes required on every Hebrew page. Screen readers use `lang` to pick the Hebrew voice; layout uses `dir` for direction.
- **Inline language switching**: wrap Latin spans inside Hebrew flow with `<span lang="en">` so screen readers switch voices mid-sentence. Especially important for proper nouns and brand names.
- **aria-labels in Hebrew**: author them in Hebrew at build time; never machine-translate at runtime. A button with Hebrew visible text needs a Hebrew `aria-label`, not the English equivalent.
- **Skip links in Hebrew**: "דלג לתוכן הראשי" (skip to main content), "דלג לניווט" (skip to navigation). Position: top-start (top-right in RTL).
- **Focus order matches visual order**: in RTL the visual reading order is right-to-left, so the keyboard tab order should follow the same path.

### Forms

- **Field labels**: top-aligned by default; if inline, label is on the start side (right in RTL).
- **Placeholder alignment**: start-aligned (right in RTL); never center-align placeholders in inputs.
- **Caret position**: appears at the visual end of typed text. Handled automatically by the browser when `dir` is set correctly on the input or its container.
- **Required-field indicator**: asterisk `*` AFTER the label in RTL ("שם מלא *", not "* שם מלא").
- **Error messages**: rendered below the field, start-aligned (right in RTL). Voice: address the user directly and explain how to fix ("הדוא״ל אינו תקין. נסו שוב במבנה name@example.com"), not "Invalid input".
- **Phone, ID, postcode inputs**: set `inputmode="numeric"` and `pattern` for native keyboard; wrap displayed values in `<bdi>`.

### Cultural notes

For community-oriented surfaces, use plural inclusive forms ("נצטרף", "נחליט") rather than singular imperative ("הצטרפו", "החליטו"). The kibbutz voice is collective, not directive.

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: עבודה שקטה, ביחד.
- **EN**: Quiet work, shared.

### Primary CTA

- **HE**: הצטרפו למעגל
- **EN**: Join the circle

### Error message

- **HE**: לא הצלחנו לשמור. חכו רגע ונסו שוב.
- **EN**: We could not save your changes. Wait a moment and try again.
