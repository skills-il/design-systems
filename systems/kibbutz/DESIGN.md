---
name: Kibbutz
description: 1950s Bezalel poster collectivism, Hebrew-first. Wheat cream, olive ink, dry working palette. Communal, idealistic, hand-set.
colors:
  primary: "#2D2A1F"
  on-primary: "#F5EFD8"
  surface: "#F5EFD8"
  on-surface: "#2D2A1F"
  surface-container: "#DDD0AE"
  accent: "#4F6B2E"
  on-accent: "#F5EFD8"
typography:
  display:
    fontFamily: "Assistant, Heebo, sans-serif"
    fontSize: 60px
    fontWeight: "800"
    lineHeight: 1.05
    letterSpacing: "-0.02em"
  headline-lg:
    fontFamily: "Assistant, Heebo, sans-serif"
    fontSize: 38px
    fontWeight: "700"
    lineHeight: 1.15
  headline-md:
    fontFamily: "Assistant, Heebo, sans-serif"
    fontSize: 26px
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
    lineHeight: 1.6
  body-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 14px
    fontWeight: "400"
    lineHeight: 1.55
  caps:
    fontFamily: "Assistant, Heebo, sans-serif"
    fontSize: 12px
    fontWeight: "700"
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
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
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

Kibbutz draws from mid-century Bezalel poster art — Yohanan Simon, Asher Hoffman, the cooperative-press aesthetic of the early state. Hand-set type, dry earth palette, poster-flat colors, no shadow. Use Kibbutz for civic-cultural surfaces, museum sites, agricultural co-ops, education, anything with a long memory.

Hebrew-first. Assistant carries display sizes — its humanist sans feel matches the printed-poster character without going kitsch. Heebo carries body. Both bilingual; Latin glyphs match optical weight cleanly.

## Colors

Earth-stained working palette.

- **Primary (#2D2A1F)**: olive-warm ink, the kind a 60-year-old screenprint settles into.
- **On primary (#F5EFD8)**: wheat cream sitting on top of primary.
- **Surface (#F5EFD8)**: wheat cream, the poster paper.
- **On surface (#2D2A1F)**: ink on paper.
- **Surface container (#DDD0AE)**: faded poster background tone, for cards and callouts.
- **Accent (#4F6B2E)**: kibbutz olive — the green of irrigated fields at noon, not a fashion green.
- **On accent (#F5EFD8)**: cream on olive.

The palette is intentionally muted. If you find yourself reaching for a brighter green, you're outside the system — pick a different system instead.

## Typography

Assistant for display gives Kibbutz its hand-set character. Heebo for body keeps the system bilingual and readable. Both pair without optical break across scripts.

Display tracking is slightly tightened (-0.02em). Body line-height holds at 1.6 for both Hebrew and English.

## Layout

Poster-grid sensibility. 8 point base, container padding 16 on mobile, 64 on desktop. Cards align on a strict 12-column grid; no off-grid floats. The system rewards alignment; misalignment reads as carelessness.

Use logical properties throughout — Kibbutz was authored Hebrew-first but flips cleanly.

## Elevation & Depth

None. Posters do not have shadows; neither does this system. Distinguish layers by tone (`surface` vs `surface-container`) and by 1-pixel ink rules. If you need a card to "lift," tighten its padding instead.

## Shapes

Minimal rounding. 2-pixel radius on buttons, inputs, and chips; 4 pixels on cards. The system is intentionally hard-edged — softness reads as digital and breaks the print metaphor.

## Components

- **Buttons**: primary fills with olive, cream text, 2-pixel rounding. Ghost is cream with an ink border. Hover on primary swaps to ink fill — the olive recedes, the depth steps forward.
- **Cards**: surface-container background, 4-pixel rounding, 24-pixel internal padding. Heading separates from body with a single 1-pixel ink rule, full-width, on the inline-start side.
- **Inputs**: cream background, 1-pixel ink border, 2-pixel rounding, 16-pixel body. Focus ring is a 2-pixel olive outline.

## Do's and Don'ts

Do let the wheat cream carry. Avoid pure white anywhere — it fights the posters.
Do align everything to the 8-point grid. The system rewards discipline.
Do use the olive for one primary action per page; demote secondaries to ghost.

Don't add gradients, shadows, or glass. Posters are flat or they're not posters.
Don't introduce a brighter green. The dryness is the point.
Don't use Hebrew script in italics — it reads as forced.

## Localization

Kibbutz is built Hebrew-first with bilingual cultural contexts (museum captions, archive metadata).

### RTL layout

`dir="rtl"` on `<html>` for Hebrew. Logical properties only. The poster-grid flips without modification.

### Digits inside RTL flow

Hebrew calendar dates appear inline with editorial copy when the historical context matters; Latin numerals for archive identifiers, catalog numbers, and modern dates. Wrap mixed-direction strings in `<bdi>`. Prefer `yyyy` in archive metadata for sortability.

### Nikkud

Kibbutz handles nikkud at body sizes for educational content. For poetry or biblical citation, override line-height to 1.95 and add 0.04em letter-spacing.

### Punctuation

Hebrew gershayim (״) and geresh (׳) where Hebrew abbreviations occur. Maqaf (־) inside compounds. Curly quotes inside English captions. The system never uses em-dashes.

### OpenType features

Default ligatures and contextual alternates remain enabled in both Assistant and Heebo. For archive-table headings, `font-variant-caps: small-caps` is acceptable on Latin captions to add a quiet hierarchical layer without breaking the poster aesthetic.

### Accessibility

All default pairs clear WCAG AA. The cream surface drops contrast slightly versus pure white; never tint body below `on-surface` and re-run a contrast check on any custom token.
