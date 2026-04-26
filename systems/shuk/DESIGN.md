---
name: Shuk
version: 0.2.1
description: Carmel Market warmth, Hebrew-first. Cream awning, paprika accent, generous rounding. Hospitable, expressive, never quiet.
colors:
  primary: "#2A1810"
  on-primary: "#FFF6E6"
  surface: "#FFF6E6"
  on-surface: "#2A1810"
  surface-container: "#F4DEB5"
  tertiary: "#B83609"
  on-tertiary: "#FFF6E6"
colors-dark:
  on-primary: "#2A1810"
  on-surface: "#FFF6E6"
  on-tertiary: "#FFF6E6"
  primary: "#FFF6E6"
  surface: "#2A1810"
  surface-container: "#3D2418"
  tertiary: "#E8542D"
typography:
  headline-display:
    fontFamily: "Rubik, Heebo, sans-serif"
    fontSize: 64px
    fontWeight: "800"
    lineHeight: 1.05
    letterSpacing: "-0.015em"
  headline-lg:
    fontFamily: "Rubik, Heebo, sans-serif"
    fontSize: 40px
    fontWeight: "700"
    lineHeight: 1.15
  headline-md:
    fontFamily: "Rubik, Heebo, sans-serif"
    fontSize: 28px
    fontWeight: "700"
    lineHeight: 1.25
  body-lg:
    fontFamily: "Heebo, sans-serif"
    fontSize: 18px
    fontWeight: "400"
    lineHeight: 1.6
  body-md:
    fontFamily: "Heebo, sans-serif"
    fontSize: 16px
    fontWeight: "400"
    lineHeight: 1.65
  body-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 14px
    fontWeight: "400"
    lineHeight: 1.55
  label-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 12px
    fontWeight: "700"
    lineHeight: 1.2
    letterSpacing: "0.1em"
rounded:
  none: 0px
  sm: 6px
  md: 14px
  lg: 24px
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
    rounded: "{rounded.lg}"
    padding: 14px 24px
  button-primary-hover:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  button-ghost:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.lg}"
    padding: 14px 24px
  card:
    backgroundColor: "{colors.surface-container}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: "{spacing.lg}"
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: 12px 16px
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

Shuk is built for Hebrew-first and bilingual interfaces.

### RTL layout

Set `dir="rtl"` on `<html>` for Hebrew pages. Use logical properties exclusively (`padding-inline-start`, `margin-inline-end`, `inset-inline-start`). Tailwind: `ps-*`, `me-*`, `start-*`. Never hardcode left or right, the system flips cleanly when the direction changes.

### Digits inside RTL flow

Use Latin digits for prices, dates, phone numbers, identifiers in both locales. Wrap mixed-direction content in `<bdi>` or apply `unicode-bidi: plaintext` so a price like "12 ₪" or a phone "03-1234567" stays readable. Prefer `dd/mm/yyyy` for dates in Hebrew UI.

### Nikkud

Shuk handles nikkud acceptably at body sizes (Heebo carries it well). For nikkud-heavy pages, override line-height to 1.85 on the affected nodes and add 0.03em letter-spacing to keep marks from colliding with descenders.

### Punctuation

In Hebrew copy use gershayim (״) and geresh (׳), not ASCII quotes. Use maqaf (־) for Hebrew compound words; ASCII hyphens stay inside code spans. Curly quotes for English copy.

### OpenType features

No special features required. Rubik and Heebo enable their default ligatures and contextual alternates; do not disable `liga` or `calt`.

### Accessibility

Maintain 4.5:1 contrast on body text. The default pairs (cocoa on cream, cream on cocoa, cream on paprika) all meet WCAG AA. If you tint text below `on-surface`, re-run a contrast check before shipping.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
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
```

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
