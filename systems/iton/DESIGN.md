---
name: Broadsheet
description: Hebrew newspaper editorial gravity. Newsprint cream, deep ink, indigo signature accent. Columnar, considered, literary.
colors:
  primary: "#14171F"
  on-primary: "#F8F4EC"
  surface: "#F8F4EC"
  on-surface: "#14171F"
  surface-container: "#ECE5D5"
  accent: "#2C4F8F"
  on-accent: "#F8F4EC"
typography:
  display:
    fontFamily: "Alef, Heebo, sans-serif"
    fontSize: 60px
    fontWeight: "700"
    lineHeight: 1.1
    letterSpacing: "-0.01em"
  headline-lg:
    fontFamily: "Alef, Heebo, sans-serif"
    fontSize: 40px
    fontWeight: "700"
    lineHeight: 1.15
  headline-md:
    fontFamily: "Alef, Heebo, sans-serif"
    fontSize: 26px
    fontWeight: "700"
    lineHeight: 1.25
  body-lg:
    fontFamily: "Heebo, sans-serif"
    fontSize: 18px
    fontWeight: "400"
    lineHeight: 1.65
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
    fontSize: 11px
    fontWeight: "700"
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
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
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
    padding: 10px 14px
---

## Overview

Broadsheet draws from the printed Hebrew newspaper — Haaretz front pages, the cultural supplement on a Friday morning, the smell of newsprint and a third cup of coffee. Use Iton for long-form content surfaces: editorials, journals, knowledge bases, archives, anything that wants to be read slowly and trusted.

Hebrew-first by construction. Alef, a quietly classical Hebrew face, carries every display and headline size. Heebo carries body. Both ship matching Latin glyphs, so a citation in English doesn't break the column.

## Colors

Newsprint palette with one signature blue.

- **Primary (#14171F)**: deep newsprint ink, slightly warm.
- **On primary (#F8F4EC)**: paper cream that sits on the ink.
- **Surface (#F8F4EC)**: newsprint cream, the page itself.
- **On surface (#14171F)**: ink on the page.
- **Surface container (#ECE5D5)**: aged margin tone, for pull quotes, sidebars, and bylines.
- **Accent (#2C4F8F)**: signature indigo, the color the editor uses for corrections. CTAs and links.
- **On accent (#F8F4EC)**: cream on accent.

The accent is a deep, dignified blue, never a bright digital one. Iton is not trying to be modern; it's trying to be permanent.

## Typography

Alef is the workhorse for display. It reads as a calm, considered Hebrew face — book-like rather than monumental. Heebo handles every body size with generous line-height (1.65 to 1.7) so long-form columns breathe.

Display weight stays at 700; the system never goes thinner than 400 on body. Iton avoids hairline weights — they read as cosmetic rather than considered.

## Layout

Columnar. 8 point base, container padding 24 on mobile, 80 on desktop. Long-form content is constrained to a 65-character measure (roughly 720px at 18px body); never let articles run edge-to-edge. Sidebar pull quotes use surface-container with a 2-pixel accent border-inline-start.

Logical properties everywhere — the columns flip cleanly between RTL and LTR.

## Elevation & Depth

None. Iton is paper, and paper does not float. Distinguish surfaces with the cream and aged-margin tones, not with shadow. Use a 1-pixel ink rule between sections when whitespace alone is not enough.

## Shapes

Sharp. Buttons and inputs are 0-radius rectangles. Cards round to 2 pixels — barely perceptible, just enough to read as digital. Avatars stay circular.

## Components

- **Buttons**: primary uses signature indigo with cream text, no rounding, no shadow. Ghost uses cream with ink text and a 1-pixel ink border. Hover on primary swaps the indigo to ink. The motion is restrained.
- **Cards**: surface-container background, 2-pixel rounding, 24-pixel padding. Pull quotes use a 2-pixel border-inline-start in accent. No shadows.
- **Inputs**: cream background, 1-pixel ink border, 0 rounding, 16-pixel body-md. Focus ring is a 2-pixel indigo outline-offset.

## Do's and Don'ts

Do constrain text to a readable measure. Long lines break this system's promise.
Do use the indigo for links inline; underline on hover is sufficient.
Do let pull quotes do the visual work. They are the system's signature.

Don't reach for sans-serif display. Alef is the editorial voice.
Don't introduce a second accent. Iton has one editor's pen.
Don't soften the rounding. The corners are part of the gravity.

## Localization

Iton was built for Hebrew long-form content with bilingual citation support.

### RTL layout

Set `dir="rtl"` for Hebrew. Long-form columns flip cleanly because the text-measure constraint is logical, not directional. Tailwind logical properties (`ps-*`, `me-*`) only.

### Digits inside RTL flow

Hebrew dates use Hebrew calendar where the editorial context demands it (heritage articles, religious calendars), Latin numerals otherwise. Years stay Latin. Wrap mixed-direction runs in `<bdi>`. Prefer `dd MMMM yyyy` (e.g. 14 בנובמבר 2025) for Hebrew article datelines.

### Nikkud

Iton handles nikkud well at body sizes — Heebo's nikkud metrics are conservative. For poetry and religious citations, override line-height to 1.95 to give marks visible breathing room.

### Punctuation

Use gershayim (״) for Hebrew abbreviations (e.g. ארה״ב), geresh (׳) for single-letter abbreviations. Maqaf (־) for Hebrew compound words (אי-שם, בית-קפה). En-dash (–) inside English citations; em-dash is forbidden site-wide.

### OpenType features

Heebo and Alef enable default ligatures and contextual alternates. Recommended for editorial: `font-variant-numeric: oldstyle-nums` inside body prose (Heebo supports `onum`) so dates inline with text don't disrupt the line rhythm.

### Accessibility

All default pairs clear WCAG AA at body and AAA at body-lg. The cream paper background reduces contrast slightly compared to pure white but stays above 4.5:1 with the deep ink. Never tint body text below `on-surface`.
