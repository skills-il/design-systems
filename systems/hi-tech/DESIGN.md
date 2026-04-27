---
name: Hi-Tech
version: 0.2.2
description: Rothschild high-rise minimalism, Hebrew-first. White surface, deep navy ink, electric blue accent. Sharp, ambitious, technical.
colors:
  primary: "#0A1A2F"
  surface: "#FFFFFF"
  tertiary: "#2456E8"
  on-primary: "#FFFFFF"
  on-surface: "#0A1A2F"
  on-tertiary: "#FFFFFF"
  surface-container: "#F4F6FA"
colors-dark:
  primary: "#E8EEF6"
  surface: "#0A1A2F"
  tertiary: "#5C8AFF"
  on-primary: "#0A1A2F"
  on-surface: "#E8EEF6"
  on-tertiary: "#0A1A2F"
  surface-container: "#0F2440"
typography:
  body-lg:
    fontSize: 17px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.55
  body-md:
    fontSize: 15px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.55
  body-sm:
    fontSize: 13px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.5
  label-sm:
    fontSize: 12px
    fontFamily: Space Grotesk, Heebo, sans-serif
    fontWeight: 500
    lineHeight: 1.2
    letterSpacing: 0.08em
  headline-lg:
    fontSize: 40px
    fontFamily: Space Grotesk, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.1
    letterSpacing: -0.02em
  headline-md:
    fontSize: 28px
    fontFamily: Space Grotesk, Heebo, sans-serif
    fontWeight: 500
    lineHeight: 1.2
    letterSpacing: -0.01em
  headline-display:
    fontSize: 64px
    fontFamily: Space Grotesk, Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.05
    letterSpacing: -0.025em
spacing:
  lg: 22px
  md: 14px
  sm: 8px
  xl: 36px
  xs: 4px
  2xl: 56px
rounded:
  lg: 8px
  md: 4px
  sm: 2px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.md}"
    elevation: 0 1px 0 rgba(0,0,0,0.04)
    textColor: "{colors.on-surface}"
    borderWidth: 1px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 10px 14px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-ghost:
    padding: 10px 18px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 10px 20px
    rounded: 2px
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
---

## Overview

Hi-Tech is the system of the Israeli SaaS landing page after a clean redesign. Crisp white surface, deep navy text, one electric blue driver. Use Hi-Tech for B2B products, developer tools, dashboards, anything that needs to read as engineered before it reads as warm.

Built Hebrew-first: Space Grotesk paired with Heebo as a Hebrew-glyph fallback for display, Heebo carrying all body sizes. The pairing keeps Latin headlines tight and confident while Hebrew metrics stay on the Heebo grid.

## Colors

Three working colors plus surface container. Restraint is the point.

- **Primary (#0A1A2F)**: deep navy, near-black. Carries body text and inverted CTAs.
- **On primary (#FFFFFF)**: pure white when sitting on primary.
- **Surface (#FFFFFF)**: clean white, the canvas.
- **On surface (#0A1A2F)**: text on surface and surface-container.
- **Surface container (#F4F6FA)**: cool gray-blue, used for cards, sidebars, code blocks.
- **Accent (#2456E8)**: electric blue, the only attention-getter. Used for primary CTAs, links, focus rings.
- **On accent (#FFFFFF)**: white sitting on the blue accent.

Never introduce a green "success" or yellow "warning" without aligning their saturation to the accent. Hi-Tech tolerates monochrome status badges (gray fill, accent stroke) better than rainbow ones.

## Typography

Space Grotesk handles every display and headline size. Its tight letterforms and slightly tucked geometry give the system a contemporary technical feel without going retro. Heebo handles body, same family used by skills-il at large, so Hebrew metrics match site chrome.

Display tracking is tightened (-0.025em) to compress headline mass; body stays at default tracking so dense paragraphs remain readable.

## Layout

Tight grid. 8 point base, container padding 24 on mobile, 64 on desktop. Dashboards use a fixed start-rail (right rail in RTL) at desktop with a 240-pixel sidebar; landing pages use a 12-column max-1280 grid.

Use logical properties throughout. The system was authored to render identically when `dir` flips.

## Elevation & Depth

Minimal shadows. Cards rest on `surface-container` instead of casting a shadow on white. Where elevation is needed (popovers, dropdowns), use a single soft shadow `0 4px 12px rgba(10, 26, 47, 0.08)`. No glass blurs, no gradients.

## Shapes

Restrained rounding. 8 pixel radius on inputs and buttons, 12 pixels on cards. Avatars are circular. Status badges are full pill rounding (999px). The system stays away from very sharp 0-radius shapes, those read as 90s utilitarian against the navy.

## Components

- **Buttons**: primary uses electric blue with white text; ghost uses white with navy text and a 1-pixel navy border. Hover on primary deepens to navy fill (the accent recedes to outline). No drop shadows on buttons.
- **Cards**: surface-container background, 12-pixel rounding, 24-pixel internal padding, no border. Headers separate from body with whitespace, never with rules.
- **Inputs**: white background, 1-pixel `surface-container`-derived border (cool gray), 8-pixel rounding, 15-pixel body-md text. Focus ring is a 2-pixel accent stroke plus a soft `0 0 0 4px rgba(36, 86, 232, 0.16)` halo.

## Do's and Don'ts

Do keep the accent rare. One CTA per viewport. The system relies on the blue working hard, not often.
Do use surface-container as the second tier of hierarchy instead of shadow.
Do use mono (JetBrains Mono is whitelist-compatible if added) only for code blocks; never for body.

Don't introduce a secondary accent. Demote actions to ghost or to text links.
Don't add gradient backgrounds. Hi-Tech is engineered, not decorated.
Don't soften the navy with slate-blue. The depth carries the trust.

## Localization

Hi-Tech is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

- **Letter-spacing override**: `headline-display.letterSpacing` is `-0.025em`. Apply this to Latin runs only. For Hebrew display text, override to `0`. Hebrew letterforms have no Latin-style ascenders/descenders, so negative tracking visually crowds them and hurts legibility.
- **Display line-height**: `headline-display.lineHeight` is `1.05`. Hebrew descenders (ק, ץ, ן) clash with the next line at this density. Override to `1.15` minimum for Hebrew display text.
- **font-feature-settings**: keep `kern` and `calt` enabled on every text node. Frank Ruhl Libre's contextual alternates and the kerning table for Heebo/Assistant are needed for proper Hebrew rendering. Never set `font-feature-settings: normal` globally.
- **Body min-size**: `body-sm` is `13px`. Hebrew at this size loses legibility faster than Latin. Use `body-sm` for metadata and captions only; never for primary content. Body-md (`15px`) is the safe Hebrew body floor.

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

- **HE**: מהונדס, לא מקושט.
- **EN**: Engineered, not decorated.

### Primary CTA

- **HE**: התחילו בחינם
- **EN**: Start free

### Error message

- **HE**: החיבור נדחה (סטטוס 401). היכנסו מחדש.
- **EN**: Connection refused (status 401). Re-authenticate.
