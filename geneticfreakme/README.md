# geneticfreakme Neopets User Lookup

Production package for the `geneticfreakme` User Lookup, completed September 13, 2026.

## Files

- `userlookup-final.html` — paste-ready Neopets HTML/CSS (4,335 characters; 665 characters below the editor limit).
- `backup-original-2026-09-13.html` — the lookup code that was present before this redesign.
- `assets/archive-hero.jpg` — production hero image, exactly 1000 × 300 px.
- `assets/archive-hero-source.png` — full-resolution generated source artwork.
- `FILTER-RESEARCH-2026.md` — the tested compatibility record and source links.

## Hosted production asset

`https://raiinman.github.io/neopets-assets/geneticfreakme/archive-hero-1000x300.jpg`

The public source repository is `https://github.com/raiinman/neopets-assets`. GitHub Pages publishes from `main` at the repository root, with HTTPS enforced. Do not rename the repository, move the file, change its letter case, make the repository private, or disable Pages unless the URL in `userlookup-final.html` is changed too.

## Install

1. Open `https://www.neopets.com/settings/profile` while logged in.
2. Copy all of `userlookup-final.html` into the User Lookup Description field.
3. Select **Preview Lookup** and confirm the hero, account/shop cards, collection rail, trophy vault, and all nine pets appear.
4. Enter the current Neopets password and select **Save Changes**.
5. Open `https://www.neopets.com/userlookup.phtml?user=geneticfreakme` in a fresh tab and verify the live page.

## Rollback

Paste the entire contents of `backup-original-2026-09-13.html` into the same field, enter the current password, and save.

## Design contract

The page deliberately uses conservative, old-school CSS: absolute positioning for the main composition, floats for the collection rail, and table/table-cell display for the pet strip. There is no JavaScript, CSS Grid, Flexbox, transform, web font, SVG, embedded data URL, or dependency on a third-party stylesheet.

The trophy section is the visual and spatial priority. Its internal vertical scroll is intentional: the live trophy table is roughly four thousand pixels tall, so displaying it unbounded would turn the whole lookup into a five-screen hallway. The 1,075 px vault keeps trophies dominant without crushing the rest of the profile.
