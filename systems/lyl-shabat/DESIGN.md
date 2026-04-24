---
name: Friday Dusk
description: Friday-night candlelight, Hebrew-first. Plum primary, candle ivory surface, warm amber accent. Intimate, ceremonial, restful.
colors:
  primary: "#2A1129"
  on-primary: "#FBE9C7"
  surface: "#FBE9C7"
  on-surface: "#2A1129"
  surface-container: "#E9D2A6"
  accent: "#C9783A"
  on-accent: "#2A1129"
typography:
  display:
    fontFamily: "Frank Ruhl Libre, Assistant, serif"
    fontSize: 64px
    fontWeight: "500"
    lineHeight: 1.1
    letterSpacing: "-0.005em"
  headline-lg:
    fontFamily: "Frank Ruhl Libre, Assistant, serif"
    fontSize: 40px
    fontWeight: "500"
    lineHeight: 1.15
  headline-md:
    fontFamily: "Frank Ruhl Libre, Assistant, serif"
    fontSize: 26px
    fontWeight: "500"
    lineHeight: 1.3
  body-lg:
    fontFamily: "Assistant, sans-serif"
    fontSize: 18px
    fontWeight: "400"
    lineHeight: 1.7
  body-md:
    fontFamily: "Assistant, sans-serif"
    fontSize: 16px
    fontWeight: "400"
    lineHeight: 1.7
  body-sm:
    fontFamily: "Assistant, sans-serif"
    fontSize: 14px
    fontWeight: "400"
    lineHeight: 1.6
  caps:
    fontFamily: "Assistant, sans-serif"
    fontSize: 12px
    fontWeight: "600"
    lineHeight: 1.2
    letterSpacing: "0.1em"
rounded:
  none: 0px
  sm: 6px
  md: 12px
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
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
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

Friday Dusk is the system of the late afternoon, the moment between hurry and rest. Candle ivory surface, deep plum primary, warm amber driver. Use Lyl Shabat for hospitality, family-oriented surfaces, prayer apps, journaling, anything that asks the reader to slow down.

Hebrew-first. Frank Ruhl Libre at display sizes carries a soft, modern Hebrew serif character; Assistant at body keeps the reading texture humanist and warm. Both bilingual.

## Colors

Candlelight palette, dim and warm.

- **Primary (#2A1129)**: deep plum, the color of the sky after the candles are lit.
- **On primary (#FBE9C7)**: candle ivory sitting on the plum.
- **Surface (#FBE9C7)**: candle ivory, the page itself.
- **On surface (#2A1129)**: plum text on ivory.
- **Surface container (#E9D2A6)**: deeper warm cream, for cards and quiet panels.
- **Accent (#C9783A)**: warm amber — the color of the candle flame seen through a glass holder.
- **On accent (#2A1129)**: plum on amber. Dark text on the warm fill keeps the candle metaphor while clearing AA contrast.

The palette is intentionally low-saturation. Bright colors pull the reader into action; this system is supposed to settle them.

## Typography

Frank Ruhl Libre at medium weight (500) gives the headlines warmth without preachy gravity. Assistant for body adds humanist rhythm to long passages. Body line-height runs 1.7 — generous, slow.

The display weight intentionally stays at 500 rather than 700. Heavy headlines feel monumental; this system wants intimate.

## Layout

Soft, generous. 8 point base, container padding 24 on mobile, 56 on desktop. Cards rest on a single column on phones, expand to a 2-column grid at tablet, never more than 3-column on desktop. The system rewards air over density.

Logical properties everywhere. Lyl Shabat reads beautifully in both directions.

## Elevation & Depth

A soft warm glow, used sparingly. Cards may carry a `0 4px 24px rgba(42, 17, 41, 0.08)` shadow to suggest candlelight from above. Buttons stay flat. No glass effects.

## Shapes

Generous rounding. 12 pixels on inputs and buttons, 24 pixels on cards. The softness is part of the candlelight metaphor; sharp corners read as institutional and break the mood.

## Components

- **Buttons**: primary uses warm amber with ivory text, 24-pixel rounding. Ghost is ivory with plum outline. Hover on primary deepens to plum fill — like the room dimming as the wick burns down.
- **Cards**: surface-container background, 12-pixel rounding, 24-pixel padding, soft warm shadow. Headers separate from body with whitespace, never with rules.
- **Inputs**: ivory background, 1-pixel plum border, 12-pixel rounding, 16-pixel body. Focus ring is a 2-pixel amber outline plus a soft `0 0 0 4px rgba(201, 120, 58, 0.16)` halo.

## Do's and Don'ts

Do leave generous whitespace. The system is built to feel uncluttered.
Do use Hebrew at display weight (500) — it reads more like a printed greeting than a billboard.
Do let the amber rest. One CTA per viewport, ideally per section.

Don't reach for blue or cool tones. The system is warm by definition.
Don't use heavy display weights (700+). Lyl Shabat whispers.
Don't use bold sans-serif headlines. The Frank Ruhl warmth is the voice.

## Localization

Lyl Shabat was built Hebrew-first with bilingual ceremonial-content support.

### RTL layout

`dir="rtl"` for Hebrew. Logical properties only — `padding-inline-start`, `inset-inline-end`, Tailwind `ps-*`, `me-*`, `start-*`. Hebrew benedictions and English translations both flow cleanly.

### Digits inside RTL flow

Hebrew calendar dates inline with ceremonial copy where appropriate; Gregorian for everything else. Wrap mixed-direction strings in `<bdi>`. Prefer `dd MMMM yyyy` in Hebrew, `MMMM dd, yyyy` in English.

### Nikkud

Lyl Shabat handles nikkud well — Frank Ruhl Libre carries niqqud beautifully at display sizes, which makes the system a strong choice for prayer texts and educational religious content. For nikkud-dense pages override body line-height to 1.85.

### Punctuation

Gershayim (״) and geresh (׳) for Hebrew abbreviations. Maqaf (־) for compounds. Curly quotes for English. The system never uses em-dashes.

### OpenType features

Frank Ruhl Libre's contextual alternates are essential — leave `calt` and `liga` on. For nikkud-heavy pages, ensure `font-feature-settings: "kern"` stays enabled so vowel marks stack correctly.

### Accessibility

All default pairs clear WCAG AA. The plum-on-ivory pair clears AAA at body-md. Be careful with amber on ivory — use it for fills, not for inline text.
