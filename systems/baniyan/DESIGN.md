---
name: Bauhaus
version: 0.2.1
description: White City modernism, Hebrew-first. Cream paper, black ink, single red ochre accent. Authoritative, quiet, civic.
colors:
  primary: "#1A1A18"
  on-primary: "#F3EEE3"
  surface: "#F3EEE3"
  on-surface: "#1A1A18"
  surface-container: "#EAE3D2"
  tertiary: "#A13A2A"
  on-tertiary: "#F3EEE3"
colors-dark:
  on-primary: "#1A1A18"
  on-surface: "#F3EEE3"
  on-tertiary: "#F3EEE3"
  primary: "#F3EEE3"
  surface: "#1A1A18"
  surface-container: "#25231F"
  tertiary: "#C44B36"
typography:
  headline-display:
    fontFamily: "Frank Ruhl Libre, Public Sans, serif"
    fontSize: 72px
    fontWeight: "700"
    lineHeight: 1.05
    letterSpacing: "-0.02em"
  headline-lg:
    fontFamily: "Frank Ruhl Libre, Public Sans, serif"
    fontSize: 48px
    fontWeight: "700"
    lineHeight: 1.1
    letterSpacing: "-0.01em"
  headline-md:
    fontFamily: "Frank Ruhl Libre, Public Sans, serif"
    fontSize: 32px
    fontWeight: "600"
    lineHeight: 1.2
  body-lg:
    fontFamily: "Heebo, sans-serif"
    fontSize: 18px
    fontWeight: "400"
    lineHeight: 1.55
  body-md:
    fontFamily: "Heebo, sans-serif"
    fontSize: 16px
    fontWeight: "400"
    lineHeight: 1.6
  body-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 14px
    fontWeight: "400"
    lineHeight: 1.55
  label-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 12px
    fontWeight: "600"
    lineHeight: 1.2
    letterSpacing: "0.12em"
rounded:
  none: 0px
  sm: 2px
  md: 4px
spacing:
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 40px
  2xl: 64px
components:
  button-primary:
    backgroundColor: "{colors.tertiary}"
    textColor: "{colors.on-tertiary}"
    typography: "{typography.body-md}"
    rounded: "{rounded.sm}"
    padding: 12px 20px
  button-primary-hover:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  button-ghost:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.sm}"
    padding: 12px 20px
  card:
    backgroundColor: "{colors.surface-container}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: "{spacing.lg}"
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.sm}"
    padding: 10px 14px
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

Bauhaus is designed for Hebrew-first and bilingual interfaces. When generating UI, follow these rules.

### RTL layout

Set `dir="rtl"` on `<html>` for Hebrew pages. Use CSS logical properties exclusively: `padding-inline-start` instead of `padding-left`, `margin-inline-end` instead of `margin-right`, `inset-inline-start` instead of `left`. Tailwind equivalents: `ps-*`, `me-*`, `start-*`. Never hardcode left/right, the system must flip cleanly.

### Digits inside RTL flow

Use Latin digits for prices, dates, phone numbers, and identifiers in both locales. Hebrew text runs right-to-left, digits render left-to-right, and unwrapped mixed runs break visually. Wrap mixed content in `<bdi>` or apply `unicode-bidi: plaintext` so "1,200 ₪" and "03-1234567" stay readable. Prefer `en-IL` date format (`dd/mm/yyyy`) in Hebrew UI.

### Nikkud

Bauhaus is not designed to carry nikkud. If niqqud is required for religious, educational, or poetic content, either switch to a nikkud-optimized system or override line-height on affected nodes to 1.9 and bump letter-spacing by 0.04em.

### Punctuation

In Hebrew copy use gershayim (״) and geresh (׳), not ASCII double and single quotes. In Latin copy use standard curly or ASCII quotes. Hyphens become maqaf (־) in Hebrew for compound words; ASCII hyphens are fine inside code spans.

### OpenType features

No special features required. Heebo and Frank Ruhl Libre both enable their default ligatures and alternates; do not disable `liga` or `calt`.

### Accessibility

Maintain 4.5:1 contrast on all text regardless of script. The palette already meets AA on every component pair; avoid tinting text below `on-surface` or `on-primary` without re-running a contrast check.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
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
```

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

- **HE**: שדה חובה. אנא מלאו אותו.
- **EN**: Required field. Please fill it in.
