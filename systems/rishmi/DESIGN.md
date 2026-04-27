---
name: Official
version: 0.2.2
description: Israeli civic services with a clean redesign, Hebrew-first. White surface, charcoal-black ink, Israeli-flag blue accent. Trustworthy, accessible, neutral.
colors:
  primary: "#11151C"
  surface: "#FFFFFF"
  tertiary: "#0038B8"
  on-primary: "#FFFFFF"
  on-surface: "#11151C"
  on-tertiary: "#FFFFFF"
  surface-container: "#F0F2F5"
colors-dark:
  primary: "#FFFFFF"
  surface: "#11151C"
  tertiary: "#4B85FF"
  on-primary: "#11151C"
  on-surface: "#FFFFFF"
  on-tertiary: "#FFFFFF"
  surface-container: "#1B2230"
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
    lineHeight: 1.65
  body-sm:
    fontSize: 14px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.55
  label-sm:
    fontSize: 12px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0.1em
  headline-lg:
    fontSize: 36px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.15
    letterSpacing: -0.01em
  headline-md:
    fontSize: 24px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.25
  headline-display:
    fontSize: 56px
    fontFamily: Heebo, sans-serif
    fontWeight: 800
    lineHeight: 1.1
    letterSpacing: -0.02em
spacing:
  lg: 24px
  md: 16px
  sm: 8px
  xl: 40px
  xs: 4px
  2xl: 64px
rounded:
  lg: 8px
  md: 6px
  sm: 4px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.md}"
    elevation: 0 1px 2px rgba(0,0,0,0.05)
    textColor: "{colors.on-surface}"
    borderWidth: 1px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 12px 14px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-ghost:
    padding: 12px 20px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 10px 20px
    rounded: "{rounded.md}"
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
---

## Overview

Rishmi is a civic-services system with the polish of a competent redesign. White surface, deep navy text, Israeli-flag blue accent. Use Rishmi for government and municipal portals, healthcare and legal services, financial regulation surfaces, anything that needs to be trusted on first read.

Hebrew-first. Heebo carries every size, display, headline, body, including all Latin glyphs. A citizen's form should not require two fonts to communicate, so the Latin fallback was intentionally removed; Heebo's Latin character set is sufficient for every English string the system renders.

## Colors

Three working colors plus a cool surface-container.

- **Primary (#11151C)**: charcoal-black, the trust color. Body text, inverted CTAs, headers. Black-rather-than-navy keeps Rishmi visually distinct from SaaS systems that use navy as their primary, citizens reading a tax form recognize ink-on-paper register, not enterprise polish.
- **On primary (#FFFFFF)**: pure white sitting on primary.
- **Surface (#FFFFFF)**: clean white, the page.
- **On surface (#11151C)**: charcoal on white.
- **Surface container (#F0F2F5)**: warm-neutral light gray, for cards, form sections, and the footer area. Slightly warmer than a pure-blue tint to soften the form chrome.
- **Accent (#0038B8)**: Israeli flag blue, the primary attention-getter. CTAs, links, focus rings, error highlights are derived from it. The contrast against charcoal text, flag-blue button next to ink-black headline, is sharper than the prior navy-on-navy combination, which read as a single tonal block.
- **On accent (#FFFFFF)**: white on accent.

The accent is a saturated, official blue, not a SaaS marketing blue. Citizens recognize it. Don't soften it toward teal or push it toward purple.

## Typography

Heebo as a single workhorse. The system uses weight (400 / 700 / 800) more aggressively than other systems to carry hierarchy without color or shape. Heebo's Latin character set is sufficient for every English string the system renders, no Latin fallback is needed and adding one would only introduce font-swap shimmer mid-form.

Body line-height stays at 1.65, generous for form-heavy pages, conservative enough to keep dense regulatory copy from feeling sparse.

## Layout

Form-friendly. 8 point base, container padding 16 on mobile, 40 on desktop. Form fields stack vertically by default; never put two inputs on one row on mobile. Help text sits below each input at body-sm in a slightly muted tone, never above.

Logical properties throughout. The system was authored Hebrew-first; English flows cleanly through the same shapes.

## Elevation & Depth

Minimal. Cards rest on `surface-container` rather than casting shadow. Where elevation is required (modals, dropdowns), use a single soft shadow `0 4px 12px rgba(10, 37, 64, 0.08)`. No glass effects, no gradients.

## Shapes

Restrained rounding. 6 pixels on inputs and buttons, 8 pixels on cards. Sharper corners read as 1990s government and miss the "redesigned, trustworthy" mood. Don't go past 8 pixels, that direction reads as consumer-product.

## Components

- **Buttons**: primary fills with Israeli blue and white text, 6-pixel rounding. Ghost is white with navy outline. Hover on primary deepens to navy fill. Disabled buttons go to 40% opacity with `cursor: not-allowed`.
- **Cards**: surface-container background, 8-pixel rounding, 24-pixel padding, no border. Form sections use cards with a navy headline at headline-md.
- **Inputs**: white background, 1-pixel navy border at 0.3 alpha, 6-pixel rounding, 16-pixel body. Focus ring is a 2-pixel accent outline plus a `0 0 0 3px rgba(0, 56, 184, 0.2)` halo. Error state swaps the border to a desaturated red and the focus halo to a red derivative.

## Do's and Don'ts

Do label every form field above the input, never use placeholder-as-label, even on mobile.
Do meet AA contrast on every component, including disabled states. The system serves citizens with a wide accessibility range.
Do use the Israeli-flag blue sparingly, primary CTAs only, plus inline links.

Don't introduce a marketing accent (orange, green, purple). The system is civic, not promotional.
Don't reach for decorative typography. Heebo at the right weight is enough.
Don't compress padding to fit more on the screen. Government forms reward whitespace.

## Localization

Official is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

Official documents and forms: same formal-Hebrew rules as memshala. Required fields marked with אסטריסק (*) AFTER the label in RTL ("שם מלא *", not "* שם מלא"). Document numbers (מס' אסמכתא, מס' תיק) shown LTR-wrapped.

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: רשומה רשמית, נשמרת בקפידה.
- **EN**: Official record, carefully kept.

### Primary CTA

- **HE**: הגישו את הטופס
- **EN**: Submit the form

### Error message

- **HE**: הטופס נדחה. בדקו את השדות המסומנים.
- **EN**: Form rejected. Please check the highlighted fields.
