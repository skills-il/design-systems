---
name: Mizrach
version: 0.2.2
description: Eastern Mediterranean cultural depth, Hebrew-first. Bone surface, deep indigo ink, saffron accent. Layered, hospitable, calm.
colors:
  primary: "#1F2347"
  surface: "#F7F1E3"
  tertiary: "#E8A22A"
  on-primary: "#F7F1E3"
  on-surface: "#1F2347"
  on-tertiary: "#1F2347"
  surface-container: "#ECE2C8"
colors-dark:
  primary: "#F7F1E3"
  surface: "#1F2347"
  tertiary: "#FFB845"
  on-primary: "#1F2347"
  on-surface: "#F7F1E3"
  on-tertiary: "#1F2347"
  surface-container: "#2A2F5A"
typography:
  body-lg:
    fontSize: 18px
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
    fontSize: 12px
    fontFamily: Heebo, sans-serif
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.1em
  headline-lg:
    fontSize: 38px
    fontFamily: David Libre, Heebo, serif
    fontWeight: 600
    lineHeight: 1.15
  headline-md:
    fontSize: 26px
    fontFamily: David Libre, Heebo, serif
    fontWeight: 600
    lineHeight: 1.3
  headline-display:
    fontSize: 60px
    fontFamily: David Libre, Heebo, serif
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: -0.01em
spacing:
  lg: 28px
  md: 16px
  sm: 10px
  xl: 44px
  xs: 6px
  2xl: 72px
rounded:
  lg: 20px
  md: 12px
  sm: 6px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.md}"
    elevation: 0 6px 16px rgba(0,0,0,0.06)
    textColor: "{colors.on-surface}"
    borderWidth: 1px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 12px 16px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-ghost:
    padding: 12px 22px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 12px 22px
    rounded: "{rounded.md}"
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
---

## Overview

Mizrach draws from Eastern Mediterranean cultural surfaces, whitewashed Jaffa walls in late afternoon, the indigo of Yemenite embroidery, baskets of dried saffron and sumac at a Friday market. Hospitable without theatrics. Use Mizrach for cultural surfaces, food and dining, hospitality, heritage archives, anything that should feel rooted but contemporary.

Hebrew-first. David Libre carries display, Yanek Iontef's classical Hebrew serif descended from Ladino prayer-book typography fits the system's Mediterranean rootedness. Heebo carries body. Both bilingual.

## Colors

Three working colors plus surface-container.

- **Primary (#1F2347)**: deep indigo, the color of an embroidered border at dusk.
- **On primary (#F7F1E3)**: bone cream sitting on indigo.
- **Surface (#F7F1E3)**: bone, whitewashed Jaffa wall, slightly warm, never pure white.
- **On surface (#1F2347)**: indigo on bone.
- **Surface container (#ECE2C8)**: a deeper bone-cream, for cards and side panels.
- **Accent (#E8A22A)**: saffron, warm and earthy without slipping into the dim amber territory of dusk systems. The single attention-getter.
- **On accent (#1F2347)**: indigo on saffron. The pair is unusual but reads cleanly because the saffron stays warm rather than going neon.

The palette is intentionally rooted, neither the indigo nor the saffron is pulled toward digital brightness. Avoid bright orange, bright yellow, or any saturation push.

## Typography

David Libre at display weight 600 carries warmth without pretense, its Hebrew letterforms have a softer counter than Frank Ruhl Libre, with subtle stroke-contrast that reads as cultural rather than ceremonial. Heebo at body keeps reading texture humanist and consistent across scripts. Body line-height runs 1.7 for Hebrew breathing room.

The system pairs Hebrew and Arabic-influenced typographic mood without using actual Arabic, that boundary belongs to designers fluent in those traditions, not to a general-purpose system.

## Layout

Generous, columnar. 8 point base, container padding 24 on mobile, 56 on desktop. Archive grids favor 2-column on tablet, 3-column on desktop with generous gaps. Cards may overlap slightly on featured surfaces, the asymmetry references textile patterns.

Logical properties everywhere; the system reads with equal weight in both directions.

## Elevation & Depth

A whisper of depth. Cards may carry `0 2px 12px rgba(31, 35, 71, 0.08)` to lift them off the bone surface. Buttons stay flat. The system is layered through tone, not shadow.

## Shapes

Soft rounding. 8 pixels on inputs and buttons, 16 pixels on cards. The rounding references arched doorways without literal-mindedness; sharper corners read as European institutional and miss the regional warmth.

## Components

- **Buttons**: primary fills with saffron, indigo text, 8-pixel rounding. Ghost is bone with indigo outline. Hover on primary deepens to indigo fill, the warmth steps back, the depth steps forward.
- **Cards**: surface-container background, 16-pixel rounding, 24-pixel padding, soft indigo shadow. Headers carry a 1-pixel indigo border-inline-start as a quiet signature.
- **Inputs**: bone background, 1-pixel indigo border at 0.4 alpha, 8-pixel rounding, 16-pixel body. Focus ring is a 2-pixel saffron outline.

## Do's and Don'ts

Do use generous whitespace. Mizrach was built to feel uncrowded.
Do let textile patterns and architectural photography sit on the bone surface, the palette frames them.
Do use the saffron sparingly. Its warmth carries when it's rare.

Don't reach for bright digital colors. The system's restraint is its rootedness.
Don't add a second accent. Demote actions to ghost or to body-md links.
Don't sharpen the rounding. The softness references arched openings, not playfulness.

## Localization

Mizrach is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

Hospitality and dining: respect כשרות (kashrut) status and שבת for restaurant hours. Israeli holidays (חגים) affect availability; surface this when relevant. Hebrew month names: ינואר through דצמבר.

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: אירוח חם, שולחן ערוך.
- **EN**: Warm hospitality, well-laid table.

### Primary CTA

- **HE**: שמרו מקום
- **EN**: Reserve a place

### Error message

- **HE**: אין מקום בשעה שבחרתם. לבחור שעה אחרת?
- **EN**: No tables for the time you chose. Pick another?
