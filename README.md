# Forever, Siya ❤️

A single-page, luxury-style romantic website — built for Gaurang & Siya (Mumbai ↔ Surat) for National Girlfriend's Day.

Pure HTML5, CSS3, and vanilla JavaScript. No build step, no npm, no frameworks. Open `index.html` and it just works.

---

## 1. Project structure

```
forsiya/
├── index.html          the whole page
├── style.css            all styling
├── script.js             all behavior + the CONFIG object (edit this!)
├── favicon.ico
├── site.webmanifest      "add to home screen" icon/theme config
├── robots.txt            tells search engines not to index this private page
├── sitemap.xml
├── README.md              you are here
├── CNAME                  custom-domain config for GitHub Pages
└── assets/
    ├── photos/            put your real photos here
    ├── music/              (no longer needed — music is a real Spotify embed now; folder kept for optional future use)
    ├── icons/              favicon + manifest icons (already generated)
    └── fonts/              empty — fonts load from Google Fonts by default
```

## 2. Preview it locally

Just double-click `index.html`, or for the most accurate preview (some browsers
restrict local file access for things like `<audio>`), run a tiny local server
from inside the `forsiya` folder:

```bash
python3 -m http.server 8000
```

then open `http://localhost:8000`.

## 3. Everything you'll want to edit lives in `script.js`

Open `script.js` and look at the `CONFIG` object at the very top. It contains:

- Names, the date you met, her quote, nickname
- The relationship-start date/time (powers the live day/month/hour/minute counters)
- The next-meeting date (powers the countdown)
- The 5-event timeline
- All 20 "reasons I love you" (flip cards)
- Gallery captions + photo paths
- The full love letter text
- The 5 "Open When..." card messages
- The 6 future-dreams cards
- The 6 promise cards
- Song title/artist
- The message revealed after "One Last Hug"

You do not need to touch `index.html` or `style.css` for any of this — just edit the values in `CONFIG` and refresh.

## 4. Photos — already added, easy to swap or add more

Your hero photo, About Her photo, and 4 gallery photos are already in `assets/photos/` and wired up:

- `hero.jpg` → the soft photo behind glass in the hero section
- `siya.jpg` → the "About Her" card photo
- `gallery-1.jpg` … `gallery-4.jpg` → the gallery masonry (2 more empty slots are ready in `CONFIG.gallery` in `script.js` — just add a photo to `assets/photos/` and set its `src`)

To swap any photo, just replace the file with the same name (keep it a `.jpg`), or point the relevant `<img src="...">` in `index.html` / `CONFIG.gallery` entry in `script.js` at a new filename.

## 5. Music — a real, licensed Spotify embed (no mp3 needed)

The "Music" section and the floating player both embed the actual official
Spotify track for "Perfect" by Ed Sheeran (from the *÷ (Deluxe)* album). This
means:

- It's the real song, streamed legally through Spotify — no copyright risk for your GitHub Pages site.
- Visitors get Spotify's own play/pause, progress bar, and volume controls right inside the embed.
- Listeners without a Spotify account get a 30-second preview; people logged into Spotify (including free accounts) can play the full track.

**To change the song:** find the track you want on [open.spotify.com](https://open.spotify.com), copy the ID from its URL (the part after `/track/`), and replace `0tgVpDi06FyKpA1z0VMD4v` in both `<iframe src="https://open.spotify.com/embed/track/...">` tags in `index.html` (one in the "Music" section, one in the floating player).

*If you'd still prefer to self-host an mp3 instead of using the Spotify embed, that's possible too — just ask and it can be swapped back.*

## 6. Deploying to GitHub Pages (no build step needed)

1. Create a new GitHub repository (public or private — GitHub Pages works with both on paid plans; public repos get free Pages on any plan).
2. Upload everything inside this `forsiya/` folder to the repo root (not the `forsiya` folder itself — its *contents*).
3. In the repo, go to **Settings → Pages**.
4. Under **Source**, choose the branch (usually `main`) and root folder, then **Save**.
5. Wait a minute or two — your site will be live at `https://<your-username>.github.io/<repo-name>/`.

Because everything is plain HTML/CSS/JS, no build process or npm install is required — GitHub Pages serves the files exactly as-is.

## 7. Using a custom domain (e.g. `forsiya.love` or `madeforsiya.com`)

1. Buy the domain from any registrar (Namecheap, GoDaddy, Google Domains, etc.).
2. In the registrar's DNS settings, add:
   - An **A record** for the root domain pointing to GitHub Pages' IPs:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Or a **CNAME record** for a subdomain (like `www`) pointing to `<your-username>.github.io`
3. Edit the `CNAME` file in this project (currently set to `forsiya.love`) so it contains **only** your actual domain, nothing else.
4. In your repo's **Settings → Pages**, enter the same custom domain and enable **Enforce HTTPS** once it's available.
5. DNS changes can take up to 24–48 hours to propagate.

**If you don't own a custom domain yet:** delete the `CNAME` file (or leave it — GitHub Pages just ignores it if the domain isn't verified) and use the default `github.io` URL instead.

## 8. SEO / sharing notes

- `index.html` currently includes `<meta name="robots" content="noindex, nofollow">` so search engines won't index this private page. Remove that tag if you'd ever want it publicly discoverable.
- Open Graph and Twitter Card meta tags are already set up so the link previews nicely if you share it — update the `og:url` and `twitter:image` values once you have a final domain and photo.
- `sitemap.xml` and `robots.txt` are included for completeness but aren't required for a private, unlisted page.

## 9. Performance & accessibility

- Images use `loading="lazy"`.
- Respects `prefers-reduced-motion` (animations are minimized/disabled automatically for users who request it).
- Keyboard support: gallery lightbox (arrow keys + Escape), modals (Escape), all interactive elements are focusable.
- `aria-hidden`, `aria-label`, and `aria-live` attributes are used throughout for screen readers.

## 10. A note on placeholders

Photos are already in place, and music is a real Spotify embed — so there's nothing left that *needs* your own files. Everything — names, dates, timeline, letter, reasons, "open when" notes, dreams, promises, photos, and music — is already filled in for Gaurang & Siya and ready to go. Keep customizing anything you like in `CONFIG` inside `script.js`.

Happy Girlfriend's Day. 🤍
