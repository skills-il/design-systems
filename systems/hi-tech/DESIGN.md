---
name: Hi-Tech
version: 0.2.1
description: Rothschild high-rise minimalism, Hebrew-first. White surface, deep navy ink, electric blue accent. Sharp, ambitious, technical.
colors:
  primary: "#0A1A2F"
  on-primary: "#FFFFFF"
  surface: "#FFFFFF"
  on-surface: "#0A1A2F"
  surface-container: "#F4F6FA"
  tertiary: "#2456E8"
  on-tertiary: "#FFFFFF"
colors-dark:
  on-primary: "#0A1A2F"
  on-surface: "#E8EEF6"
  on-tertiary: "#0A1A2F"
  primary: "#E8EEF6"
  surface: "#0A1A2F"
  surface-container: "#0F2440"
  tertiary: "#5C8AFF"
typography:
  headline-display:
    fontFamily: "Space Grotesk, Heebo, sans-serif"
    fontSize: 64px
    fontWeight: "700"
    lineHeight: 1.05
    letterSpacing: "-0.025em"
  headline-lg:
    fontFamily: "Space Grotesk, Heebo, sans-serif"
    fontSize: 40px
    fontWeight: "700"
    lineHeight: 1.1
    letterSpacing: "-0.02em"
  headline-md:
    fontFamily: "Space Grotesk, Heebo, sans-serif"
    fontSize: 28px
    fontWeight: "500"
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
    fontFamily: "Space Grotesk, Heebo, sans-serif"
    fontSize: 12px
    fontWeight: "500"
    lineHeight: 1.2
    letterSpacing: "0.08em"
rounded:
  none: 0px
  sm: 4px
  md: 8px
  lg: 12px
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
    rounded: "{rounded.md}"
    padding: 10px 18px
  button-primary-hover:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  button-ghost:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: 10px 18px
  card:
    backgroundColor: "{colors.surface-container}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.lg}"
    padding: "{spacing.lg}"
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: 10px 14px
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

Hi-Tech is built for Hebrew-first and bilingual product surfaces.

### RTL layout

Set `dir="rtl"` on `<html>` for Hebrew. Use logical properties only (`padding-inline-start`, `inset-inline-end`). Tailwind: `ps-*`, `me-*`, `start-*`. Sidebars flip from right to left when `dir` changes; nothing should break.

### Digits inside RTL flow

Use Latin digits for prices, dates, phone numbers, version strings, and identifiers in both locales. Wrap mixed-direction strings in `<bdi>` or `unicode-bidi: plaintext`. Prefer `dd/mm/yyyy` in Hebrew UI; ISO 8601 inside engineering surfaces (logs, audit tables).

### Nikkud

Hi-Tech is not optimized for nikkud. Religious or educational nikkud-heavy content should use a heritage system (Iton, Kodesh) instead, or override line-height to 1.85 and letter-spacing to 0.03em on affected nodes.

### Punctuation

Hebrew copy uses gershayim (״) and geresh (׳); maqaf (־) for Hebrew compounds. English copy uses curly quotes. ASCII hyphens are fine inside code spans, command names, and CLI examples.

### OpenType features

Space Grotesk's contextual alternates (`calt`) are on by default, do not disable. Tabular numerals (`tnum`) are recommended for dashboards: enable via `font-variant-numeric: tabular-nums` on numeric columns.

### Accessibility

The default pairs all clear WCAG AA. Be careful with the cool gray-blue surface-container on white, large text only at low contrast pairs, never body-sm.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
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
```

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
