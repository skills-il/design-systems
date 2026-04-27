---
name: Shuk
version: 0.2.2
description: Carmel Market warmth, Hebrew-first. Cream awning, paprika accent, generous rounding. Hospitable, expressive, never quiet.
colors:
  primary: "#2A1810"
  surface: "#FFF6E6"
  tertiary: "#B83609"
  on-primary: "#FFF6E6"
  on-surface: "#2A1810"
  on-tertiary: "#FFF6E6"
  surface-container: "#F4DEB5"
colors-dark:
  primary: "#FFF6E6"
  surface: "#2A1810"
  tertiary: "#E8542D"
  on-primary: "#2A1810"
  on-surface: "#FFF6E6"
  on-tertiary: "#FFF6E6"
  surface-container: "#3D2418"
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
    fontSize: 40px
    fontFamily: Rubik, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.15
  headline-md:
    fontSize: 28px
    fontFamily: Rubik, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.25
  headline-display:
    fontSize: 64px
    fontFamily: Rubik, Heebo, sans-serif
    fontWeight: 800
    lineHeight: 1.05
    letterSpacing: -0.015em
spacing:
  lg: 32px
  md: 20px
  sm: 12px
  xl: 48px
  xs: 6px
  2xl: 80px
rounded:
  lg: 24px
  md: 14px
  sm: 8px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.lg}"
    elevation: 0 8px 24px rgba(0,0,0,0.08)
    textColor: "{colors.on-surface}"
    borderWidth: 0px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 12px 16px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-ghost:
    padding: 14px 24px
    rounded: "{rounded.lg}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 12px 24px
    rounded: 9999px
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
---

## Overview

Shuk is the design system of Israeli daylight commerce. Hand-painted produce signs, fluorescent halogen on canvas awnings, the quick exchange of cash and shekels at five in the afternoon. Use Shuk when warmth is the product: hospitality apps, neighborhood marketplaces, food and dining, anything that should feel like its readers are welcome.

The system is Hebrew-first. Rubik carries display sizes with a chunky, almost hand-cut Hebrew character; Heebo carries body. Both ship full Latin glyphs, so a single bilingual page reads cleanly without script swapping.

## Colors

Warm cream, deep cocoa ink, one paprika accent.

- **Primary (#2A1810)**: cocoa-charcoal, used for all body text and ink-level surfaces.
- **On primary (#FFF6E6)**: warm cream, sits on top of primary when the role inverts.
- **Surface (#FFF6E6)**: awning cream, the dominant page background.
- **On surface (#2A1810)**: text color on surface and surface-container.
- **Surface container (#F4DEB5)**: sun-warmed straw, for cards, sidebars, callouts.
- **Accent (#B83609)**: paprika, the only color allowed to call for attention. CTAs, error states, key chips.
- **On accent (#FFF6E6)**: cream sitting on accent fills.

The palette intentionally skews warm. Avoid pure white and pure black, both fight the cream surface. If you need cooler contrast, deepen primary instead of swapping for slate.

## Typography

Two families carry the system. Rubik for display and headlines (chunky, friendly, slightly informal); Heebo for everything body-sized down (bilingual, neutral, optically calm at small sizes).

Display weight is heavy (800) on purpose. Shuk wants headlines that feel hand-set on a wooden sign, not whispered in a museum. Body line-heights run 1.6 to 1.65 to give Hebrew descenders room.

## Layout

Generous spacing, but not academic. 8 point base, container padding 16 pixels on mobile, 40 on desktop. Cards group naturally on a single column on phones; expand to a 12-column grid at tablet and above.

Use logical properties everywhere, `padding-inline-start`, `inset-inline-end`, Tailwind `ps-*`, `me-*`, `start-*`. Shuk lives in both directions; never hardcode left or right.

## Elevation & Depth

Shuk uses depth sparingly but allows it. Cards get a soft warm shadow (`0 2px 8px rgba(42, 24, 16, 0.08)`) to lift them off the cream surface; hover deepens to `0 4px 16px rgba(42, 24, 16, 0.12)`. Avoid hard shadows or glass effects, the system is not premium, it is friendly.

## Shapes

Generous rounding. 14 pixel radius on inputs and buttons, 24 pixels on cards and pill chips. The rounding is part of the personality; sharp corners read as institutional in this palette and that is the wrong feeling.

## Components

- **Buttons**: primary uses paprika fill with cream text and 24-pixel rounding; ghost uses transparent fill with cocoa outline. Hover swaps paprika to cocoa for a deeper, fuller pull. No gradients.
- **Cards**: surface-container background, 14-pixel rounding, 24-pixel padding, soft warm shadow. Section dividers prefer whitespace over rules.
- **Inputs**: surface background, 1-pixel cocoa border, 14-pixel rounding, 16-pixel body-md text. Focus ring is a 2-pixel paprika outline plus a 1-pixel cocoa border.

## Do's and Don'ts

Do let the paprika rest. One CTA per viewport, if everything is calling for attention, nothing is.
Do pair display headlines with photography of food, fabric, or markets. The system was built to frame those.
Do use generous internal padding. Cramped cards read as anxious in this palette.

Don't add a second accent. If two actions must coexist, demote one to ghost.
Don't use pure white anywhere. The cream is load-bearing.
Don't sharpen the rounding to look "more professional", the warmth is the professionalism here.

## Localization

Shuk is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

- **Letter-spacing override**: `headline-display.letterSpacing` is `-0.015em`. Apply this to Latin runs only. For Hebrew display text, override to `0`. Hebrew letterforms have no Latin-style ascenders/descenders, so negative tracking visually crowds them and hurts legibility.
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

Marketplace voice: confident and direct. Currency always `1,200 ₪`. Use אחוז (%) for discounts, displayed `25%` (LTR) inside Hebrew context. Friday market hours often differ from weekday hours; surface this.

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: טרי היום. בקול ובלב שלם.
- **EN**: Fresh today. Loud and proud.

### Primary CTA

- **HE**: הוסיפו לסל
- **EN**: Add to basket

### Error message

- **HE**: אזל מהמלאי. נסו דוכן שכן.
- **EN**: Out of stock. Try the stall next door.
