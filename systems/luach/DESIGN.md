---
name: Bulletin
version: 0.1.0
description: Israeli classifieds utilitarian. Yellow-cream paper, ultra-dense list rows, square corners, prices in red.
---

## Overview

Bulletin is for surfaces that show lots of small things in rows: apartment listings, used cars, second-hand furniture, jobs, classifieds, marketplace inventory. Unmistakably Israeli classified-board — warm yellow-cream paper, white listing rows, blue links, red prices. Density is utility; decoration is friction.

## Colors

Primary `#1F1F1F` ink for body. Secondary `#0061A8` link blue for every clickable noun. Tertiary `#D8001A` prices and "discounted" markers — the eye locks onto it. Surface `#FFFCEB` cream-yellow paper carries the page; never replaced with pure white. Surface-container `#FFFFFF` for the listing rows themselves.

Dark mode flips the relationship: yellow becomes the bright primary tone (`#FFE066`), surfaces go warm-near-black.

## Typography

Heebo only. No display serif. Largest is 36px and that's already aggressive — most surfaces live at body-md (14px) or body-sm (12px). Density of information beats hierarchy of size. Tight line-heights (1.2-1.3 headings, 1.5 body).

## Layout

Ultra-tight spacing (`xs: 2, sm: 4, md: 8, lg: 12`). Listing rows have 8-12px vertical padding and a 1-pixel separator. Photo thumbnails are small (96-120px) — description carries the listing.

## Shapes

Square or near-square. 2px corners on cards, buttons, inputs. Circular only on avatars.

## Components

Buttons: ink primary on cream, 2px corners. Cards (listing rows): white on cream, 1px border, 2px corners, 8-pixel internal padding. Hover lifts border to 24% opacity instead of adding shadow. Inputs: cream background with 1-pixel ink border.

## Localization

Hebrew-first. Numbers (prices, sqm, phones, listing IDs) appear LTR inside RTL flow; wrap them in `<bdi>` ("1,250,000 ₪", "85 מ״ר", "052-123-4567"). "Ago" timestamps in natural Israeli Hebrew ("לפני 3 שעות", "אתמול", "ביום ראשון"). Use ש״ח or ₪ for shekel; pick one per surface and stay consistent.
