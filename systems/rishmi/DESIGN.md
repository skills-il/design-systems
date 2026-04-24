---
name: Official
description: Israeli civic services with a clean redesign, Hebrew-first. White surface, charcoal-black ink, Israeli-flag blue accent. Trustworthy, accessible, neutral.
colors:
  primary: "#11151C"
  on-primary: "#FFFFFF"
  surface: "#FFFFFF"
  on-surface: "#11151C"
  surface-container: "#F0F2F5"
  accent: "#0038B8"
  on-accent: "#FFFFFF"
typography:
  display:
    fontFamily: "Heebo, sans-serif"
    fontSize: 56px
    fontWeight: "800"
    lineHeight: 1.1
    letterSpacing: "-0.02em"
  headline-lg:
    fontFamily: "Heebo, sans-serif"
    fontSize: 36px
    fontWeight: "700"
    lineHeight: 1.15
    letterSpacing: "-0.01em"
  headline-md:
    fontFamily: "Heebo, sans-serif"
    fontSize: 24px
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
    lineHeight: 1.65
  body-sm:
    fontFamily: "Heebo, sans-serif"
    fontSize: 14px
    fontWeight: "400"
    lineHeight: 1.55
  caps:
    fontFamily: "Heebo, sans-serif"
    fontSize: 12px
    fontWeight: "700"
    lineHeight: 1.2
    letterSpacing: "0.1em"
rounded:
  none: 0px
  sm: 4px
  md: 6px
  lg: 8px
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
    padding: 12px 20px
  button-primary-hover:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  button-ghost:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    rounded: "{rounded.md}"
    padding: 12px 20px
  card:
    backgroundColor: "{colors.surface-container}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.lg}"
    padding: "{spacing.lg}"
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: 12px 14px
---

## Overview

Rishmi is a civic-services system with the polish of a competent redesign. White surface, deep navy text, Israeli-flag blue accent. Use Rishmi for government and municipal portals, healthcare and legal services, financial regulation surfaces, anything that needs to be trusted on first read.

Hebrew-first. Heebo carries every size — display, headline, body — including all Latin glyphs. A citizen's form should not require two fonts to communicate, so the Latin fallback was intentionally removed; Heebo's Latin character set is sufficient for every English string the system renders.

## Colors

Three working colors plus a cool surface-container.

- **Primary (#11151C)**: charcoal-black, the trust color. Body text, inverted CTAs, headers. Black-rather-than-navy keeps Rishmi visually distinct from SaaS systems that use navy as their primary — citizens reading a tax form recognize ink-on-paper register, not enterprise polish.
- **On primary (#FFFFFF)**: pure white sitting on primary.
- **Surface (#FFFFFF)**: clean white, the page.
- **On surface (#11151C)**: charcoal on white.
- **Surface container (#F0F2F5)**: warm-neutral light gray, for cards, form sections, and the footer area. Slightly warmer than a pure-blue tint to soften the form chrome.
- **Accent (#0038B8)**: Israeli flag blue, the primary attention-getter. CTAs, links, focus rings, error highlights are derived from it. The contrast against charcoal text — flag-blue button next to ink-black headline — is sharper than the prior navy-on-navy combination, which read as a single tonal block.
- **On accent (#FFFFFF)**: white on accent.

The accent is a saturated, official blue — not a SaaS marketing blue. Citizens recognize it. Don't soften it toward teal or push it toward purple.

## Typography

Heebo as a single workhorse. The system uses weight (400 / 700 / 800) more aggressively than other systems to carry hierarchy without color or shape. Heebo's Latin character set is sufficient for every English string the system renders — no Latin fallback is needed and adding one would only introduce font-swap shimmer mid-form.

Body line-height stays at 1.65 — generous for form-heavy pages, conservative enough to keep dense regulatory copy from feeling sparse.

## Layout

Form-friendly. 8 point base, container padding 16 on mobile, 40 on desktop. Form fields stack vertically by default; never put two inputs on one row on mobile. Help text sits below each input at body-sm in a slightly muted tone — never above.

Logical properties throughout. The system was authored Hebrew-first; English flows cleanly through the same shapes.

## Elevation & Depth

Minimal. Cards rest on `surface-container` rather than casting shadow. Where elevation is required (modals, dropdowns), use a single soft shadow `0 4px 12px rgba(10, 37, 64, 0.08)`. No glass effects, no gradients.

## Shapes

Restrained rounding. 6 pixels on inputs and buttons, 8 pixels on cards. Sharper corners read as 1990s government and miss the "redesigned, trustworthy" mood. Don't go past 8 pixels — that direction reads as consumer-product.

## Components

- **Buttons**: primary fills with Israeli blue and white text, 6-pixel rounding. Ghost is white with navy outline. Hover on primary deepens to navy fill. Disabled buttons go to 40% opacity with `cursor: not-allowed`.
- **Cards**: surface-container background, 8-pixel rounding, 24-pixel padding, no border. Form sections use cards with a navy headline at headline-md.
- **Inputs**: white background, 1-pixel navy border at 0.3 alpha, 6-pixel rounding, 16-pixel body. Focus ring is a 2-pixel accent outline plus a `0 0 0 3px rgba(0, 56, 184, 0.2)` halo. Error state swaps the border to a desaturated red and the focus halo to a red derivative.

## Do's and Don'ts

Do label every form field above the input — never use placeholder-as-label, even on mobile.
Do meet AA contrast on every component, including disabled states. The system serves citizens with a wide accessibility range.
Do use the Israeli-flag blue sparingly — primary CTAs only, plus inline links.

Don't introduce a marketing accent (orange, green, purple). The system is civic, not promotional.
Don't reach for decorative typography. Heebo at the right weight is enough.
Don't compress padding to fit more on the screen. Government forms reward whitespace.

## Localization

Rishmi was built Hebrew-first for civic surfaces; bilingual support is essential, not optional.

### RTL layout

`dir="rtl"` on `<html>` for Hebrew. Logical properties only — `padding-inline-start`, `inset-inline-end`. Tailwind `ps-*`, `me-*`, `start-*`. Form labels, help text, error messages, and submit buttons all flip cleanly when `dir` changes.

### Digits inside RTL flow

Hebrew identifier numbers (Teudat Zehut, phone) use Latin digits inline with Hebrew prose; wrap mixed-direction strings in `<bdi>`. Date format `dd/mm/yyyy` in both Hebrew and English UI for consistency. Tabular numerals (`tnum`) recommended on receipt and invoice tables.

### Nikkud

Rishmi is not optimized for nikkud — it serves civic content, not religious or educational. If you need to render nikkud (e.g. inside a quoted form-instruction page), override line-height to 1.85 on the affected node.

### Punctuation

Gershayim (״) for Hebrew abbreviations (e.g. ת״ז, ח״פ). Maqaf (־) inside compounds. Curly quotes in English. ASCII hyphens fine inside form-field placeholder examples (e.g. `xxx-xxxxxxx`).

### OpenType features

Heebo's default ligatures and contextual alternates remain enabled. Tabular numerals are essential for receipts, financial statements, and any table of identifiers — apply via `font-variant-numeric: tabular-nums`.

### Accessibility

Every default pair clears WCAG AA. The navy-on-white pair clears AAA at body-md. Error-state colors (derived from a desaturated red) must pass AA against the white surface; never use a bright pure red. Form fields require associated `<label>` and `aria-describedby` linking to help and error messages — the system's components ship with these wired by default.
