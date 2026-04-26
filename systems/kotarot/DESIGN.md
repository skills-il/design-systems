---
name: Headlines
version: 0.1.0
description: Dense Israeli news-portal. Saturated red CTA, hairline rules, square corners.
---

## Overview

Headlines is built for surfaces that publish faster than they polish: news desks, live tickers, sports feeds, breaking-event pages. Density is the point. Whitespace is rationed.

The visual language is rooted in the dominant Israeli portal aesthetic of the last twenty years — bold red CTA, crisp ink type on a cool grey paper, card grids divided by hairline rules, no shadows, no gradients, no playful curves. Use Headlines when scanability beats elegance.

## Colors

Two-temperature palette: cool ink on warm paper, with a single saturated red as the entire emergency vocabulary. Primary `#1B1B1B` for ledes; tertiary `#D80019` for breaking pills and the single CTA per viewport. Surface `#F5F5F4` is cool grey paper, never pure white. Surface-container `#FFFFFF` for cards on the grey.

## Typography

Heebo carries everything in three weights: 400 body, 700 headlines, 800 display lede at 56px. Captions use label-sm at 11px UPPERCASE with 0.08em tracking — print-masthead section labels (חדשות / כלכלה / ספורט).

## Layout

Tight spacing scale (`xs: 3, sm: 6, md: 10, lg: 16, xl: 24`). Cards butt against each other with 1-pixel separators. Multi-column desktop grids collapse to single-column on mobile but keep internal density.

## Shapes

All sharp. 0px radius on buttons, cards, inputs. Curves only on avatars (circular).

## Components

Buttons: primary fills with red, square corners, 8/16 padding. Cards: white on grey, 1px border, no shadow, square. Inputs: square, 1-pixel ink border, 8/12 padding. Focus ring is a 2-pixel red outline.

## Localization

Hebrew-first. Heebo handles both scripts. Use `<bdi>` around Latin numerals inside RTL flow ("1,200 ₪", "03-1234567"). Date format `dd/mm/yyyy` in Hebrew. Direction-aware CTA arrows (`←` RTL, `→` LTR). Logical CSS properties throughout.
