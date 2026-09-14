# Neopets User Lookup filter research — September 14, 2026

## Sources and verification method

- Official Neopets User Lookup HTML lesson: https://www.neopets.com/help/html_13.phtml
- SunnyNeo User Lookups, updated December 21, 2025: https://www.sunnyneo.com/lookups.php
- SunnyNeo CSS Codes, including scroll-box examples using `overflow:auto`: https://www.sunnyneo.com/csscodes.php
- Jellyneo report on Neopets' March 2025 URL/image-filter failure and April 1 fix: https://www.jellyneo.net/?go=comments&post=15265

The official lesson confirms that the User Lookup Description accepts a `<style>` block, fonts, online background images, pictures, tables, and links. Neopets does not publish a complete sanitizer allowlist or an approved-host list. Current SunnyNeo code was therefore used as the community baseline, then every production declaration below was tested in the authenticated Preview Lookup, saved through the real Profile form, reloaded from the editor, and checked again on the public `geneticfreakme` lookup.

## What survived the September 2026 save sanitizer

| Area | Verified production behavior |
|---|---|
| Description limit | The editor exposes `maxlength="5000"`. The final paste-ready source is 4,178 characters and Neopets stores it as 4,850 characters after reformatting. |
| HTML tags used | `<style>`, `<div>`, `<a>`, `<span>`, `<h1>`, `<h2>`, `<p>`, `<b>`, and `<br>` |
| Selectors used | Element, class, ID, descendant, direct-child (`>`), and grouped selectors |
| Positioning/layout | `position:relative/absolute/static`, pixel offsets and dimensions, `float`, and `display:block/table/table-cell/none` |
| Overflow | `overflow:hidden` and `overflow:auto`; the saved public trophy module retains a 512 px viewport over 2,883 px of content |
| Typography/visuals | Font shorthand with one family, font size, line height, letter spacing, colors, borders, backgrounds, padding, margins, alignment, decoration, transform-to-uppercase, visibility, and `!important` |
| External image URL | A public GitHub Pages JPEG in a CSS background was accepted, saved, and rendered on the public lookup |
| HTTPS handling | Neopets rewrites the submitted GitHub Pages `https://` URL to `http://`; GitHub Pages redirects it back to HTTPS, so the asset still loads securely |
| Rejected in testing | CSS `transform`, comma-separated font fallbacks, the background slash syntax (`center/cover`), and `background-size` |

## Production-safe choices

- The single background render is physically 1000 × 1500 px, exactly matching the lookup canvas. It does not depend on `background-size`.
- The code uses one external asset and an old-browser-compatible background shorthand.
- The page uses absolute positioning for the painted composition, floats for Collections, and table/table-cell display for the nine-pet strip.
- There is no JavaScript, CSS Grid, Flexbox, SVG, data URL, iframe, embedded object, form, custom property, external stylesheet, or web font.
- The production host is a public GitHub Pages repository with HTTPS enabled. Changing the repository name, path, letter case, privacy, or Pages setting will break the lookup asset URL.

## Save-time length trap

Preview Lookup is not sufficient to certify a build. Neopets expands compact CSS when it saves. A 4,318-character draft became 4,994 characters and silently lost the trophy module's `overflow:auto` declaration. After removing only redundant declarations, the final 4,178-character source stores at 4,850 characters and retains the scroll rule after a fresh editor reload.

## Final live geometry

| Region | Client size | Scroll size | Overflow |
|---|---:|---:|---|
| Main canvas | 1000 × 1500 px | 1000 × 1500 px | hidden |
| User Info | 280 × 278 px | 280 × 278 px | hidden; exact fit |
| Shop/Gallery | 280 × 174 px | 280 × 174 px | hidden; exact fit |
| Collections | 290 × 268 px | 290 × 268 px | hidden; exact fit |
| Trophy Vault | 615 × 512 px | 615 × 2,883 px | auto; vertical scroll only |
| Pet strip | 930 × 190 px | 930 × 190 px | hidden; all nine pets visible |

The production background is 1000 × 1500 JPEG/sRGB. Trophy images are 54 px wide, the User Info shield is 38 px wide, the Shop/Gallery image is fixed at 58 × 58 px, and pet images are fixed at 70 × 70 px.
