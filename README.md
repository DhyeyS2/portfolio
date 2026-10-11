# Portfolio site: how to edit and put it online

## Adding photos
Drop images into the `images/` folder using the exact file names shown on the grey striped
boxes on the site (e.g. `images/motor-1.jpg`). They appear automatically. No code needed.

Visitors can click any photo inside a project to open it full screen, then flick through
the other photos from that same section with the arrows (or swipe on a phone).

The first rocket, the flight computer rocket and the final motor each have 4 photo slots.
To add more anywhere, find that section in `index.html`, copy one `<figure ...>` line,
and change the file name in both places on that line. Empty slots are skipped by the viewer,
but they still show as striped boxes on the page, so delete any you don't fill.

## Adding videos
Any photo slot can show a video instead. Name the video the same as the slot but ending in `.mp4`
(e.g. `motor-3.mp4` instead of `motor-3.jpg`) and put it in `images/`. If a slot has no `.jpg`,
it shows the `.mp4` as a still frame with a play button, and visitors click it to watch full screen with sound.
Videos only play inside projects. The homepage tiles (`cover-...`) are photo-only.
Keep clips short (5 to 20 s) and under about 10 MB. iPhone `.MOV` files need converting to `.mp4` first.

## How the site is laid out
- The top screen has the launch-pad rocket. It lifts off as visitors scroll.
- Below it is the project grid. Each tile opens its own project page.
- Each project page has its own link you can send directly, e.g. `yoursite.com/#p/motors`
  (`#p/rockets`, `#p/motors`, `#p/rc`, `#p/cubesat`, `#p/vanguard`, `#p/cad`, `#p/tedx`).
- Project content lives near the bottom of `index.html` inside `<template id="t-...">` blocks.

## Tile cover photos
Each tile on the grid uses a cover image: `cover-rockets.jpg`, `cover-motors.jpg`, `cover-rc.jpg`,
`cover-cubesat.jpg`, `cover-vanguard.jpg`, `cover-cad.jpg`, `cover-tedx.jpg`. Landscape photos work best.
There is also `profile.jpg` (a square headshot for the profile at the top) and `me.jpg` for the About section.

## Editing text
Open `index.html` in any text editor (VS Code is free). Search for `EDIT` to find every
spot that needs your real info:
- Motors 2, 3 and 4: what you changed each time
- First rocket and RC plane attempt one: what went wrong
- TEDx talk: title, event, summary, YouTube link
- CAD captions
- About section: tweak the wording so it sounds like you
- Contact section: your real email, LinkedIn, GitHub and CV link

## Putting it online (GitHub Pages, free)
1. Make a free account at github.com
2. Click **New repository**, name it `portfolio`, set it to **Public**, create it
3. Click **uploading an existing file**, drag in `index.html` and the `images` folder, click **Commit changes**
4. Go to **Settings > Pages**. Under Source pick **Deploy from a branch**, branch `main`, folder `/ (root)`, Save
5. After a minute it's live at `https://YOUR-USERNAME.github.io/portfolio`

## Custom domain (Cloudflare)
1. Buy the domain on Cloudflare (Domain Registration)
2. In GitHub: **Settings > Pages > Custom domain**, type your domain, Save
3. In Cloudflare: **DNS > Records**, add these:
   - Four `A` records, name `@`, values: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One `CNAME` record, name `www`, value `YOUR-USERNAME.github.io`
   - Set the proxy toggle to **DNS only** (grey cloud) for all of them
4. Wait 10 to 30 minutes, then tick **Enforce HTTPS** in GitHub Pages settings

## Updating later
Upload the changed file to the same GitHub repo. The site updates within a minute.
