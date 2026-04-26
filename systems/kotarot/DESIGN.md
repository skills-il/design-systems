---
name: Headlines
version: 0.1.2
description: Dense Israeli news-portal. Saturated red CTA, hairline rules, square corners.
---

## Overview

Headlines is built for surfaces that publish faster than they polish: news desks, live tickers, sports feeds, breaking-event pages. Density is the point. Whitespace is rationed.

The visual language is rooted in the dominant Israeli portal aesthetic of the last twenty years, bold red CTA, crisp ink type on a cool grey paper, card grids divided by hairline rules, no shadows, no gradients, no playful curves. Use Headlines when scanability beats elegance.

## Colors

Two-temperature palette: cool ink on warm paper, with a single saturated red as the entire emergency vocabulary. Primary `#1B1B1B` for ledes; tertiary `#D80019` for breaking pills and the single CTA per viewport. Surface `#F5F5F4` is cool grey paper, never pure white. Surface-container `#FFFFFF` for cards on the grey.

## Typography

Heebo carries everything in three weights: 400 body, 700 headlines, 800 display lede at 56px. Captions use label-sm at 11px UPPERCASE with 0.08em tracking, print-masthead section labels (חדשות / כלכלה / ספורט).

## Layout

Tight spacing scale (`xs: 3, sm: 6, md: 10, lg: 16, xl: 24`). Cards butt against each other with 1-pixel separators. Multi-column desktop grids collapse to single-column on mobile but keep internal density.

## Shapes

All sharp. 0px radius on buttons, cards, inputs. Curves only on avatars (circular).

## Components

Buttons: primary fills with red, square corners, 8/16 padding. Cards: white on grey, 1px border, no shadow, square. Inputs: square, 1-pixel ink border, 8/12 padding. Focus ring is a 2-pixel red outline.

## Localization

Hebrew-first. Heebo handles both scripts. Use `<bdi>` around Latin numerals inside RTL flow ("1,200 ₪", "03-1234567"). Date format `dd/mm/yyyy` in Hebrew. Direction-aware CTA arrows (`←` RTL, `→` LTR). Logical CSS properties throughout.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
colors:
  primary: "#1B1B1B"
  surface: "#F5F5F4"
  tertiary: "#D80019"
  secondary: "#2A2A2A"
  on-primary: "#FFFFFF"
  on-surface: "#1B1B1B"
  on-tertiary: "#FFFFFF"
  on-secondary: "#FFFFFF"
  surface-container: "#FFFFFF"
colors-dark:
  primary: "#FFFFFF"
  surface: "#0A0A0A"
  tertiary: "#FF3145"
  secondary: "#D6D6D6"
  on-primary: "#0A0A0A"
  on-surface: "#F5F5F4"
  on-tertiary: "#FFFFFF"
  on-secondary: "#0A0A0A"
  surface-container: "#1A1A1A"
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
    fontSize: 11px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0.08em
  headline-lg:
    fontSize: 32px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.15
  headline-md:
    fontSize: 22px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
  headline-display:
    fontSize: 56px
    fontFamily: Heebo, sans-serif
    fontWeight: 800
    lineHeight: 1.05
    letterSpacing: -0.015em
spacing:
  lg: 16px
  md: 10px
  sm: 6px
  xl: 24px
  xs: 3px
  2xl: 40px
rounded:
  lg: 2px
  md: 2px
  sm: 0px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: 0px
    elevation: none
    textColor: "{colors.on-surface}"
    borderWidth: 1px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 8px 12px
    rounded: 0px
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 8px 16px
    rounded: 0px
    textColor: "{colors.on-tertiary}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.tertiary}"
  button-primary-hover:
    textColor: "{colors.on-primary}"
    backgroundColor: "{colors.primary}"
```

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: עכשיו: בריקינג.
- **EN**: Breaking now.

### Primary CTA

- **HE**: קראו עוד
- **EN**: Read more

### Error message

- **HE**: הכתבה כבר לא מתעדכנת. עברו לפיד החי.
- **EN**: This story has expired. See the live feed.
