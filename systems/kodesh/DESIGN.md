---
name: Kodesh
version: 0.2.2
description: Sacred Hebrew manuscript gravity, Hebrew-first. Parchment surface, manuscript ink, gilt accent. Reverent, traditional, still.
colors:
  primary: "#1B1612"
  surface: "#F2E8CF"
  tertiary: "#6F5520"
  on-primary: "#F2E8CF"
  on-surface: "#1B1612"
  on-tertiary: "#F2E8CF"
  surface-container: "#E5D7AC"
colors-dark:
  primary: "#F2E8CF"
  surface: "#1B1612"
  tertiary: "#B8923D"
  on-primary: "#1B1612"
  on-surface: "#F2E8CF"
  on-tertiary: "#1B1612"
  surface-container: "#2A2218"
typography:
  body-lg:
    fontSize: 19px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.85
  body-md:
    fontSize: 17px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.85
  body-sm:
    fontSize: 15px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.7
  label-sm:
    fontSize: 12px
    fontFamily: Heebo, sans-serif
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.14em
  headline-lg:
    fontSize: 40px
    fontFamily: Frank Ruhl Libre, Heebo, serif
    fontWeight: 700
    lineHeight: 1.2
  headline-md:
    fontSize: 26px
    fontFamily: Frank Ruhl Libre, Heebo, serif
    fontWeight: 700
    lineHeight: 1.3
  headline-display:
    fontSize: 60px
    fontFamily: Frank Ruhl Libre, Heebo, serif
    fontWeight: 700
    lineHeight: 1.15
spacing:
  lg: 40px
  md: 24px
  sm: 14px
  xl: 64px
  xs: 8px
  2xl: 104px
rounded:
  lg: 4px
  md: 2px
  sm: 0px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.md}"
    elevation: none
    textColor: "{colors.on-surface}"
    borderWidth: 1px
    backgroundColor: "{colors.surface}"
  input:
    padding: 12px 16px
    rounded: "{rounded.none}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-ghost:
    padding: 12px 22px
    rounded: "{rounded.none}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 14px 28px
    rounded: 2px
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
---

## Overview

Kodesh draws from the Hebrew manuscript tradition, parchment, square Hebrew letters, the gilt page edge of a 15th-century prayer book. Reverent without ornament. Use Kodesh for prayer apps, religious-text study, archive surfaces, anything that should feel like it has been carefully copied by hand.

Hebrew-first by definition. Frank Ruhl Libre carries every display and headline size, its modern Hebrew serif is descended directly from the manuscript tradition. Heebo carries body, including nikkud-heavy passages.

## Colors

Manuscript palette. Every color earns its place.

- **Primary (#1B1612)**: manuscript ink, slightly warm, never pure black.
- **On primary (#F2E8CF)**: parchment cream sitting on ink.
- **Surface (#F2E8CF)**: parchment, the page itself.
- **On surface (#1B1612)**: ink on parchment.
- **Surface container (#E5D7AC)**: aged parchment, slightly deeper, for chapter dividers and citation panels.
- **Accent (#6F5520)**: gilt, soft gold leaf, never bright. Reserved for chapter marks, primary CTAs, and the single page-edge stripe.
- **On accent (#F2E8CF)**: parchment on gilt.

The palette is intentionally narrow. If you need to introduce a "color" for status (warning, error), demote it to a 1-pixel ink rule with text below, never tint the parchment.

## Typography

Frank Ruhl Libre is the load-bearing face. Display, headline, and any prominent prose use it; the system was built around its modern Hebrew serif. Heebo carries body, with nikkud-aware metrics.

Body line-height runs 1.85, wide enough to carry niqqud comfortably without the page feeling sparse. The system never goes below 16-pixel body.

## Layout

Single-column long-form. 8 point base, container padding 24 on mobile, 64 on desktop. Long-form text is constrained to a 60-character measure (about 660px at body-lg). Side notes and citations use surface-container with a 2-pixel ink border-inline-start.

Logical properties throughout. Hebrew is the primary direction; English citations flow cleanly when isolated.

## Elevation & Depth

None. Manuscripts do not float. Hierarchy comes from typography (size, weight, position), tone (`surface` vs `surface-container`), and 1-pixel ink rules.

## Shapes

Sharp. Buttons and inputs are 0-radius. Cards round to 2 pixels at most. Avatars are circular only when avatars are necessary; otherwise prefer initials in a 2-pixel rounded square.

## Components

- **Buttons**: primary fills with gilt, parchment text, no rounding, no shadow. Ghost is parchment with ink border. Hover on primary swaps to ink fill, the gilt recedes, the depth steps forward.
- **Cards**: surface-container background, 2-pixel rounding, 24-pixel padding. Citation panels carry a 2-pixel ink border-inline-start. No shadows.
- **Inputs**: parchment background, 1-pixel ink border, 0 rounding, 17-pixel body-md. Focus ring is a 2-pixel gilt outline-offset.

## Do's and Don'ts

Do constrain text measure. Manuscripts read column-by-column, not edge-to-edge.
Do use the gilt sparingly, once per page, ideally on the chapter mark or primary CTA.
Do let typography carry the hierarchy. Frank Ruhl at headline weight is enough.

Don't reach for sans-serif headlines. The whole system is built around the serif.
Don't introduce decorative color. The parchment, ink, and gilt are the entire palette.
Don't soften the rounding to look modern, the sharpness is the gravity.

## Localization

Kodesh is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

For religious/educational content: prefer Hebrew calendar dates alongside Gregorian (e.g., "ב׳ תשרי תשפ״ז · 14 בספטמבר 2026"). When citing texts, follow Hebrew citation conventions: ספר, פרק, פסוק (Book, Chapter, Verse) rather than the Latin pattern.

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: מלאכה של קודש, שנכתבת בכוונה.
- **EN**: Sacred work, set down with care.

### Primary CTA

- **HE**: פתחו ללימוד
- **EN**: Begin the study

### Error message

- **HE**: הטקסט לא נטען. רעננו ונסו שוב.
- **EN**: The text could not be loaded. Refresh and try again.
