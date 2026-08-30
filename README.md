# noisecomplaint.rocks

Static one-page site for Noise Complaint, served free from GitHub Pages.
No build step, no dependencies, no JavaScript.

## Files
- `index.html` — the whole site
- `CNAME` — tells GitHub Pages to serve at noisecomplaint.rocks. Don't delete it.
- `logo.png` / `logo-white.png` — the kick-drum tape lettering, extracted to transparent PNG
- `band.jpg` — band photo
- `og.png` — the image that shows up when the link is shared
- `favicon.png` — browser tab icon

## Adding a gig
Open `index.html`, find the `UPCOMING SHOWS` comment, copy the commented-out
`<li class="show">` example block, fill it in, commit. Delete the
`<li class="empty">` block whenever at least one real show is listed.

## Things still to fill in
Search `index.html` for `REPLACE-ME`:
- Venmo username and Cash App cashtag (Buy Us a Beer section)
- MailerLite form URL (Get the Gig List section)
- Formspree endpoint + booking email (Book Us section)

## Colors
Frog green `#8ED13F`, sampled off the tape on the kick drum. Background `#0a0b09`.

## DNS (at name.com)
Apex `@` A records: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
Apex `@` AAAA records: 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, 2606:50c0:8003::153
`www` CNAME: dannypier.github.io
