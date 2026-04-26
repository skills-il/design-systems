---
name: Coast
version: 0.1.1
description: Tel Aviv Mediterranean. Bone-white surfaces, deep ocean primary, warm sand secondary, sea-foam accent.
---

## Overview

Coast is a Mediterranean design system rooted in Tel Aviv's particular light: bone-white limestone, ocean blue, warm sand, sea-foam shadows under a 2pm sun. Editorial in tone, hospitable in spacing, photo-friendly in chrome.

Use Coast for hospitality (boutique hotels, restaurants, wineries), travel editorial, lifestyle commerce, beach-adjacent SaaS. Wrong for transactional gov surfaces, news portals, dense classifieds.

## Colors

Primary `#1E5F8C` deep ocean, headlines, primary CTAs, navigation. Secondary `#D4906B` warm terracotta sand for accents. Tertiary `#5BA8B8` turquoise sea-foam, hover state on primary buttons (transitions ocean → seafoam). Surface `#F9F4E8` bone-white limestone. Surface-container `#FFFFFF` for actual cards, white-on-bone gives the soft contrast Tel Aviv stucco walls have at midday.

## Typography

Two families. Display uses Frank Ruhl Libre, modern Hebrew serif with optical Latin coverage, weight 400 at 64px gives editorial gravitas. Body uses Heebo for both scripts, generous 1.7 line-height for long-form reading flow. The serif/sans contrast is intentional, Frank Ruhl on a hero against Heebo body reads like a magazine layout.

## Layout

Airy by default. `lg: 32px`, `xl: 52px`, `2xl: 88px`. Hero sections breathe. Image-led layouts with full-bleed photos and asymmetric text columns.

## Shapes

Soft and rounded. `lg: 24px` on cards, `9999px` (full pill) on buttons and search inputs. The pill is essential, it's the visual signature that separates Coast from every other Hebrew system.

## Components

Buttons: ocean primary, full pill, 12/28 padding. Hover transitions to seafoam under 120ms. Cards: white on bone, no border, 24px corners. Shadow is the chrome: `0 16px 40px rgba(30,95,140,0.12)`, diffused, ocean-tinted. Inputs: bone surface, full pill, 12/18 padding.

## Localization

Hebrew-first. Frank Ruhl Libre is a Hebrew-native serif (Hebrew Type Society) and pairs cleanly with Heebo body. Date format `dd MMMM yyyy` in Hebrew ("12 ביוני 2026"). Long-form Hebrew benefits from generous line-height, 1.7 is non-negotiable for the Coast voice. Wrap numerical content in `<bdi>` inside RTL flow. Currency stays as ₪.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
colors:
  primary: "#1E5F8C"
  surface: "#F9F4E8"
  tertiary: "#5BA8B8"
  secondary: "#D4906B"
  on-primary: "#F9F4E8"
  on-surface: "#2A3540"
  on-tertiary: "#FFFFFF"
  on-secondary: "#FFFFFF"
  surface-container: "#FFFFFF"
colors-dark:
  primary: "#76B5D9"
  surface: "#0A1828"
  tertiary: "#7DC4CE"
  secondary: "#E8B795"
  on-primary: "#0A1828"
  on-surface: "#F9F4E8"
  on-tertiary: "#0A1828"
  on-secondary: "#0A1828"
  surface-container: "#142A40"
typography:
  body-lg:
    fontSize: 17px
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
    fontSize: 11px
    fontFamily: Heebo, sans-serif
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.12em
  headline-lg:
    fontSize: 40px
    fontFamily: Frank Ruhl Libre, serif
    fontWeight: 600
    lineHeight: 1.15
  headline-md:
    fontSize: 26px
    fontFamily: Frank Ruhl Libre, serif
    fontWeight: 600
    lineHeight: 1.25
  headline-display:
    fontSize: 64px
    fontFamily: Frank Ruhl Libre, serif
    fontWeight: 400
    lineHeight: 1.1
    letterSpacing: -0.01em
spacing:
  lg: 32px
  md: 20px
  sm: 12px
  xl: 52px
  xs: 6px
  2xl: 88px
rounded:
  lg: 24px
  md: 16px
  sm: 8px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.lg}"
    elevation: 0 16px 40px rgba(30,95,140,0.12)
    textColor: "{colors.on-surface}"
    borderWidth: 0px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 12px 18px
    rounded: 9999px
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 12px 28px
    rounded: 9999px
    textColor: "{colors.on-primary}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.primary}"
  button-primary-hover:
    textColor: "{colors.on-tertiary}"
    backgroundColor: "{colors.tertiary}"
```

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: אור של ים, אחר צהריים שקט.
- **EN**: Sea light, slow afternoon.

### Primary CTA

- **HE**: שמרו את החדר
- **EN**: Reserve the room

### Error message

- **HE**: אין זמינות בתאריכים האלה. לבחור שבוע אחר?
- **EN**: No availability for these dates. Pick a different week?
