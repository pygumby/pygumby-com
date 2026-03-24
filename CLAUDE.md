# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

Open `index.html` directly in a browser — no build step required.

## Architecture

A single-page personal link site for Lucas Konstantin Bärenfänger (`@pygumby`), hosted at `pygumby.com`. Pure HTML and CSS, no JavaScript, no dependencies. All styling is in a `<style>` block inside `index.html`. No separate CSS file.

## Card structure (top to bottom)

1. **Avatar** — loaded live from `https://github.com/pygumby.png`, 125px circle with a `#e8eaed` ring (`box-shadow: 0 0 0 3px #e8eaed`)
2. **Handle** — `<h1>` with muted `@` prefix (`#bdc1c6`), rest in `#202124`
3. **Full name** — `<h2>` in muted `#80868b`
4. **Link buttons** — ordered: Website, X, Discord, GitHub, PyPI
5. **Footer** — outside the card, "Made with Claude Code" with the Claude icon (simpleicons.org)

## Link buttons

Each button is a `<li>` containing either an `<a>` (external links) or a `<div>` (Website). Each row has three elements:
- **Icon** — 20px inline SVG from simpleicons.org, grey (`#5f6368`) at rest
- **Label** — uppercase, `0.75rem`, `#80868b`, fixed `3.5rem` width (e.g. "Website", "GitHub")
- **URL** — full URL text in Google blue (`#4285F4`)

The **Website row** is a non-interactive `<div class="current-site">` — this page *is* the website. It is permanently styled in the active state: `#e8f0fe` background, `#d2e3fc` border, icon and URL in `#4285F4`, URL `font-weight: 500`.

All other buttons on hover: background shifts to `#e8f0fe`, border to `#d2e3fc`, icon to `#4285F4`.

## Spacing system

Consistent `1.5rem` base unit throughout:
- Body padding (card-to-window-edge gap): `1.5rem`
- Card padding: `2.5rem` uniform
- Avatar → handle: `1.5rem`
- Handle → full name: `0.5rem` (they belong together)
- Full name → links: `1.5rem`
- Gap between link rows: `0.5rem`
- Footer margin-top: `1.5rem`

## Color palette

| Token | Value | Usage |
|---|---|---|
| Background | `#f8f9fa` | Page background |
| Surface | `#fff` | Card background |
| Text | `#202124` | Primary text |
| Muted | `#80868b` | Full name, link labels |
| Muted light | `#bdc1c6` | `@` prefix, footer text |
| Border | `#e8eaed` | Button borders at rest |
| Google blue | `#4285F4` | Link URLs, hover icons, active state |
| Blue tint | `#e8f0fe` | Hover/active background, avatar ring |
| Blue border | `#d2e3fc` | Hover/active border |

## Typography

Google Sans loaded via Google Fonts (`preconnect` to `fonts.googleapis.com` and `fonts.gstatic.com`), falling back to Roboto then sans-serif. Google Sans may not always resolve as it is semi-proprietary; Roboto is the reliable fallback and gives the same Google feel.

## Mobile

`@media (max-width: 480px)` applies `min-height: 4rem` to all link buttons. This ensures uniform button height when longer URLs (`discord.com/users/pygumby`, `github.com/pygumby`, `pypi.org/user/pygumby`) wrap to a second line on narrow screens.
