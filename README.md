# noisecomplaint.rocks

Static one-page site for Noise Complaint, served free from GitHub Pages.

## Files
- `index.html` — the whole site. No build step, no dependencies.
- `CNAME` — tells GitHub Pages to serve at noisecomplaint.rocks. Don't delete it.

## Adding a gig
Open `index.html`, find the `UPCOMING SHOWS` comment, copy the commented-out
`<li class="show">` example block, and fill it in. Delete the `<li class="empty">`
block once there's at least one real show.

## DNS (at name.com)
Apex `@` -> A records: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
`www` -> CNAME: <github-username>.github.io
