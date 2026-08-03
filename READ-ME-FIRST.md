# Convoy website — how to put this online

Everything in this `site` folder is the website. Upload its **contents** to your
GitHub repo (`convoyevents.github.io`) and convoyevents.au serves it.

## What each file is

    index.html            the homepage  →  convoyevents.au
    whatisart/index.html  the event page →  convoyevents.au/whatisart
    support.js            the engine both pages need (do not delete)
    image-slot.js         handles the artwork photo frames on the auction page
    assets/               photos + favicon
    assets/archive/       the four past artworks
    CNAME                 tells GitHub the site answers to convoyevents.au
    .nojekyll             stops GitHub reprocessing the files (harmless, leave it)

## Uploading (GitHub website, no software needed)

1. Go to github.com and open your repository `convoyevents.github.io`.
2. Click **Add file → Upload files**.
3. Unzip the folder I gave you, open it, select ALL the items inside
   (index.html, whatisart, support.js, image-slot.js, assets, CNAME) and drag
   them into the browser window. Folders keep their structure.
4. In the "Commit changes" box type something like "new homepage", then click
   **Commit changes**.
5. Wait 1–2 minutes, then open convoyevents.au. If you see the old page, do a
   hard refresh (Cmd+Shift+R).

Files with the same name are replaced automatically — the old `index.html`
becomes the new homepage, which is what we want.

If the hidden `.nojekyll` file will not upload (some computers hide it), make it
by hand: **Add file → Create new file**, type `.nojekyll` as the name, leave the
file empty, commit.

## Checking it worked

- convoyevents.au                → homepage, dark maroon, big CONVOY
- convoyevents.au/whatisart      → What Is Art? event page
- Auction tab                    → live countdown, bidding works

## Changing things later

Text, prices and photos are edited here in this project, then re-upload the
files that changed. Bids, opening prices and the close time live in Supabase,
not in these files — change those in the Supabase dashboard.
