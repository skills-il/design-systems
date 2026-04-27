---
name: Bauhaus
version: 0.2.3
description: White City modernism, Hebrew-first. Cream paper, black ink, single red ochre accent. Authoritative, quiet, civic.
colors:
  primary: "#1A1A18"
  surface: "#F3EEE3"
  tertiary: "#A13A2A"
  on-primary: "#F3EEE3"
  on-surface: "#1A1A18"
  on-tertiary: "#F3EEE3"
  surface-container: "#EAE3D2"
colors-dark:
  primary: "#F3EEE3"
  surface: "#1A1A18"
  tertiary: "#C44B36"
  on-primary: "#1A1A18"
  on-surface: "#F3EEE3"
  on-tertiary: "#F3EEE3"
  surface-container: "#25231F"
typography:
  body-lg:
    fontSize: 18px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.55
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
    fontFamily: Heebo, sans-serif
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.12em
  headline-lg:
    fontSize: 48px
    fontFamily: Frank Ruhl Libre, Public Sans, serif
    fontWeight: 700
    lineHeight: 1.1
    letterSpacing: -0.01em
  headline-md:
    fontSize: 32px
    fontFamily: Frank Ruhl Libre, Public Sans, serif
    fontWeight: 600
    lineHeight: 1.2
  headline-display:
    fontSize: 72px
    fontFamily: Frank Ruhl Libre, Public Sans, serif
    fontWeight: 700
    lineHeight: 1.05
    letterSpacing: -0.02em
spacing:
  lg: 20px
  md: 12px
  sm: 8px
  xl: 32px
  xs: 4px
  2xl: 56px
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
    borderWidth: 1.5px
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
    padding: 10px 18px
    rounded: 0px
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
---

## Overview

Architectural minimalism meets journalistic gravitas. The UI evokes a premium matte finish, a contemporary gallery wall, the White City's stucco facades at noon. Use Bauhaus for civic platforms, editorial products, government services, and any surface that needs to feel permanent instead of trendy.

Bauhaus is built Hebrew-first. Every font stack leads with a Hebrew-capable family so Hebrew content renders with optically-matched metrics; Latin glyphs fall through cleanly when the leading font ships them (Heebo and Frank Ruhl Libre both do).

## Colors

High-contrast neutrals with a single red-ochre driver.

- **Primary (#1A1A18)**: deep near-black for headlines, core text, and hover states.
- **On primary (#F3EEE3)**: cream that sits on top of primary when the role inverts.
- **Surface (#F3EEE3)**: warm limestone, softer than pure white, carries the page.
- **On surface (#1A1A18)**: text color on top of surface and surface-container.
- **Surface container (#EAE3D2)**: one step deeper, for cards, sidebars, quote blocks.
- **Accent (#A13A2A)**: Boston Clay, the sole driver for calls to action. Never decorative.
- **On accent (#F3EEE3)**: cream sitting on the accent fill.

Never introduce a second accent. If you need to separate two actions, demote one to ghost.

## Typography

Two families carry the whole system.

- **Display and headlines** pair Frank Ruhl Libre (Hebrew) with Public Sans (Latin) as the fallback. Frank Ruhl is a modern Hebrew serif at display sizes; Public Sans covers Latin with matching optical weight.
- **Body** uses Heebo for both scripts. Heebo is bilingual by design and ships crisp Latin glyphs, so a single body family works across Hebrew and English without a kerning break.

Leading runs generous (1.55 to 1.6 for body) to accommodate Hebrew descenders without tightening Latin lines.

## Layout

Respect the grid. 8 point spacing scale, container padding 24 pixels on mobile, 64 on desktop. Start-rail navigation on desktop when the surface is a dashboard (right rail in RTL, left rail in LTR); stacked otherwise. Use logical properties (`padding-inline-start`, `inset-inline-end`) throughout, the system must render identically when `dir` flips.

## Elevation & Depth

None. Bauhaus is intentionally flat. Distinguish surfaces with the surface and surface-container tones, not with shadows. If you need hierarchy, tighten a border or add whitespace.

## Shapes

Minimal rounding. 2 pixel radius on inputs and buttons; 4 pixels on cards and panels. Never circular except for avatars.

## Components

- **Buttons**: primary uses accent background with cream text; ghost uses transparent background with ink outline; no shadows, no gradients. Hover swaps the accent fill to ink for a dramatic but monochrome shift.
- **Cards**: surface-container background, 4 pixel radius, no shadow, 24 pixels of internal padding. Header separates from body with a single 1-pixel border in the on-surface tone, never with whitespace alone.
- **Inputs**: surface background, 1-pixel on-surface border, 2 pixel radius, 14 pixel body-md typography. Focus ring is a 2-pixel accent outline.

## Do's and Don'ts

Do pair headlines with generous whitespace and hold the reader at the top.
Do let the accent rest. One CTA per viewport.
Do use all-caps labels sparingly, only for category chips and overlines.

Don't add a secondary accent. Demote actions instead.
Don't use shadows, gradients, or glass. This system is flat by definition.
Don't reach for emoji or illustration for decoration. Let the type carry the mood.

## Localization

Bauhaus is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: בהירות אזרחית. צבע אחד, בלי קישוטים.
- **EN**: Civic clarity. One color, no decoration.

### Primary CTA

- **HE**: המשך
- **EN**: Continue

### Error message

- **HE**: שדה חובה. נא למלא.
- **EN**: Required field. Please fill it in.
