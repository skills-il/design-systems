---
name: Coast
version: 0.1.0
description: Tel Aviv Mediterranean. Bone-white surfaces, deep ocean primary, warm sand secondary, sea-foam accent.
---

## Overview

Coast is a Mediterranean design system rooted in Tel Aviv's particular light: bone-white limestone, ocean blue, warm sand, sea-foam shadows under a 2pm sun. Editorial in tone, hospitable in spacing, photo-friendly in chrome.

Use Coast for hospitality (boutique hotels, restaurants, wineries), travel editorial, lifestyle commerce, beach-adjacent SaaS. Wrong for transactional gov surfaces, news portals, dense classifieds.

## Colors

Primary `#1E5F8C` deep ocean — headlines, primary CTAs, navigation. Secondary `#D4906B` warm terracotta sand for accents. Tertiary `#5BA8B8` turquoise sea-foam — hover state on primary buttons (transitions ocean → seafoam). Surface `#F9F4E8` bone-white limestone. Surface-container `#FFFFFF` for actual cards — white-on-bone gives the soft contrast Tel Aviv stucco walls have at midday.

## Typography

Two families. Display uses Frank Ruhl Libre — modern Hebrew serif with optical Latin coverage, weight 400 at 64px gives editorial gravitas. Body uses Heebo for both scripts, generous 1.7 line-height for long-form reading flow. The serif/sans contrast is intentional — Frank Ruhl on a hero against Heebo body reads like a magazine layout.

## Layout

Airy by default. `lg: 32px`, `xl: 52px`, `2xl: 88px`. Hero sections breathe. Image-led layouts with full-bleed photos and asymmetric text columns.

## Shapes

Soft and rounded. `lg: 24px` on cards, `9999px` (full pill) on buttons and search inputs. The pill is essential — it's the visual signature that separates Coast from every other Hebrew system.

## Components

Buttons: ocean primary, full pill, 12/28 padding. Hover transitions to seafoam under 120ms. Cards: white on bone, no border, 24px corners. Shadow is the chrome: `0 16px 40px rgba(30,95,140,0.12)` — diffused, ocean-tinted. Inputs: bone surface, full pill, 12/18 padding.

## Localization

Hebrew-first. Frank Ruhl Libre is a Hebrew-native serif (Hebrew Type Society) and pairs cleanly with Heebo body. Date format `dd MMMM yyyy` in Hebrew ("12 ביוני 2026"). Long-form Hebrew benefits from generous line-height — 1.7 is non-negotiable for the Coast voice. Wrap numerical content in `<bdi>` inside RTL flow. Currency stays as ₪.
