---
name: Friday Dusk
version: 0.2.3
description: Friday-night candlelight, Hebrew-first. Deep plum surface, candle ivory ink, warm amber accent. Intimate, ceremonial, dim.
colors:
  primary: "#FBE9C7"
  surface: "#2A1129"
  tertiary: "#E0935A"
  on-primary: "#2A1129"
  on-surface: "#FBE9C7"
  on-tertiary: "#2A1129"
  surface-container: "#3F1A3D"
colors-dark:
  primary: "#FFF1D2"
  surface: "#1A0818"
  tertiary: "#FF9D60"
  on-primary: "#1A0818"
  on-surface: "#FFF1D2"
  on-tertiary: "#1A0818"
  surface-container: "#2D0E2A"
typography:
  body-lg:
    fontSize: 18px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.7
  body-md:
    fontSize: 16px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.7
  body-sm:
    fontSize: 14px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.6
  label-sm:
    fontSize: 12px
    fontFamily: Assistant, sans-serif
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.1em
  headline-lg:
    fontSize: 40px
    fontFamily: Frank Ruhl Libre, Assistant, serif
    fontWeight: 500
    lineHeight: 1.15
  headline-md:
    fontSize: 26px
    fontFamily: Frank Ruhl Libre, Assistant, serif
    fontWeight: 500
    lineHeight: 1.3
  headline-display:
    fontSize: 64px
    fontFamily: Frank Ruhl Libre, Assistant, serif
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: -0.005em
spacing:
  lg: 32px
  md: 20px
  sm: 12px
  xl: 48px
  xs: 6px
  2xl: 80px
rounded:
  lg: 24px
  md: 16px
  sm: 8px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.lg}"
    elevation: 0 24px 48px rgba(0,0,0,0.18)
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

Friday Dusk is the system of the late evening, the room after the candles are lit. Deep plum surface, candle ivory ink, warm amber driver. Use Lyl Shabat for hospitality, family-oriented surfaces, prayer apps, journaling, anything that asks the reader to slow down. The dark surface is the system's authentic register, Friday night is a dim room, not a sunlit page.

Hebrew-first. Frank Ruhl Libre at display sizes carries a soft, modern Hebrew serif character; Assistant at body keeps the reading texture humanist and warm. Both bilingual.

## Colors

Candlelight palette, dim plum room, ivory ink, single warm flame.

- **Primary (#FBE9C7)**: candle ivory, used for ink-level fills (avatars, ghost-button text, headline color).
- **On primary (#2A1129)**: deep plum sitting on ivory fills.
- **Surface (#2A1129)**: deep plum, the room. Slightly warm, never blue-black.
- **On surface (#FBE9C7)**: ivory text on plum. Clears AAA at body-md (~14:1).
- **Surface container (#3F1A3D)**: lifted plum, for cards and quiet panels, slightly warmer and one shade up from the surface.
- **Accent (#E0935A)**: warm amber, the candle flame seen through glass. Brightened from the previous dusk-room amber so it lifts off the plum surface and clears AA on body-md text.
- **On accent (#2A1129)**: plum on amber. The pair holds the candle metaphor while clearing AA.

The palette stays low-saturation by intent. The amber should read as a flame in a dim room, present but never insistent.

## Typography

Frank Ruhl Libre at medium weight (500) gives the headlines warmth without preachy gravity. Assistant for body adds humanist rhythm to long passages. Body line-height runs 1.7, generous, slow.

The display weight intentionally stays at 500 rather than 700. Heavy headlines feel monumental; this system wants intimate.

## Layout

Soft, generous. 8 point base, container padding 24 on mobile, 56 on desktop. Cards rest on a single column on phones, expand to a 2-column grid at tablet, never more than 3-column on desktop. The system rewards air over density.

Logical properties everywhere. Lyl Shabat reads beautifully in both directions.

## Elevation & Depth

A soft warm glow, used sparingly. Cards lift via a tonal step (surface-container vs surface) plus an optional `0 4px 24px rgba(0, 0, 0, 0.4)` to suggest candlelight pooling on a dim table. Buttons stay flat. No glass effects.

## Shapes

Generous rounding. 12 pixels on inputs and buttons, 24 pixels on cards. The softness is part of the candlelight metaphor; sharp corners read as institutional and break the mood.

- **Buttons**: primary uses warm amber with plum text, 24-pixel rounding. Ghost is plum with ivory outline. Hover on primary swaps amber for ivory, the candle steadies and the room reads sharper.
- **Cards**: lifted-plum (surface-container) background, 12-pixel rounding, 24-pixel padding, soft warm shadow. Headers separate from body with whitespace, never with rules.
- **Inputs**: lifted-plum background, 1-pixel ivory border at low alpha, 12-pixel rounding, 16-pixel body. Focus ring is a 2-pixel amber outline.

## Do's and Don'ts

Do leave generous whitespace. The system is built to feel uncluttered.
Do use Hebrew at display weight (500), it reads more like a printed greeting than a billboard.
Do let the amber rest. One CTA per viewport, ideally per section.

Don't reach for blue or cool tones. The system is warm by definition.
Don't use heavy display weights (700+). Lyl Shabat whispers.
Don't use bold sans-serif headlines. The Frank Ruhl warmth is the voice.

## Localization

Friday Dusk is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

- **Letter-spacing override**: `headline-display.letterSpacing` is `-0.005em`. Apply this to Latin runs only. For Hebrew display text, override to `0`. Hebrew letterforms have no Latin-style ascenders/descenders, so negative tracking visually crowds them and hurts legibility.
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

Shabbat-aware UI: respect Friday sundown to Saturday sundown (zmanim). When showing times near these boundaries, surface a notice. Hebrew calendar dates are essential for ceremonial content (e.g., "ערב שבת פרשת בראשית · 18 בספטמבר 2026"). Candle-lighting time integration is recommended.

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: האור כבוי. הדף דולק.
- **EN**: Light off. Page on.

### Primary CTA

- **HE**: לקריאה בחושך
- **EN**: Read in the dark

### Error message

- **HE**: לא הצלחנו לטעון. נסו רשת חזקה יותר.
- **EN**: Could not load. Try a quieter network.
