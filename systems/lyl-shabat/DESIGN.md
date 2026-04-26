---
name: Friday Dusk
version: 0.2.1
description: Friday-night candlelight, Hebrew-first. Deep plum surface, candle ivory ink, warm amber accent. Intimate, ceremonial, dim.
colors:
  primary: "#FBE9C7"
  on-primary: "#2A1129"
  surface: "#2A1129"
  on-surface: "#FBE9C7"
  surface-container: "#3F1A3D"
  tertiary: "#E0935A"
  on-tertiary: "#2A1129"
colors-dark:
  on-primary: "#1A0818"
  on-surface: "#FFF1D2"
  on-tertiary: "#1A0818"
  primary: "#FFF1D2"
  surface: "#1A0818"
  surface-container: "#2D0E2A"
  tertiary: "#FF9D60"
typography:
  headline-display:
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
  label-sm:
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

Friday Dusk is the system of the late evening, the room after the candles are lit. Deep plum surface, candle ivory ink, warm amber driver. Use Lyl Shabat for hospitality, family-oriented surfaces, prayer apps, journaling, anything that asks the reader to slow down. The dark surface is the system's authentic register, Friday night is a dim room, not a sunlit page.

Hebrew-first. Frank Ruhl Libre at display sizes carries a soft, modern Hebrew serif character; Assistant at body keeps the reading texture humanist and warm. Both bilingual.

## Colors

Candlelight palette, dim plum room, ivory ink, single warm flame.

- **Primary (#FBE9C7)**: candle ivory, used for ink-level fills (avatars, ghost-button text, headline color).
- **On primary (#2A1129)**: deep plum sitting on ivory fills.
- **Surface (#2A1129)**: deep plum, the room. Slightly warm, never blue-black.
- **On surface (#FBE9C7)**: ivory text on plum. Clears AAA at body-md (~14:1).
- **Surface container (#3F1A3D)**: lifted plum, for cards and quiet panels, slightly warmer and one shade up from the surface.
- **Accent (#E0935A)**: warm amber, the candle flame seen through glass. Brightened from the previous dusk-room amber so it lifts off the plum surface and clears AA on body-md text.
- **On accent (#2A1129)**: plum on amber. The pair holds the candle metaphor while clearing AA.

The palette stays low-saturation by intent. The amber should read as a flame in a dim room, present but never insistent.

## Typography

Frank Ruhl Libre at medium weight (500) gives the headlines warmth without preachy gravity. Assistant for body adds humanist rhythm to long passages. Body line-height runs 1.7, generous, slow.

The display weight intentionally stays at 500 rather than 700. Heavy headlines feel monumental; this system wants intimate.

## Layout

Soft, generous. 8 point base, container padding 24 on mobile, 56 on desktop. Cards rest on a single column on phones, expand to a 2-column grid at tablet, never more than 3-column on desktop. The system rewards air over density.

Logical properties everywhere. Lyl Shabat reads beautifully in both directions.

## Elevation & Depth

A soft warm glow, used sparingly. Cards lift via a tonal step (surface-container vs surface) plus an optional `0 4px 24px rgba(0, 0, 0, 0.4)` to suggest candlelight pooling on a dim table. Buttons stay flat. No glass effects.

## Shapes

Generous rounding. 12 pixels on inputs and buttons, 24 pixels on cards. The softness is part of the candlelight metaphor; sharp corners read as institutional and break the mood.

- **Buttons**: primary uses warm amber with plum text, 24-pixel rounding. Ghost is plum with ivory outline. Hover on primary swaps amber for ivory, the candle steadies and the room reads sharper.
- **Cards**: lifted-plum (surface-container) background, 12-pixel rounding, 24-pixel padding, soft warm shadow. Headers separate from body with whitespace, never with rules.
- **Inputs**: lifted-plum background, 1-pixel ivory border at low alpha, 12-pixel rounding, 16-pixel body. Focus ring is a 2-pixel amber outline.

## Do's and Don'ts

Do leave generous whitespace. The system is built to feel uncluttered.
Do use Hebrew at display weight (500), it reads more like a printed greeting than a billboard.
Do let the amber rest. One CTA per viewport, ideally per section.

Don't reach for blue or cool tones. The system is warm by definition.
Don't use heavy display weights (700+). Lyl Shabat whispers.
Don't use bold sans-serif headlines. The Frank Ruhl warmth is the voice.

## Localization

Lyl Shabat was built Hebrew-first with bilingual ceremonial-content support.

### RTL layout

`dir="rtl"` for Hebrew. Logical properties only, `padding-inline-start`, `inset-inline-end`, Tailwind `ps-*`, `me-*`, `start-*`. Hebrew benedictions and English translations both flow cleanly.

### Digits inside RTL flow

Hebrew calendar dates inline with ceremonial copy where appropriate; Gregorian for everything else. Wrap mixed-direction strings in `<bdi>`. Prefer `dd MMMM yyyy` in Hebrew, `MMMM dd, yyyy` in English.

### Nikkud

Lyl Shabat handles nikkud well, Frank Ruhl Libre carries niqqud beautifully at display sizes, which makes the system a strong choice for prayer texts and educational religious content. For nikkud-dense pages override body line-height to 1.85.

### Punctuation

Gershayim (״) and geresh (׳) for Hebrew abbreviations. Maqaf (־) for compounds. Curly quotes for English. The system never uses em-dashes.

### OpenType features

Frank Ruhl Libre's contextual alternates are essential, leave `calt` and `liga` on. For nikkud-heavy pages, ensure `font-feature-settings: "kern"` stays enabled so vowel marks stack correctly.

### Accessibility

All default pairs clear WCAG AA. The ivory-on-plum pair clears AAA at body-md. The brightened amber clears AA on plum, safe for fills and large display text. Avoid using amber for inline body links; demote those to ivory underlines.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
colors:
  primary: "#FBE9C7"
  surface: "#2A1129"
  tertiary: "#E0935A"
  on-primary: "#2A1129"
  on-surface: "#FBE9C7"
  on-tertiary: "#2A1129"
  surface-container: "#3F1A3D"
colors-dark:
  primary: "#FFF1D2"
  surface: "#1A0818"
  tertiary: "#FF9D60"
  on-primary: "#1A0818"
  on-surface: "#FFF1D2"
  on-tertiary: "#1A0818"
  surface-container: "#2D0E2A"
typography:
  body-lg:
    fontSize: 18px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.7
  body-md:
    fontSize: 16px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.7
  body-sm:
    fontSize: 14px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.6
  label-sm:
    fontSize: 12px
    fontFamily: Assistant, sans-serif
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.1em
  headline-lg:
    fontSize: 40px
    fontFamily: Frank Ruhl Libre, Assistant, serif
    fontWeight: 500
    lineHeight: 1.15
  headline-md:
    fontSize: 26px
    fontFamily: Frank Ruhl Libre, Assistant, serif
    fontWeight: 500
    lineHeight: 1.3
  headline-display:
    fontSize: 64px
    fontFamily: Frank Ruhl Libre, Assistant, serif
    fontWeight: 500
    lineHeight: 1.1
    letterSpacing: -0.005em
spacing:
  lg: 32px
  md: 20px
  sm: 12px
  xl: 48px
  xs: 6px
  2xl: 80px
rounded:
  lg: 24px
  md: 16px
  sm: 8px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.lg}"
    elevation: 0 24px 48px rgba(0,0,0,0.18)
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

- **HE**: האור כבוי. הדף דולק.
- **EN**: Light off. Page on.

### Primary CTA

- **HE**: לקריאה בחושך
- **EN**: Read in the dark

### Error message

- **HE**: לא הצלחנו לטעון. נסו רשת שקטה יותר.
- **EN**: Could not load. Try a quieter network.
