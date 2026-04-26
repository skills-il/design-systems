---
name: Kodesh
version: 0.2.1
description: Sacred Hebrew manuscript gravity, Hebrew-first. Parchment surface, manuscript ink, gilt accent. Reverent, traditional, still.
colors:
  primary: "#1B1612"
  on-primary: "#F2E8CF"
  surface: "#F2E8CF"
  on-surface: "#1B1612"
  surface-container: "#E5D7AC"
  tertiary: "#6F5520"
  on-tertiary: "#F2E8CF"
colors-dark:
  on-primary: "#1B1612"
  on-surface: "#F2E8CF"
  on-tertiary: "#1B1612"
  primary: "#F2E8CF"
  surface: "#1B1612"
  surface-container: "#2A2218"
  tertiary: "#B8923D"
typography:
  headline-display:
    fontFamily: "Frank Ruhl Libre, Heebo, serif"
    fontSize: 60px
    fontWeight: "700"
    lineHeight: 1.15
  headline-lg:
    fontFamily: "Frank Ruhl Libre, Heebo, serif"
    fontSize: 40px
    fontWeight: "700"
    lineHeight: 1.2
  headline-md:
    fontFamily: "Frank Ruhl Libre, Heebo, serif"
    fontSize: 26px
    fontWeight: "700"
    lineHeight: 1.3
  body-lg:
    fontFamily: "Heebo, sans-serif"
    fontSize: 19px
    fontWeight: "400"
    lineHeight: 1.85
  body-md:
    fontFamily: "Heebo, sans-serif"
    fontSize: 17px
    fontWeight: "400"
    lineHeight: 1.85
  body-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 15px
    fontWeight: "400"
    lineHeight: 1.7
  label-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 12px
    fontWeight: "600"
    lineHeight: 1.2
    letterSpacing: "0.14em"
rounded:
  none: 0px
  sm: 0px
  md: 2px
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
    rounded: "{rounded.none}"
    padding: 12px 22px
  button-primary-hover:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  button-ghost:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.none}"
    padding: 12px 22px
  card:
    backgroundColor: "{colors.surface-container}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: "{spacing.lg}"
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.none}"
    padding: 12px 16px
---

## Overview

Kodesh draws from the Hebrew manuscript tradition, parchment, square Hebrew letters, the gilt page edge of a 15th-century prayer book. Reverent without ornament. Use Kodesh for prayer apps, religious-text study, archive surfaces, anything that should feel like it has been carefully copied by hand.

Hebrew-first by definition. Frank Ruhl Libre carries every display and headline size, its modern Hebrew serif is descended directly from the manuscript tradition. Heebo carries body, including nikkud-heavy passages.

## Colors

Manuscript palette. Every color earns its place.

- **Primary (#1B1612)**: manuscript ink, slightly warm, never pure black.
- **On primary (#F2E8CF)**: parchment cream sitting on ink.
- **Surface (#F2E8CF)**: parchment, the page itself.
- **On surface (#1B1612)**: ink on parchment.
- **Surface container (#E5D7AC)**: aged parchment, slightly deeper, for chapter dividers and citation panels.
- **Accent (#6F5520)**: gilt, soft gold leaf, never bright. Reserved for chapter marks, primary CTAs, and the single page-edge stripe.
- **On accent (#F2E8CF)**: parchment on gilt.

The palette is intentionally narrow. If you need to introduce a "color" for status (warning, error), demote it to a 1-pixel ink rule with text below, never tint the parchment.

## Typography

Frank Ruhl Libre is the load-bearing face. Display, headline, and any prominent prose use it; the system was built around its modern Hebrew serif. Heebo carries body, with nikkud-aware metrics.

Body line-height runs 1.85, wide enough to carry niqqud comfortably without the page feeling sparse. The system never goes below 16-pixel body.

## Layout

Single-column long-form. 8 point base, container padding 24 on mobile, 64 on desktop. Long-form text is constrained to a 60-character measure (about 660px at body-lg). Side notes and citations use surface-container with a 2-pixel ink border-inline-start.

Logical properties throughout. Hebrew is the primary direction; English citations flow cleanly when isolated.

## Elevation & Depth

None. Manuscripts do not float. Hierarchy comes from typography (size, weight, position), tone (`surface` vs `surface-container`), and 1-pixel ink rules.

## Shapes

Sharp. Buttons and inputs are 0-radius. Cards round to 2 pixels at most. Avatars are circular only when avatars are necessary; otherwise prefer initials in a 2-pixel rounded square.

## Components

- **Buttons**: primary fills with gilt, parchment text, no rounding, no shadow. Ghost is parchment with ink border. Hover on primary swaps to ink fill, the gilt recedes, the depth steps forward.
- **Cards**: surface-container background, 2-pixel rounding, 24-pixel padding. Citation panels carry a 2-pixel ink border-inline-start. No shadows.
- **Inputs**: parchment background, 1-pixel ink border, 0 rounding, 17-pixel body-md. Focus ring is a 2-pixel gilt outline-offset.

## Do's and Don'ts

Do constrain text measure. Manuscripts read column-by-column, not edge-to-edge.
Do use the gilt sparingly, once per page, ideally on the chapter mark or primary CTA.
Do let typography carry the hierarchy. Frank Ruhl at headline weight is enough.

Don't reach for sans-serif headlines. The whole system is built around the serif.
Don't introduce decorative color. The parchment, ink, and gilt are the entire palette.
Don't soften the rounding to look modern, the sharpness is the gravity.

## Localization

Kodesh was built Hebrew-first specifically for sacred-text surfaces.

### RTL layout

`dir="rtl"` on `<html>` for Hebrew. Logical properties only. The single-column manuscript layout flips trivially; English citations should be wrapped in `<bdi>` or use `dir="ltr"` on the citation block to avoid bidi confusion inside Hebrew running text.

### Digits inside RTL flow

Hebrew calendar dates inline with religious copy; gematria values acceptable inside scholarly contexts. Latin numerals for chapter and verse references, page numbers, and modern dates. Wrap mixed-direction citations in `<bdi>`.

### Nikkud

Kodesh is the recommended system for any Hebrew nikkud-heavy content. Frank Ruhl Libre's niqqud metrics are conservative and the parchment background reduces eye strain on dense vowelized passages. The default body line-height (1.85) is already nikkud-safe; do not tighten it.

### Punctuation

Gershayim (״) and geresh (׳) for Hebrew abbreviations. Maqaf (־) for compounds. Inverted nun (׆) and other rare Hebrew punctuation may appear inside scriptural quotation, Frank Ruhl Libre carries them. The system never uses em-dashes.

### OpenType features

Frank Ruhl Libre's contextual alternates (`calt`), ligatures (`liga`), and discretionary ligatures (`dlig`) are essential, leave them all on. For nikkud-heavy passages, ensure `font-feature-settings: "kern"` stays enabled so vowel marks stack correctly.

### Accessibility

All default pairs clear WCAG AAA at body-md. The parchment surface reduces contrast slightly versus pure white but stays well above 4.5:1 with the deep ink. Body-lg is preferred over body-md for long-form sacred-text reading; body-sm is for citation footnotes only.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
colors:
  primary: "#1B1612"
  surface: "#F2E8CF"
  tertiary: "#6F5520"
  on-primary: "#F2E8CF"
  on-surface: "#1B1612"
  on-tertiary: "#F2E8CF"
  surface-container: "#E5D7AC"
colors-dark:
  primary: "#F2E8CF"
  surface: "#1B1612"
  tertiary: "#B8923D"
  on-primary: "#1B1612"
  on-surface: "#F2E8CF"
  on-tertiary: "#1B1612"
  surface-container: "#2A2218"
typography:
  body-lg:
    fontSize: 19px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.85
  body-md:
    fontSize: 17px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.85
  body-sm:
    fontSize: 15px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.7
  label-sm:
    fontSize: 12px
    fontFamily: Heebo, sans-serif
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.14em
  headline-lg:
    fontSize: 40px
    fontFamily: Frank Ruhl Libre, Heebo, serif
    fontWeight: 700
    lineHeight: 1.2
  headline-md:
    fontSize: 26px
    fontFamily: Frank Ruhl Libre, Heebo, serif
    fontWeight: 700
    lineHeight: 1.3
  headline-display:
    fontSize: 60px
    fontFamily: Frank Ruhl Libre, Heebo, serif
    fontWeight: 700
    lineHeight: 1.15
spacing:
  lg: 40px
  md: 24px
  sm: 14px
  xl: 64px
  xs: 8px
  2xl: 104px
rounded:
  lg: 4px
  md: 2px
  sm: 0px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.md}"
    elevation: none
    textColor: "{colors.on-surface}"
    borderWidth: 1px
    backgroundColor: "{colors.surface}"
  input:
    padding: 12px 16px
    rounded: "{rounded.none}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-ghost:
    padding: 12px 22px
    rounded: "{rounded.none}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 14px 28px
    rounded: 2px
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

- **HE**: מלאכה של קודש, שנכתבת בכוונה.
- **EN**: Sacred work, set down with care.

### Primary CTA

- **HE**: פתחו ללימוד
- **EN**: Begin the study

### Error message

- **HE**: הטקסט לא נטען. רעננו ונסו שוב.
- **EN**: The text could not be loaded. Refresh and try again.
