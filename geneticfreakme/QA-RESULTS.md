# Production QA — September 14, 2026

## Hosting

- GitHub repository: public
- GitHub Pages: deployed successfully from `main` / root
- HTTPS: enforced
- Production asset response: image document
- Browser-reported asset dimensions: 1280 × 3500
- Production JPEG size: 744,292 bytes
- Production JPEG SHA-256: `4561ed62b72c7f25707efea93f3ca7e665a533413dfaf1c6fdc56fbe7c40bf90`

## Neopets Preview Lookup

- Submitted V5 source length: 4,276 characters
- Sanitizer blocked tokens: 0
- Full-page V5 background: retained and visibly rendered
- Main canvas: 1280 × 3500 px inside a measured 1348px lookup viewport
- Base text: 14px Georgia
- Trophy viewport: 1164 × 640 px; vertical scroll retained with no horizontal spill
- Trophy images: 188 live images at 74px width
- User Info viewport: 620 × 370 px with no overflow
- Shop/Gallery viewport: 620 × 360 px with no overflow
- Collections viewport: 1184 × 270 px with no overflow; seven entries in a four-column float layout
- Pet viewport: 1184 × 540 px with no overflow
- Visible pets: 9
- Visible carousel clones: 0
- CSS Grid: absent from custom source
- CSS Flexbox: absent
- CSS transform: absent

The first V5 Preview exposed Neopets' built-in two-column Grid rule for `.ul-collections`, which made the collection content 460px tall. The production code explicitly restores the intended four-column float layout with `.ul-collections{display:block!important}`; the final measured scroll height equals the 270px viewport height.

The hosted browser could not fetch Neopets' own `pets.neopets.com` thumbnail images during QA, so the nine pet image boxes displayed broken-image placeholders there. Pet names, species, ages, levels, links, count, and layout all rendered. This is an environment/network limitation affecting Neopets' asset host, not the custom GitHub Pages asset or the lookup CSS.

## Live publication

- Neopets **Save Changes**: accepted for V5
- Stored description length after Neopets formatting: 4,276 characters
- Fresh public lookup: verified at `https://www.neopets.com/userlookup.phtml?user=geneticfreakme`
- Live V5 background URL: retained and rendered
- Live main canvas: 1280 × 3500 px
- Live User Info client/scroll size: 620 × 370 / 620 × 370 px
- Live Shop client/scroll size: 620 × 360 / 620 × 360 px
- Live Collections client/scroll size: 1184 × 270 / 1184 × 270 px
- Live pet client/scroll size: 1184 × 540 / 1184 × 540 px
- Live trophy client size: 1164 × 640 px; `overflow: auto` retained
- Live visible pets: 9
- Live visible carousel clones: 0
- Live trophy images: 188

Neopets may inject a site-controlled 728 × 90 advertisement over the welcome panel for non-Premium viewers. This does not change the saved CSS or module geometry.
