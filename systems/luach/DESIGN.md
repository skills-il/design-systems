---
name: Bulletin
version: 0.1.3
description: Israeli classifieds utilitarian. Yellow-cream paper, ultra-dense list rows, square corners, prices in red.
colors:
  primary: "#1F1F1F"
  surface: "#FFFCEB"
  tertiary: "#D8001A"
  secondary: "#0061A8"
  on-primary: "#FFFCEB"
  on-surface: "#1F1F1F"
  on-tertiary: "#FFFFFF"
  on-secondary: "#FFFFFF"
  surface-container: "#FFFFFF"
colors-dark:
  primary: "#FFE066"
  surface: "#1A1A14"
  tertiary: "#FF6679"
  secondary: "#5BA8FF"
  on-primary: "#1F1F1F"
  on-surface: "#FFFCEB"
  on-tertiary: "#0A0A0A"
  on-secondary: "#0A0A0A"
  surface-container: "#262620"
typography:
  body-lg:
    fontSize: 15px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.5
  body-md:
    fontSize: 14px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.5
  body-sm:
    fontSize: 12px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.4
  label-sm:
    fontSize: 10px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0.06em
  headline-lg:
    fontSize: 24px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
  headline-md:
    fontSize: 18px
    fontFamily: Heebo, sans-serif
    fontWeight: 600
    lineHeight: 1.3
  headline-display:
    fontSize: 36px
    fontFamily: Heebo, sans-serif
    fontWeight: 800
    lineHeight: 1.1
spacing:
  lg: 12px
  md: 8px
  sm: 4px
  xl: 20px
  xs: 2px
  2xl: 32px
rounded:
  lg: 4px
  md: 2px
  sm: 2px
  none: 0px
components:
  card:
    padding: "{spacing.md}"
    rounded: 2px
    elevation: none
    textColor: "{colors.on-surface}"
    borderWidth: 1px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 6px 10px
    rounded: 2px
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 8px 14px
    rounded: 2px
    textColor: "{colors.on-primary}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.primary}"
---

## Overview

Bulletin is for surfaces that show lots of small things in rows: apartment listings, used cars, second-hand furniture, jobs, classifieds, marketplace inventory. Unmistakably Israeli classified-board, warm yellow-cream paper, white listing rows, blue links, red prices. Density is utility; decoration is friction.

## Colors

Primary `#1F1F1F` ink for body. Secondary `#0061A8` link blue for every clickable noun. Tertiary `#D8001A` prices and "discounted" markers, the eye locks onto it. Surface `#FFFCEB` cream-yellow paper carries the page; never replaced with pure white. Surface-container `#FFFFFF` for the listing rows themselves.

Dark mode flips the relationship: yellow becomes the bright primary tone (`#FFE066`), surfaces go warm-near-black.

## Typography

Heebo only. No display serif. Largest is 36px and that's already aggressive, most surfaces live at body-md (14px) or body-sm (12px). Density of information beats hierarchy of size. Tight line-heights (1.2-1.3 headings, 1.5 body).

## Layout

Ultra-tight spacing (`xs: 2, sm: 4, md: 8, lg: 12`). Listing rows have 8-12px vertical padding and a 1-pixel separator. Photo thumbnails are small (96-120px), description carries the listing.

## Shapes

Square or near-square. 2px corners on cards, buttons, inputs. Circular only on avatars.

## Components

Buttons: ink primary on cream, 2px corners. Cards (listing rows): white on cream, 1px border, 2px corners, 8-pixel internal padding. Hover lifts border to 24% opacity instead of adding shadow. Inputs: cream background with 1-pixel ink border.

## Localization

Bulletin is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

- **Display line-height**: `headline-display.lineHeight` is `1.1`. Hebrew descenders (ק, ץ, ן) clash with the next line at this density. Override to `1.15` minimum for Hebrew display text.
- **font-feature-settings**: keep `kern` and `calt` enabled on every text node. Frank Ruhl Libre's contextual alternates and the kerning table for Heebo/Assistant are needed for proper Hebrew rendering. Never set `font-feature-settings: normal` globally.
- **Body min-size**: `body-sm` is `12px`. Hebrew at this size loses legibility faster than Latin. Use `body-sm` for metadata and captions only; never for primary content. Body-md (`14px`) is the safe Hebrew body floor.

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

Classified-board phrasing: "יד שנייה" (second-hand), "במצב מצוין" (excellent condition), "מפרסם פרטי" (private seller), "להחלפה" (for trade). Currency always shown as `1,200 ₪` not `₪1,200` (the symbol follows the number with a space in Israeli convention).

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: דירה, רכב, ריהוט. שורה אחר שורה.
- **EN**: Apartment, car, furniture. One row at a time.

### Primary CTA

- **HE**: צפו במודעה
- **EN**: View listing

### Error message

- **HE**: המפרסם הסיר את המודעה.
- **EN**: Listing removed by owner.
