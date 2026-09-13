# geneticfreakme Neopets User Lookup

Production package for the `geneticfreakme` User Lookup, completed September 13, 2026.

## Files

- `userlookup-final.html` — paste-ready V3 Neopets HTML/CSS (4,295 source characters).
- `backup-original-2026-09-13.html` — the lookup code that was present before this redesign.
- `assets/lookup-skin-v3.jpg` — production full-page background, exactly 1000 × 1500 px.
- `assets/lookup-skin-v3-source.png` — full-resolution 1024 × 1536 source artwork.
- `assets/lookup-skin-v2.jpg` — previous approved full-page background without the faerie tableau.
- `FILTER-RESEARCH-2026.md` — the tested compatibility record and source links.

## Hosted production asset

`https://raiinman.github.io/neopets-assets/geneticfreakme/lookup-skin-v3.jpg`

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

The trophy section is the visual and spatial priority. Its internal vertical scroll is intentional. Fyora, Illusen, and Jhudora are painted full-length into the lower-right architectural bay without covering any live Neopets module.
