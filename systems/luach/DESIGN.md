---
name: Bulletin
version: 0.1.2
description: Israeli classifieds utilitarian. Yellow-cream paper, ultra-dense list rows, square corners, prices in red.
---

## Overview

Bulletin is for surfaces that show lots of small things in rows: apartment listings, used cars, second-hand furniture, jobs, classifieds, marketplace inventory. Unmistakably Israeli classified-board, warm yellow-cream paper, white listing rows, blue links, red prices. Density is utility; decoration is friction.

## Colors

Primary `#1F1F1F` ink for body. Secondary `#0061A8` link blue for every clickable noun. Tertiary `#D8001A` prices and "discounted" markers, the eye locks onto it. Surface `#FFFCEB` cream-yellow paper carries the page; never replaced with pure white. Surface-container `#FFFFFF` for the listing rows themselves.

Dark mode flips the relationship: yellow becomes the bright primary tone (`#FFE066`), surfaces go warm-near-black.

## Typography

Heebo only. No display serif. Largest is 36px and that's already aggressive, most surfaces live at body-md (14px) or body-sm (12px). Density of information beats hierarchy of size. Tight line-heights (1.2-1.3 headings, 1.5 body).

## Layout

Ultra-tight spacing (`xs: 2, sm: 4, md: 8, lg: 12`). Listing rows have 8-12px vertical padding and a 1-pixel separator. Photo thumbnails are small (96-120px), description carries the listing.

## Shapes

Square or near-square. 2px corners on cards, buttons, inputs. Circular only on avatars.

## Components

Buttons: ink primary on cream, 2px corners. Cards (listing rows): white on cream, 1px border, 2px corners, 8-pixel internal padding. Hover lifts border to 24% opacity instead of adding shadow. Inputs: cream background with 1-pixel ink border.

## Localization

Hebrew-first. Numbers (prices, sqm, phones, listing IDs) appear LTR inside RTL flow; wrap them in `<bdi>` ("1,250,000 ₪", "85 מ״ר", "052-123-4567"). "Ago" timestamps in natural Israeli Hebrew ("לפני 3 שעות", "אתמול", "ביום ראשון"). Use ש״ח or ₪ for shekel; pick one per surface and stay consistent.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
colors:
  primary: "#1F1F1F"
  surface: "#FFFCEB"
  tertiary: "#D8001A"
  secondary: "#0061A8"
  on-primary: "#FFFCEB"
  on-surface: "#1F1F1F"
  on-tertiary: "#FFFFFF"
  on-secondary: "#FFFFFF"
  surface-container: "#FFFFFF"
colors-dark:
  primary: "#FFE066"
  surface: "#1A1A14"
  tertiary: "#FF6679"
  secondary: "#5BA8FF"
  on-primary: "#1F1F1F"
  on-surface: "#FFFCEB"
  on-tertiary: "#0A0A0A"
  on-secondary: "#0A0A0A"
  surface-container: "#262620"
typography:
  body-lg:
    fontSize: 15px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.5
  body-md:
    fontSize: 14px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.5
  body-sm:
    fontSize: 12px
    fontFamily: Heebo, sans-serif
    fontWeight: 400
    lineHeight: 1.4
  label-sm:
    fontSize: 10px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0.06em
  headline-lg:
    fontSize: 24px
    fontFamily: Heebo, sans-serif
    fontWeight: 700
    lineHeight: 1.2
  headline-md:
    fontSize: 18px
    fontFamily: Heebo, sans-serif
    fontWeight: 600
    lineHeight: 1.3
  headline-display:
    fontSize: 36px
    fontFamily: Heebo, sans-serif
    fontWeight: 800
    lineHeight: 1.1
spacing:
  lg: 12px
  md: 8px
  sm: 4px
  xl: 20px
  xs: 2px
  2xl: 32px
rounded:
  lg: 4px
  md: 2px
  sm: 2px
  none: 0px
components:
  card:
    padding: "{spacing.md}"
    rounded: 2px
    elevation: none
    textColor: "{colors.on-surface}"
    borderWidth: 1px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 6px 10px
    rounded: 2px
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 8px 14px
    rounded: 2px
    textColor: "{colors.on-primary}"
    typography: "{typography.body-md}"
    backgroundColor: "{colors.primary}"
```

## Examples

Reference snippets in the system's voice. Use these to calibrate brand
tone in headlines, CTAs, and error states; do not copy verbatim into
production surfaces.

### Hero

- **HE**: דירה, רכב, ריהוט. שורה אחר שורה.
- **EN**: Apartment, car, furniture. One row at a time.

### Primary CTA

- **HE**: צפו במודעה
- **EN**: View listing

### Error message

- **HE**: המפרסם הסיר את המודעה.
- **EN**: Listing removed by owner.
