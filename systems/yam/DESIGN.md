---
name: Coast
version: 0.1.2
description: Tel Aviv Mediterranean. Bone-white surfaces, deep ocean primary, warm sand secondary, sea-foam accent.
colors:
  primary: "#1E5F8C"
  surface: "#F9F4E8"
  tertiary: "#5BA8B8"
  secondary: "#D4906B"
  on-primary: "#F9F4E8"
  on-surface: "#2A3540"
  on-tertiary: "#FFFFFF"
  on-secondary: "#FFFFFF"
  surface-container: "#FFFFFF"
colors-dark:
  primary: "#76B5D9"
  surface: "#0A1828"
  tertiary: "#7DC4CE"
  secondary: "#E8B795"
  on-primary: "#0A1828"
  on-surface: "#F9F4E8"
  on-tertiary: "#0A1828"
  on-secondary: "#0A1828"
  surface-container: "#142A40"
typography:
  body-lg:
    fontSize: 17px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.7
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
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.12em
  headline-lg:
    fontSize: 40px
    fontFamily: Frank Ruhl Libre, serif
    fontWeight: 600
    lineHeight: 1.15
  headline-md:
    fontSize: 26px
    fontFamily: Frank Ruhl Libre, serif
    fontWeight: 600
    lineHeight: 1.25
  headline-display:
    fontSize: 64px
    fontFamily: Frank Ruhl Libre, serif
    fontWeight: 400
    lineHeight: 1.1
    letterSpacing: -0.01em
spacing:
  lg: 32px
  md: 20px
  sm: 12px
  xl: 52px
  xs: 6px
  2xl: 88px
rounded:
  lg: 24px
  md: 16px
  sm: 8px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.lg}"
    elevation: 0 16px 40px rgba(30,95,140,0.12)
    textColor: "{colors.on-surface}"
    borderWidth: 0px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 12px 18px
    rounded: 9999px
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 12px 28px
    rounded: 9999px
    textColor: "{colors.on-primary}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-tertiary}"
    backgroundColor: "{colors.tertiary}"
---

## Overview

Coast is a Mediterranean design system rooted in Tel Aviv's particular light: bone-white limestone, ocean blue, warm sand, sea-foam shadows under a 2pm sun. Editorial in tone, hospitable in spacing, photo-friendly in chrome.

Use Coast for hospitality (boutique hotels, restaurants, wineries), travel editorial, lifestyle commerce, beach-adjacent SaaS. Wrong for transactional gov surfaces, news portals, dense classifieds.

## Colors

Primary `#1E5F8C` deep ocean, headlines, primary CTAs, navigation. Secondary `#D4906B` warm terracotta sand for accents. Tertiary `#5BA8B8` turquoise sea-foam, hover state on primary buttons (transitions ocean → seafoam). Surface `#F9F4E8` bone-white limestone. Surface-container `#FFFFFF` for actual cards, white-on-bone gives the soft contrast Tel Aviv stucco walls have at midday.

## Typography

Two families. Display uses Frank Ruhl Libre, modern Hebrew serif with optical Latin coverage, weight 400 at 64px gives editorial gravitas. Body uses Heebo for both scripts, generous 1.7 line-height for long-form reading flow. The serif/sans contrast is intentional, Frank Ruhl on a hero against Heebo body reads like a magazine layout.

## Layout

Airy by default. `lg: 32px`, `xl: 52px`, `2xl: 88px`. Hero sections breathe. Image-led layouts with full-bleed photos and asymmetric text columns.

## Shapes

Soft and rounded. `lg: 24px` on cards, `9999px` (full pill) on buttons and search inputs. The pill is essential, it's the visual signature that separates Coast from every other Hebrew system.

## Components

Buttons: ocean primary, full pill, 12/28 padding. Hover transitions to seafoam under 120ms. Cards: white on bone, no border, 24px corners. Shadow is the chrome: `0 16px 40px rgba(30,95,140,0.12)`, diffused, ocean-tinted. Inputs: bone surface, full pill, 12/18 padding.

## Localization

Coast is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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
- **Display weight floor**: Frank Ruhl Libre at weight `400` reads thin in Hebrew at display sizes. Override to `500` minimum for Hebrew display text; Latin can stay at the lower weight.
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

Hospitality and travel: check-in/check-out times follow Israeli convention (typically 15:00 / 11:00). Hebrew long-form dates: "12 ביוני 2026" (note the prefix ב for "in"). For booking surfaces, the Israeli weekend is Friday and Saturday (not Saturday and Sunday).

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: אור של ים, אחר צהריים שקט.
- **EN**: Sea light, slow afternoon.

### Primary CTA

- **HE**: שמרו את החדר
- **EN**: Reserve the room

### Error message

- **HE**: אין זמינות בתאריכים האלה. לבחור שבוע אחר?
- **EN**: No availability for these dates. Pick a different week?
