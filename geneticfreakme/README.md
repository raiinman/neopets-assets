# geneticfreakme Neopets User Lookup

Production package for the `geneticfreakme` User Lookup, completed September 14, 2026. V5 replaces the cramped 1000px V3 with a new wide composition built from scratch.

## Files

- `userlookup-final.html` — paste-ready V5 Neopets HTML/CSS (4,276 stored characters after Neopets reformats it).
- `backup-original-2026-09-13.html` — the lookup code that was present before this redesign.
- `assets/lookup-skin-v5.jpg` — production full-page background, exactly 1280 × 3500 px.
- `assets/lookup-skin-v5-source.png` — V5 source artwork used for the production render.
- `assets/lookup-skin-v3.jpg` — previous production full-page background.
- `assets/lookup-skin-v3-source.png` — previous source artwork.
- `assets/lookup-skin-v2.jpg` — previous approved full-page background without the faerie tableau.
- `FILTER-RESEARCH-2026.md` — the tested compatibility record and source links.

## Hosted production asset

`https://raiinman.github.io/neopets-assets/geneticfreakme/lookup-skin-v5.jpg`

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

The 1280px-wide trophy section is the visual and spatial priority. Its internal vertical scroll is intentional. User Info is 620px wide, Collections spans 1184px in four columns, and all nine pets share a 1184px gallery. Fyora, Illusen, and Jhudora occupy a dedicated illustrated bay without covering any live Neopets module.

Neopets may inject a 728 × 90 advertisement over the welcome panel for non-Premium viewers. That ad is site-controlled and is not part of the custom lookup source.

Keep the source compact. Neopets reformats saved CSS and enforces a 5,000-character description limit; expanding this version substantially can cause late declarations to disappear even when Preview accepts them.
