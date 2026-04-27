---
name: Broadsheet
version: 0.2.2
description: Hebrew newspaper editorial gravity. Newsprint cream, deep ink, indigo signature accent. Columnar, considered, literary.
colors:
  primary: "#14171F"
  surface: "#F8F4EC"
  tertiary: "#2C4F8F"
  on-primary: "#F8F4EC"
  on-surface: "#14171F"
  on-tertiary: "#F8F4EC"
  surface-container: "#ECE5D5"
colors-dark:
  primary: "#F8F4EC"
  surface: "#14171F"
  tertiary: "#5478C8"
  on-primary: "#14171F"
  on-surface: "#F8F4EC"
  on-tertiary: "#F8F4EC"
  surface-container: "#1F2330"
typography:
  body-lg:
    fontSize: 18px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.65
  body-md:
    fontSize: 16px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.7
  body-sm:
    fontSize: 14px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.6
  label-sm:
    fontSize: 11px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0.14em
  headline-lg:
    fontSize: 40px
    fontFamily: Alef, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.15
  headline-md:
    fontSize: 26px
    fontFamily: Alef, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.25
  headline-display:
    fontSize: 60px
    fontFamily: Alef, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.1
    letterSpacing: -0.01em
spacing:
  lg: 32px
  md: 20px
  sm: 8px
  xl: 56px
  xs: 4px
  2xl: 96px
rounded:
  lg: 2px
  md: 0px
  sm: 0px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: 0px
    elevation: none
    textColor: "{colors.on-surface}"
    borderWidth: 0px
    backgroundColor: "{colors.surface}"
  input:
    padding: 10px 14px
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
    padding: 12px 24px
    rounded: 0px
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
---

## Overview

Broadsheet draws from the printed Hebrew newspaper, Haaretz front pages, the cultural supplement on a Friday morning, the smell of newsprint and a third cup of coffee. Use Iton for long-form content surfaces: editorials, journals, knowledge bases, archives, anything that wants to be read slowly and trusted.

Hebrew-first by construction. Alef, a quietly classical Hebrew face, carries every display and headline size. Heebo carries body. Both ship matching Latin glyphs, so a citation in English doesn't break the column.

## Colors

Newsprint palette with one signature blue.

- **Primary (#14171F)**: deep newsprint ink, slightly warm.
- **On primary (#F8F4EC)**: paper cream that sits on the ink.
- **Surface (#F8F4EC)**: newsprint cream, the page itself.
- **On surface (#14171F)**: ink on the page.
- **Surface container (#ECE5D5)**: aged margin tone, for pull quotes, sidebars, and bylines.
- **Accent (#2C4F8F)**: signature indigo, the color the editor uses for corrections. CTAs and links.
- **On accent (#F8F4EC)**: cream on accent.

The accent is a deep, dignified blue, never a bright digital one. Iton is not trying to be modern; it's trying to be permanent.

## Typography

Alef is the workhorse for display. It reads as a calm, considered Hebrew face, book-like rather than monumental. Heebo handles every body size with generous line-height (1.65 to 1.7) so long-form columns breathe.

Display weight stays at 700; the system never goes thinner than 400 on body. Iton avoids hairline weights, they read as cosmetic rather than considered.

## Layout

Columnar. 8 point base, container padding 24 on mobile, 80 on desktop. Long-form content is constrained to a 65-character measure (roughly 720px at 18px body); never let articles run edge-to-edge. Sidebar pull quotes use surface-container with a 2-pixel accent border-inline-start.

Logical properties everywhere, the columns flip cleanly between RTL and LTR.

## Elevation & Depth

None. Iton is paper, and paper does not float. Distinguish surfaces with the cream and aged-margin tones, not with shadow. Use a 1-pixel ink rule between sections when whitespace alone is not enough.

## Shapes

Sharp. Buttons and inputs are 0-radius rectangles. Cards round to 2 pixels, barely perceptible, just enough to read as digital. Avatars stay circular.

## Components

- **Buttons**: primary uses signature indigo with cream text, no rounding, no shadow. Ghost uses cream with ink text and a 1-pixel ink border. Hover on primary swaps the indigo to ink. The motion is restrained.
- **Cards**: surface-container background, 2-pixel rounding, 24-pixel padding. Pull quotes use a 2-pixel border-inline-start in accent. No shadows.
- **Inputs**: cream background, 1-pixel ink border, 0 rounding, 16-pixel body-md. Focus ring is a 2-pixel indigo outline-offset.

## Do's and Don'ts

Do constrain text to a readable measure. Long lines break this system's promise.
Do use the indigo for links inline; underline on hover is sufficient.
Do let pull quotes do the visual work. They are the system's signature.

Don't reach for sans-serif display. Alef is the editorial voice.
Don't introduce a second accent. Iton has one editor's pen.
Don't soften the rounding. The corners are part of the gravity.

## Localization

Broadsheet is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

- **Letter-spacing override**: `headline-display.letterSpacing` is `-0.01em`. Apply this to Latin runs only. For Hebrew display text, override to `0`. Hebrew letterforms have no Latin-style ascenders/descenders, so negative tracking visually crowds them and hurts legibility.
- **Display line-height**: `headline-display.lineHeight` is `1.1`. Hebrew descenders (ק, ץ, ן) clash with the next line at this density. Override to `1.15` minimum for Hebrew display text.
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

For breaking-news pages, use the Hebrew expression "מתעדכן" rather than the English calque "מתעדכן בזמן אמת". The latter reads as "real-time update", which is a literal translation, not a Hebrew idiom.

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: הסיפור המלא.
- **EN**: The story, in full.

### Primary CTA

- **HE**: קראו עוד
- **EN**: Read on

### Error message

- **HE**: הכתבה לא נמצאה. נסו את החדשות האחרונות.
- **EN**: Article not found. Try our latest.
