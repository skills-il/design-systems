---
name: Civic
version: 0.1.1
description: Modern Israeli government, WCAG-strict contrast, generous accessible spacing, deep navy authority.
---

## Overview

Civic is what Israeli government should look like in 2026: deep navy authority, neutral greys, strict WCAG AA contrast, generous tap targets, no marketing flourish. Modeled on the post-redesign gov.il aesthetic, calm, accessible, trustworthy, immediately recognizable as state digital service.

Use Civic for citizen-facing services: tax forms, benefits applications, ID renewals, municipal portals. Anywhere the user is performing a transaction with the state.

## Colors

Primary `#003E80` deep gov navy. Tertiary `#0061A8` action blue for hover and links. Surface `#FFFFFF` pure white. Surface-container `#F3F4F6` subtle grey panels for sidebars and helper sections.

Every text-on-surface pair clears WCAG AA (4.5:1 body, 3:1 large) by design. Don't introduce decorative grays below `#1F2937` for body copy.

## Typography

Assistant for everything, Hebrew-first sans designed for the Israeli government context, excellent legibility at body sizes. No display serif. Body sits at 16-18px. Line-height 1.6 so dense form labels don't feel cramped. Display headlines stay restrained at 48px weight 700, Civic doesn't shout.

## Layout

Generous spacing: `lg: 28px`, `xl: 44px`, `2xl: 72px`. Forms get airy field spacing. Buttons have 12/24 padding for accessible touch targets.

## Shapes

Modest 8px radius on cards, buttons, inputs. Soft enough to feel modern, restrained enough to feel official. Never pill-shaped, pill reads as marketing/SaaS, wrong for civic.

## Components

Buttons: navy primary, 8px corners, 12/24 padding. Hover transitions to action-blue. Cards: light grey panels with 1px hairline border and 1px lift shadow. Inputs: white background, 1px hairline border, 8px corners, 12/16 padding. Focus ring is a 2-pixel navy outline with 2-pixel offset.

## Localization

Hebrew-first. Date format `dd/mm/yyyy` in Hebrew. ID numbers (`ת.ז.`), case numbers, reference codes always rendered LTR with `<bdi>` wrappers. Hebrew form labels use natural Israeli phrasing ("מה השם שלך?", not "אנא הזן שמך"). Error messages address the user directly and explain the fix.

Maintain 4.5:1 contrast on all text. Keyboard focus order matches visual order. All interactive elements have aria-label or visible label.

## Tokens

Machine-readable token block. Reference values via the curly-brace alias
syntax (e.g. `{colors.primary}`); resolve recursively if your build step
supports it. All hex values are sRGB.

```yaml
colors:
  primary: "#003E80"
  surface: "#FFFFFF"
  tertiary: "#0061A8"
  secondary: "#1F2937"
  on-primary: "#FFFFFF"
  on-surface: "#111827"
  on-tertiary: "#FFFFFF"
  on-secondary: "#FFFFFF"
  surface-container: "#F3F4F6"
colors-dark:
  primary: "#5BA0E8"
  surface: "#0A0F1C"
  tertiary: "#76B5E8"
  secondary: "#E5E7EB"
  on-primary: "#0A0F1C"
  on-surface: "#F3F4F6"
  on-tertiary: "#0A0F1C"
  on-secondary: "#0A0F1C"
  surface-container: "#16223A"
typography:
  body-lg:
    fontSize: 18px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.6
  body-md:
    fontSize: 16px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.6
  body-sm:
    fontSize: 14px
    fontFamily: Assistant, sans-serif
    fontWeight: 400
    lineHeight: 1.55
  label-sm:
    fontSize: 12px
    fontFamily: Assistant, sans-serif
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: 0.04em
  headline-lg:
    fontSize: 32px
    fontFamily: Assistant, sans-serif
    fontWeight: 700
    lineHeight: 1.2
  headline-md:
    fontSize: 22px
    fontFamily: Assistant, sans-serif
    fontWeight: 600
    lineHeight: 1.3
  headline-display:
    fontSize: 48px
    fontFamily: Assistant, sans-serif
    fontWeight: 700
    lineHeight: 1.15
    letterSpacing: -0.01em
spacing:
  lg: 28px
  md: 18px
  sm: 10px
  xl: 44px
  xs: 6px
  2xl: 72px
rounded:
  lg: 12px
  md: 8px
  sm: 4px
  none: 0px
components:
  card:
    padding: "{spacing.lg}"
    rounded: "{rounded.md}"
    elevation: 0 1px 2px rgba(0,0,0,0.05)
    textColor: "{colors.on-surface}"
    borderWidth: 1px
    backgroundColor: "{colors.surface-container}"
  input:
    padding: 12px 16px
    rounded: "{rounded.md}"
    textColor: "{colors.on-surface}"
    backgroundColor: "{colors.surface}"
  button-primary:
    padding: 12px 24px
    rounded: "{rounded.md}"
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

- **HE**: שירות ממשלתי, פשוט להבין.
- **EN**: A government service, made simple.

### Primary CTA

- **HE**: פתחו את הבקשה
- **EN**: Begin the request

### Error message

- **HE**: נצטרך את מספר תעודת הזהות כדי להמשיך.
- **EN**: We need your ID number to continue.
