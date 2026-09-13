# Neopets User Lookup filter research — September 13, 2026

## Primary and current references

- Official Neopets HTML Guide: https://www.neopets.com/help/html_13.phtml
- SunnyNeo User Lookups, updated December 21, 2025: https://www.sunnyneo.com/lookups.php
- Jellyneo report on the March 2025 URL/image filter failure and April 1 fix: https://www.jellyneo.net/?go=comments&post=15265

The official guide confirms that User Lookups can use a `<style>` block, fonts, online background images, pictures, tables, and links. It does not publish a complete sanitizer allowlist or an approved-host list. SunnyNeo's current premades therefore served as the practical compatibility baseline, followed by tests in the live `geneticfreakme` Preview Lookup.

## Live findings

| Item | September 2026 result |
|---|---|
| Lookup Description limit | `maxlength=5000`; final code is 4,335 characters with 665 shown remaining |
| HTML used successfully | `<style>`, `<div>`, `<a>`, `<span>`, `<h1>`, `<p>`, `<b>`, `<em>`, `<br>` |
| Selector forms used successfully | element, class, ID, descendant, grouped selectors, `:hover`, `:visited` |
| Layout used successfully | `position:absolute/relative/static`, pixel offsets and sizes, `float`, `display:block/table/table-cell/none`, `overflow:hidden/auto` |
| Visual properties used successfully | hex colors, borders, backgrounds, padding, margins, text alignment, font shorthand with one family, letter spacing, line height, text decoration, text transform, visibility |
| External asset | Public GitHub Pages JPEG accepted in CSS and retained by Preview Lookup |
| HTTPS behavior | Neopets rewrites submitted external `https://` values to `http://`; the host must redirect/upgrade cleanly to HTTPS |
| Rejected or stripped in testing | CSS `transform`; comma-separated font fallbacks; the slash form `center/cover`; `background-size` |

## Conservative compatibility decisions

- The hero file is physically 1000 × 300 px, matching its box, because the filter strips `background-size`.
- The declaration uses `background: color url(...) center no-repeat`, avoiding the rejected slash syntax.
- Fonts use one family per declaration (`Georgia` or `Verdana`) because fallback commas were rewritten to `-blocked-`.
- The page avoids CSS Grid and Flexbox. Current community examples consistently rely on positioning, floats, and table display, and those techniques passed the live preview.
- The page avoids scripts, event handlers, forms, iframes, embedded objects, SVG, data URLs, custom properties, external stylesheets, and web fonts. They were unnecessary and were not treated as safe merely because modern browsers support them.

Preview alone is not enough to certify the length. Neopets accepted a 4,961-character draft in Preview Lookup but rejected the real save because its internal formatter expanded that draft to 5,626 characters. The production source was reduced to 4,335 characters and then accepted by the real **Save Changes** flow.

## Dimensions tested on the live account

| Region | Dimensions |
|---|---:|
| Main canvas | 1000 × 2050 px |
| Hero artwork | 1000 × 300 px |
| User information | 450 × 265 px plus borders |
| Shop | 259 × 265 px plus borders |
| Collections rail | 255 × 1075 px plus borders |
| Trophy vault | 724 × 1075 px plus borders |
| Pet strip | 994 × 255 px plus borders |

Preview verification found nine visible pets and zero visible carousel clones. The trophy image width is capped at 74 px to prevent horizontal spill inside the vault.
