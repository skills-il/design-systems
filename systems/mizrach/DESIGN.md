---
name: Mizrach
description: Eastern Mediterranean cultural depth, Hebrew-first. Bone surface, deep indigo ink, saffron accent. Layered, hospitable, calm.
colors:
  primary: "#1F2347"
  on-primary: "#F7F1E3"
  surface: "#F7F1E3"
  on-surface: "#1F2347"
  surface-container: "#ECE2C8"
  accent: "#E8A22A"
  on-accent: "#1F2347"
typography:
  display:
    fontFamily: "David Libre, Heebo, serif"
    fontSize: 60px
    fontWeight: "600"
    lineHeight: 1.1
    letterSpacing: "-0.01em"
  headline-lg:
    fontFamily: "David Libre, Heebo, serif"
    fontSize: 38px
    fontWeight: "600"
    lineHeight: 1.15
  headline-md:
    fontFamily: "David Libre, Heebo, serif"
    fontSize: 26px
    fontWeight: "600"
    lineHeight: 1.3
  body-lg:
    fontFamily: "Heebo, sans-serif"
    fontSize: 18px
    fontWeight: "400"
    lineHeight: 1.7
  body-md:
    fontFamily: "Heebo, sans-serif"
    fontSize: 16px
    fontWeight: "400"
    lineHeight: 1.7
  body-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 14px
    fontWeight: "400"
    lineHeight: 1.6
  caps:
    fontFamily: "Heebo, sans-serif"
    fontSize: 12px
    fontWeight: "600"
    lineHeight: 1.2
    letterSpacing: "0.1em"
rounded:
  none: 0px
  sm: 4px
  md: 8px
  lg: 16px
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
    rounded: "{rounded.md}"
    padding: 12px 22px
  button-primary-hover:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  button-ghost:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: 12px 22px
  card:
    backgroundColor: "{colors.surface-container}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.lg}"
    padding: "{spacing.lg}"
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: 12px 16px
---

## Overview

Mizrach draws from Eastern Mediterranean cultural surfaces — whitewashed Jaffa walls in late afternoon, the indigo of Yemenite embroidery, baskets of dried saffron and sumac at a Friday market. Hospitable without theatrics. Use Mizrach for cultural surfaces, food and dining, hospitality, heritage archives, anything that should feel rooted but contemporary.

Hebrew-first. David Libre carries display — Yanek Iontef's classical Hebrew serif descended from Ladino prayer-book typography fits the system's Mediterranean rootedness. Heebo carries body. Both bilingual.

## Colors

Three working colors plus surface-container.

- **Primary (#1F2347)**: deep indigo, the color of an embroidered border at dusk.
- **On primary (#F7F1E3)**: bone cream sitting on indigo.
- **Surface (#F7F1E3)**: bone — whitewashed Jaffa wall, slightly warm, never pure white.
- **On surface (#1F2347)**: indigo on bone.
- **Surface container (#ECE2C8)**: a deeper bone-cream, for cards and side panels.
- **Accent (#E8A22A)**: saffron — warm and earthy without slipping into the dim amber territory of dusk systems. The single attention-getter.
- **On accent (#1F2347)**: indigo on saffron. The pair is unusual but reads cleanly because the saffron stays warm rather than going neon.

The palette is intentionally rooted — neither the indigo nor the saffron is pulled toward digital brightness. Avoid bright orange, bright yellow, or any saturation push.

## Typography

David Libre at display weight 600 carries warmth without pretense — its Hebrew letterforms have a softer counter than Frank Ruhl Libre, with subtle stroke-contrast that reads as cultural rather than ceremonial. Heebo at body keeps reading texture humanist and consistent across scripts. Body line-height runs 1.7 for Hebrew breathing room.

The system pairs Hebrew and Arabic-influenced typographic mood without using actual Arabic — that boundary belongs to designers fluent in those traditions, not to a general-purpose system.

## Layout

Generous, columnar. 8 point base, container padding 24 on mobile, 56 on desktop. Archive grids favor 2-column on tablet, 3-column on desktop with generous gaps. Cards may overlap slightly on featured surfaces — the asymmetry references textile patterns.

Logical properties everywhere; the system reads with equal weight in both directions.

## Elevation & Depth

A whisper of depth. Cards may carry `0 2px 12px rgba(31, 35, 71, 0.08)` to lift them off the bone surface. Buttons stay flat. The system is layered through tone, not shadow.

## Shapes

Soft rounding. 8 pixels on inputs and buttons, 16 pixels on cards. The rounding references arched doorways without literal-mindedness; sharper corners read as European institutional and miss the regional warmth.

## Components

- **Buttons**: primary fills with saffron, indigo text, 8-pixel rounding. Ghost is bone with indigo outline. Hover on primary deepens to indigo fill — the warmth steps back, the depth steps forward.
- **Cards**: surface-container background, 16-pixel rounding, 24-pixel padding, soft indigo shadow. Headers carry a 1-pixel indigo border-inline-start as a quiet signature.
- **Inputs**: bone background, 1-pixel indigo border at 0.4 alpha, 8-pixel rounding, 16-pixel body. Focus ring is a 2-pixel saffron outline.

## Do's and Don'ts

Do use generous whitespace. Mizrach was built to feel uncrowded.
Do let textile patterns and architectural photography sit on the bone surface — the palette frames them.
Do use the saffron sparingly. Its warmth carries when it's rare.

Don't reach for bright digital colors. The system's restraint is its rootedness.
Don't add a second accent. Demote actions to ghost or to body-md links.
Don't sharpen the rounding. The softness references arched openings, not playfulness.

## Localization

Mizrach is built Hebrew-first with bilingual cultural-content support.

### RTL layout

`dir="rtl"` on `<html>` for Hebrew. Logical properties only. The system was authored Hebrew-first; English flows cleanly through the same component shapes when `dir` flips.

### Digits inside RTL flow

Hebrew calendar dates appear inline with cultural copy where the context demands it; Latin numerals for archive identifiers, addresses, prices. Wrap mixed-direction strings in `<bdi>`. Prefer `dd MMMM yyyy` in Hebrew with month names spelled out.

### Nikkud

Mizrach handles nikkud well — David Libre carries niqqud cleanly and the bone background reduces eye strain on dense prayer texts. For nikkud-heavy pages override line-height to 1.9.

### Punctuation

Gershayim (״) and geresh (׳) for Hebrew abbreviations. Maqaf (־) inside compounds. Curly quotes in English. The system never uses em-dashes.

### OpenType features

David Libre's contextual alternates and ligatures are essential — leave `calt` and `liga` on. Recommended for archive metadata: `font-variant-numeric: oldstyle-nums` to keep dates in body prose from disrupting the line.

### Accessibility

All default pairs clear WCAG AA. The indigo-on-bone pair clears AAA at body-md. Saffron is acceptable for fills and for large display text only; never use it for inline body links.
