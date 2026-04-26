---
name: Civic
version: 0.1.0
description: Modern Israeli government — WCAG-strict contrast, generous accessible spacing, deep navy authority.
---

## Overview

Civic is what Israeli government should look like in 2026: deep navy authority, neutral greys, strict WCAG AA contrast, generous tap targets, no marketing flourish. Modeled on the post-redesign gov.il aesthetic — calm, accessible, trustworthy, immediately recognizable as state digital service.

Use Civic for citizen-facing services: tax forms, benefits applications, ID renewals, municipal portals. Anywhere the user is performing a transaction with the state.

## Colors

Primary `#003E80` deep gov navy. Tertiary `#0061A8` action blue for hover and links. Surface `#FFFFFF` pure white. Surface-container `#F3F4F6` subtle grey panels for sidebars and helper sections.

Every text-on-surface pair clears WCAG AA (4.5:1 body, 3:1 large) by design. Don't introduce decorative grays below `#1F2937` for body copy.

## Typography

Assistant for everything — Hebrew-first sans designed for the Israeli government context, excellent legibility at body sizes. No display serif. Body sits at 16-18px. Line-height 1.6 so dense form labels don't feel cramped. Display headlines stay restrained at 48px weight 700 — Civic doesn't shout.

## Layout

Generous spacing: `lg: 28px`, `xl: 44px`, `2xl: 72px`. Forms get airy field spacing. Buttons have 12/24 padding for accessible touch targets.

## Shapes

Modest 8px radius on cards, buttons, inputs. Soft enough to feel modern, restrained enough to feel official. Never pill-shaped — pill reads as marketing/SaaS, wrong for civic.

## Components

Buttons: navy primary, 8px corners, 12/24 padding. Hover transitions to action-blue. Cards: light grey panels with 1px hairline border and 1px lift shadow. Inputs: white background, 1px hairline border, 8px corners, 12/16 padding. Focus ring is a 2-pixel navy outline with 2-pixel offset.

## Localization

Hebrew-first. Date format `dd/mm/yyyy` in Hebrew. ID numbers (`ת.ז.`), case numbers, reference codes always rendered LTR with `<bdi>` wrappers. Hebrew form labels use natural Israeli phrasing ("מה השם שלך?", not "אנא הזן שמך"). Error messages address the user directly and explain the fix.

Maintain 4.5:1 contrast on all text. Keyboard focus order matches visual order. All interactive elements have aria-label or visible label.
