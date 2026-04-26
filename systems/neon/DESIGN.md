---
name: Neon
version: 0.2.1
description: Tel Aviv signage at 2am, Hebrew-first. Jet surface, hot magenta accent, sharp grotesque type. Nocturnal, vivid, urban.
colors:
  primary: "#F0F0F8"
  on-primary: "#0A0A12"
  surface: "#0A0A12"
  on-surface: "#F0F0F8"
  surface-container: "#1A1A28"
  tertiary: "#FF2A8F"
  on-tertiary: "#0A0A12"
colors-dark:
  on-primary: "#000000"
  on-surface: "#FFFFFF"
  on-tertiary: "#000000"
  primary: "#FFFFFF"
  surface: "#000000"
  surface-container: "#0F0F1F"
  tertiary: "#FF45A0"
typography:
  headline-display:
    fontFamily: "Archivo Black, Heebo, sans-serif"
    fontSize: 72px
    fontWeight: "400"
    lineHeight: 1.0
    letterSpacing: "-0.03em"
  headline-lg:
    fontFamily: "Archivo Black, Heebo, sans-serif"
    fontSize: 44px
    fontWeight: "400"
    lineHeight: 1.05
    letterSpacing: "-0.02em"
  headline-md:
    fontFamily: "Heebo, sans-serif"
    fontSize: 28px
    fontWeight: "700"
    lineHeight: 1.2
    letterSpacing: "-0.01em"
  body-lg:
    fontFamily: "Heebo, sans-serif"
    fontSize: 17px
    fontWeight: "400"
    lineHeight: 1.55
  body-md:
    fontFamily: "Heebo, sans-serif"
    fontSize: 15px
    fontWeight: "400"
    lineHeight: 1.55
  body-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 13px
    fontWeight: "400"
    lineHeight: 1.5
  label-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 12px
    fontWeight: "700"
    lineHeight: 1.2
    letterSpacing: "0.12em"
rounded:
  none: 0px
  sm: 2px
  md: 6px
  lg: 999px
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
    padding: 12px 22px
  button-primary-hover:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  button-ghost:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.lg}"
    padding: 12px 22px
  card:
    backgroundColor: "{colors.surface-container}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: "{spacing.lg}"
  input:
    backgroundColor: "{colors.surface-container}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: 10px 14px
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

Neon is built Hebrew-first for nightlife, events, and youth-culture surfaces.

### RTL layout

`dir="rtl"` on `<html>` for Hebrew. Logical properties, `ps-*`, `me-*`, `start-*`, only. The asymmetric layouts flip cleanly when authored against logical sides.

### Digits inside RTL flow

Latin digits everywhere, event times, prices, addresses, ages. Wrap mixed-direction strings in `<bdi>` or `unicode-bidi: plaintext`. Time formats use 24-hour (`22:00`) consistently across locales for clarity.

### Nikkud

Neon is not built for nikkud. Educational or religious content should use Iton, Kodesh, or Lyl Shabat instead.

### Punctuation

Hebrew gershayim (״) and geresh (׳); maqaf (־) for compounds. Curly quotes in English copy. ASCII hyphens stay inside artist names and venue names.

### OpenType features

Tabular numerals (`tnum`) are recommended for event listings: enable `font-variant-numeric: tabular-nums` on times and prices so they align in a vertical list. Archivo Black ships a single weight without alternates, keep all OpenType features on default.

### Accessibility

The cool-white-on-jet pair clears WCAG AAA. The magenta-on-jet pair clears AA at large text only, never use the accent for body text. The white-on-magenta pair clears AA. Always pair magenta with white text, never with the cool primary.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
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
```

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
