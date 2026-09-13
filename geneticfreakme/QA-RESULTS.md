# Production QA — September 13, 2026

## Hosting

- GitHub repository: public
- GitHub Pages: deployed successfully from `main` / root
- HTTPS: enforced
- Production asset response: image document
- Browser-reported asset dimensions: 1000 × 1500

## Neopets Preview Lookup

- Submitted V3 source length: 4,295 characters
- Sanitizer `-blocked-` tokens: 0
- Full-page V3 background: retained and visibly rendered
- Main canvas: 1000 × 1500 px
- Trophy viewport: 615 px client width and 615 px scroll width; no horizontal spill
- Trophy viewport height: 512 px; vertical scroll retained for the live trophy table
- Collections viewport: 290 × 268 px with no overflow
- Shop viewport: 280 × 174 px with no overflow
- Visible pets: 9
- Visible carousel clones: 0
- CSS Grid: absent
- CSS Flexbox: absent
- CSS transform: absent

The hosted browser could not fetch Neopets' own `pets.neopets.com` thumbnail images during QA, so the nine pet image boxes displayed broken-image placeholders there. Pet names, species, ages, levels, links, count, and layout all rendered. This is an environment/network limitation affecting Neopets' asset host, not the custom GitHub Pages asset or the lookup CSS.

## Live publication

- Neopets **Save Changes**: accepted for V3
- Stored description length after Neopets formatting: 4,944 characters
- Fresh public lookup: verified at `https://www.neopets.com/userlookup.phtml?user=geneticfreakme`
- Live sanitizer blocked tokens: 0
- Live V3 skin: rendered from the production GitHub Pages URL
- Full-length Fyora, Illusen, and Jhudora tableau: visible in the lower-right bay
- Live visible pets: 9
- Live visible carousel clones: 0
- Live trophy client/scroll width: 615/615 px
