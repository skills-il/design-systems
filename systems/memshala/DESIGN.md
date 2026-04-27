---
name: Civic
version: 0.1.2
description: Modern Israeli government, WCAG-strict contrast, generous accessible spacing, deep navy authority.
colors:
  primary: "#003E80"
  surface: "#FFFFFF"
  tertiary: "#0061A8"
  secondary: "#1F2937"
  on-primary: "#FFFFFF"
  on-surface: "#111827"
  on-tertiary: "#FFFFFF"
  on-secondary: "#FFFFFF"
  surface-container: "#F3F4F6"
colors-dark:
  primary: "#5BA0E8"
  surface: "#0A0F1C"
  tertiary: "#76B5E8"
  secondary: "#E5E7EB"
  on-primary: "#0A0F1C"
  on-surface: "#F3F4F6"
  on-tertiary: "#0A0F1C"
  on-secondary: "#0A0F1C"
  surface-container: "#16223A"
typography:
  body-lg:
    fontSize: 18px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.6
  body-md:
    fontSize: 16px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.6
  body-sm:
    fontSize: 14px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.55
  label-sm:
    fontSize: 12px
    fontFamily: Assistant, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0.04em
  headline-lg:
    fontSize: 32px
    fontFamily: Assistant, sans-serif
    fontWeight: 700
    lineHeight: 1.2
  headline-md:
    fontSize: 22px
    fontFamily: Assistant, sans-serif
    fontWeight: 600
    lineHeight: 1.3
  headline-display:
    fontSize: 48px
    fontFamily: Assistant, sans-serif
    fontWeight: 700
    lineHeight: 1.15
    letterSpacing: -0.01em
spacing:
  lg: 28px
  md: 18px
  sm: 10px
  xl: 44px
  xs: 6px
  2xl: 72px
rounded:
  lg: 12px
  md: 8px
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
    padding: 12px 16px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 12px 24px
    rounded: "{rounded.md}"
    textColor: "{colors.on-primary}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-tertiary}"
    backgroundColor: "{colors.tertiary}"
---

## Overview

Civic is what Israeli government should look like in 2026: deep navy authority, neutral greys, strict WCAG AA contrast, generous tap targets, no marketing flourish. Modeled on the post-redesign gov.il aesthetic, calm, accessible, trustworthy, immediately recognizable as state digital service.

Use Civic for citizen-facing services: tax forms, benefits applications, ID renewals, municipal portals. Anywhere the user is performing a transaction with the state.

## Colors

Primary `#003E80` deep gov navy. Tertiary `#0061A8` action blue for hover and links. Surface `#FFFFFF` pure white. Surface-container `#F3F4F6` subtle grey panels for sidebars and helper sections.

Every text-on-surface pair clears WCAG AA (4.5:1 body, 3:1 large) by design. Don't introduce decorative grays below `#1F2937` for body copy.

## Typography

Assistant for everything, Hebrew-first sans designed for the Israeli government context, excellent legibility at body sizes. No display serif. Body sits at 16-18px. Line-height 1.6 so dense form labels don't feel cramped. Display headlines stay restrained at 48px weight 700, Civic doesn't shout.

## Layout

Generous spacing: `lg: 28px`, `xl: 44px`, `2xl: 72px`. Forms get airy field spacing. Buttons have 12/24 padding for accessible touch targets.

## Shapes

Modest 8px radius on cards, buttons, inputs. Soft enough to feel modern, restrained enough to feel official. Never pill-shaped, pill reads as marketing/SaaS, wrong for civic.

## Components

Buttons: navy primary, 8px corners, 12/24 padding. Hover transitions to action-blue. Cards: light grey panels with 1px hairline border and 1px lift shadow. Inputs: white background, 1px hairline border, 8px corners, 12/16 padding. Focus ring is a 2-pixel navy outline with 2-pixel offset.

## Localization

Civic is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

Government surfaces require formal Hebrew register (לשון רשמית). Avoid colloquialisms like "תיכף נחזור אליכם"; prefer "נחזור אליכם בהקדם". The Israeli ID number (תעודת זהות, ת.ז.) is 9 digits, displayed LTR-wrapped: `<bdi>123456789</bdi>`. Forms must accept both spellings of names (Hebrew + Latin transliteration).

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: שירות ממשלתי, פשוט להבין.
- **EN**: A government service, made simple.

### Primary CTA

- **HE**: פתחו את הבקשה
- **EN**: Begin the request

### Error message

- **HE**: נצטרך את מספר תעודת הזהות כדי להמשיך.
- **EN**: We need your ID number to continue.
