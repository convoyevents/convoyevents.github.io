# Convoy website — how to put this online

Everything in this folder is the website. Upload its **contents** to your
GitHub repo (`convoyevents.github.io`) and convoyevents.au serves it.

## What each file is

    index.html            the homepage       →  convoyevents.au
    whatisart/index.html  the event page     →  convoyevents.au/whatisart
    auction/index.html    the auction page   →  convoyevents.au/auction
    join/index.html       the sign-up page   →  convoyevents.au/join
    support.js            the engine every page needs (do not delete)
    image-slot.js         handles the artwork photo frames on the auction page
    assets/               photos + favicon
    assets/archive/       the four past artworks
    CNAME                 tells GitHub the site answers to convoyevents.au
    .nojekyll             stops GitHub reprocessing the files (harmless, leave it)

Auction and Join are now separate pages (no longer part of the homepage), so
your Meta Pixel counts a PageView for each — filter by URL `/auction` and
`/join` in Events Manager. Old links like convoyevents.au/#auction still work:
the homepage forwards them to the new pages.

## ⚠ Before you upload: the form worker address

The RSVP form (event page) and both Join forms now post to your Cloudflare
Worker instead of Formspree:

    https://convoy-form-sync.quiet-tree-ba04.workers.dev/submit-rsvp
    https://convoy-form-sync.quiet-tree-ba04.workers.dev/submit-join

`quiet-tree-ba04` is a placeholder — replace it with your real workers.dev
subdomain (shown in your Cloudflare dashboard) in `whatisart/index.html` and
`join/index.html`, or tell Claude the subdomain and it will be swapped in.
Until then the forms will show their "didn't send" error.

## Uploading (GitHub website, no software needed)

1. Go to github.com and open your repository `convoyevents.github.io`.
2. Click **Add file → Upload files**.
3. Unzip the folder I gave you, open it, select ALL the items inside
   (index.html, whatisart, auction, join, support.js, image-slot.js, assets,
   CNAME) and drag them into the browser window. Folders keep their structure.
4. In the "Commit changes" box type something like "auction + join pages",
   then click **Commit changes**.
5. Wait 1–2 minutes, then open convoyevents.au. If you see the old page, do a
   hard refresh (Cmd+Shift+R).

Files with the same name are replaced automatically.

If the hidden `.nojekyll` file will not upload (some computers hide it), make it
by hand: **Add file → Create new file**, type `.nojekyll` as the name, leave the
file empty, commit.

## Checking it worked

- convoyevents.au            → homepage
- convoyevents.au/whatisart  → What Is Art? event page
- convoyevents.au/auction    → live countdown, bidding works
- convoyevents.au/join       → community sign-up form

## Changing things later

Text, prices and photos are edited here in this project, then re-upload the
files that changed. Bids, opening prices and the close time live in Supabase,
not in these files — change those in the Supabase dashboard.
