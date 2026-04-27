---
name: Neon
version: 0.2.2
description: Tel Aviv signage at 2am, Hebrew-first. Jet surface, hot magenta accent, sharp grotesque type. Nocturnal, vivid, urban.
colors:
  primary: "#F0F0F8"
  surface: "#0A0A12"
  tertiary: "#FF2A8F"
  on-primary: "#0A0A12"
  on-surface: "#F0F0F8"
  on-tertiary: "#0A0A12"
  surface-container: "#1A1A28"
colors-dark:
  primary: "#FFFFFF"
  surface: "#000000"
  tertiary: "#FF45A0"
  on-primary: "#000000"
  on-surface: "#FFFFFF"
  on-tertiary: "#000000"
  surface-container: "#0F0F1F"
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
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0.12em
  headline-lg:
    fontSize: 44px
    fontFamily: Archivo Black, Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.05
    letterSpacing: -0.02em
  headline-md:
    fontSize: 28px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: -0.01em
  headline-display:
    fontSize: 72px
    fontFamily: Archivo Black, Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1
    letterSpacing: -0.03em
spacing:
  lg: 20px
  md: 12px
  sm: 8px
  xl: 32px
  xs: 4px
  2xl: 56px
rounded:
  lg: 9999px
  md: 2px
  sm: 0px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.md}"
    elevation: 0 0 24px rgba(255,32,200,0.25)
    textColor: "{colors.on-surface}"
    borderWidth: 0px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 10px 14px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface-container}"
  button-ghost:
    padding: 12px 22px
    rounded: "{rounded.lg}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 10px 22px
    rounded: 9999px
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
---

## Overview

Neon is the system of Tel Aviv after midnight. The shop signs on Allenby, the bar entrance on Lilienblum, headlights cutting through humidity on Ibn Gabirol. Pitch surface, one electric magenta, sharp grotesque type. Use Neon for nightlife, music, events, club listings, anything that should feel like it stays open after everyone else closes.

Hebrew-first. Archivo Black handles display, the heaviest grotesque on the Google Fonts roster, descended from sign-painter lettering, the closest typographic match to a hand-cut neon tube. Heebo handles body and any sub-display headline. The contrast between the two faces, display impossibly heavy, body neutral and quiet, is the system's signature.

## Colors

Three working colors. The palette is unforgiving on purpose.

- **Primary (#F0F0F8)**: cool off-white, used for body text on the jet surface. Inverted from most systems.
- **On primary (#0A0A12)**: jet sitting on top of primary fills.
- **Surface (#0A0A12)**: jet, the canvas. Not pure black, slightly cool, like wet asphalt.
- **On surface (#F0F0F8)**: cool white text on jet.
- **Surface container (#1A1A28)**: deeper night, for cards and inputs that need to recede.
- **Accent (#FF2A8F)**: hot magenta. The only thing that glows.
- **On accent (#0A0A12)**: jet on magenta. Black-on-pink reads as classic neon-sign typography and clears AA contrast where white-on-pink would not.

Never introduce a second accent color. Cyan, lime, electric yellow, they all read as decoration in this system. Demote secondary actions to ghost or to body-md links.

## Typography

Archivo Black is the load-bearing display face. Single weight (400 maps to its only available cut) compressed by -0.03em tracking on display gives the system its signage-like density, letterforms touch each other the way neon-tube curves do. Heebo carries body and headline-md, keeping mid-prose reading rhythm calm so the display work feels staged.

The system has no second display weight. Body weight stays 400. There is no italic, neon signs do not lean.

## Layout

Asymmetric. 8 point base, container padding 24 on mobile, 56 on desktop. The system rewards bold blocks of color, generous negative space, and the occasional off-grid quote. Avoid timid evenly-distributed grids, Neon was built to feel staged.

Logical properties throughout. Hebrew flips cleanly to the right rail.

## Elevation & Depth

Selective glow. The accent magenta may carry a `0 0 24px rgba(255, 42, 143, 0.4)` glow on primary CTAs and on focus rings. Cards stay flat. No drop shadows, Neon is a flat city seen at night, not a relief.

## Shapes

Pill rounding (999px) on buttons, full circle on avatars. Cards round to 6 pixels. Inputs to 6 pixels. The pill buttons reference neon tube ends.

## Components

- **Buttons**: primary fills with magenta and a soft magenta glow on hover; pill rounding. Ghost is jet with cool-white outline. Hover on primary swaps the magenta for cool white, the sign turns off and the room sharpens.
- **Cards**: surface-container background (slight tonal step from jet), 6-pixel rounding, 24-pixel padding. Headers may carry a 1-pixel magenta border-block-start as a signature stripe.
- **Inputs**: surface-container background, 1-pixel cool-white-at-low-alpha border, 6-pixel rounding. Focus ring is a 2-pixel magenta outline with the magenta glow.

## Do's and Don'ts

Do let the surface read pitch. Do not lighten the jet to slate.
Do use the magenta sparingly. The magenta works because most of the screen is jet.
Do tighten display tracking. The system is built for compressed headlines.

Don't add a second accent. Cyan and magenta together read as 80s costume; the system is contemporary.
Don't reach for italic or hairline weights. Neither survives at small sizes against the jet.
Don't shadow text, the surface is already dramatic.

## Localization

Neon is built Hebrew-first. The token block above ships values that work for both scripts when consumed via a Hebrew-capable font stack; the rules below capture the practical RTL, BiDi, and Hebrew typography decisions that the tokens alone do not encode.

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

- **Letter-spacing override**: `headline-display.letterSpacing` is `-0.03em`. Apply this to Latin runs only. For Hebrew display text, override to `0`. Hebrew letterforms have no Latin-style ascenders/descenders, so negative tracking visually crowds them and hurts legibility.
- **Display line-height**: `headline-display.lineHeight` is `1`. Hebrew descenders (ק, ץ, ן) clash with the next line at this density. Override to `1.15` minimum for Hebrew display text.
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

### Cultural notes

Late-night entertainment: assume 24-hour clock. Friday-night and Saturday-night are peak; distinguish between ערב שבת (Friday eve) and מוצאי שבת (Saturday night). Avoid "סוף שבוע" as a single concept; in Israel the work week is Sunday through Thursday.

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: אחרי חצות, אות מלא.
- **EN**: Late hours, loud signal.

### Primary CTA

- **HE**: תפתחו את ההופעה
- **EN**: Start the show

### Error message

- **HE**: השידור נפל. מתחברים שוב.
- **EN**: Stream dropped. We are reconnecting.
