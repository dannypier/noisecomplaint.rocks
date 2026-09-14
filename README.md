# noisecomplaint.rocks

Static site for Noise Complaint, a Denver rock cover band. Served free from
GitHub Pages. No build step and no dependencies — edit a file, commit, and the
site redeploys in about a minute.

## Pages
- `index.html` — the whole main site
- `livegigqr.html` — served at `/livegigqr`. The page the QR code in the guitar
  case points at: three buttons (Venmo, Instagram, main site). Marked `noindex`
  so it doesn't compete with the main site in search.

## Logo variants — which one to use
- `logo.png` — green on transparent. **Use on dark backgrounds only.**
- `logo-outline.png` — green with a black outline, on transparent. **Use on white,
  light, or busy backgrounds** — light shirts, print, photos. This is the one that
  survives a home printer that's light on cyan.
- `logo-white.png` — solid white on transparent, for single-colour use.
- `logo-sm.png` — 700px green version, ~100KB instead of 250KB. Used by
  `/livegigqr` because that page gets loaded on bar wifi.

All were extracted from a photo of the frog-tape lettering on the kick drum head
by green-chromaticity masking, then rotated 5.25° to level the two lines.

## The two videos
The page carries two, both using the same click-to-load facade — nothing is
requested from YouTube until a visitor presses play.

1. **Vertical clip** (`#reel`, first): phone footage in a 9:16 frame, capped at
   330px wide and 60vh tall so it can't swallow a laptop screen. Its poster is
   `reel-poster.jpg`, pulled from the source file rather than YouTube — a Short's
   YouTube thumbnail comes back letterboxed and looks wrong in a portrait frame.
2. **Landscape video** (`#watch`, below it): the standard 16:9 embed.

To swap either one, replace the ID in its `data-yt` attribute. For the vertical
one, also replace `reel-poster.jpg` with a frame from the new clip:
`ffmpeg -ss 30 -i clip.mp4 -frames:v 1 -vf scale=720:1280 reel-poster.jpg`

## Other assets
- `reel-poster.jpg` — poster frame for the vertical clip (720×1280)
- `favicon.png` — NC monogram, built from the N in NOISE and the C in COMPLAINT
- `og.png` — link-preview image (1200×630)
- `band.jpg` — band photo
- `venue-logo.png` — Crazy Mountain Taproom logo (theirs, not ours)
- `qr.png`, `qr-poster.pdf/.png` — older QR pointing at `/#tip`
- `gig-flyer.pdf`, `gig-flyer-outline.pdf` — 8.5×11 guitar-case flyers pointing at
  `/livegigqr`. The outline version prints better.
- `CNAME` — pins the custom domain. Don't delete it.
- `robots.txt`, `sitemap.xml`

## Adding a gig
**Two places**, both in `index.html`:
1. Find the `UPCOMING SHOWS` comment and copy the commented-out
   `<li class="show">` block.
2. Add a matching `Event` entry in the `STRUCTURED DATA` block near the top, or
   Google won't see the show.

Delete past gigs from both. Delete the `<li class="empty">` block whenever at
least one real show is listed.

## What's wired up
- **Buy Us a Beer** → Venmo `@dannypier`
- **Get the Gig List** → MailerLite (account 2605706), posts to their subscribe
  endpoint through a hidden iframe so the page keeps this site's styling.
  Double opt-in is on.
- **Book Us** → Web3Forms, submits in place via fetch. Lands at
  `noisecomplaintrocks@gmail.com` with subject "Noise Complaint Booking Request".
  Falls back to a plain mailto panel if the service ever fails.
- **Video** → YouTube, loaded only on click so the player's JS and cookies stay
  off the page for anyone who doesn't press play.

## Colors
Frog green `#8ED13F`, sampled off the tape on the kick drum.
Background `#0A0B09`, panels `#14160F`, borders `#2B3022`.
Type: Archivo Black for headings, Archivo for body.

## DNS (at name.com)
Apex `@` A: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
Apex `@` AAAA: 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, 2606:50c0:8003::153
`www` CNAME: dannypier.github.io
