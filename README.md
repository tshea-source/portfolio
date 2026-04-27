# Tally Shea — PMM Portfolio Site

A single-page static site. Everything is in this folder — just upload the whole folder to a host.

## File structure

```
site/
├── index.html                  # the site itself
├── assets/
│   ├── headshot.png            # hero photo
│   ├── page8.png               # sales enablement screenshot
│   ├── demo-cryptomining.mp4   # local demo video (~100MB)
│   └── tally-shea-resume.pdf   # downloadable résumé
└── README.md                   # this file
```

## Deploying to GitHub Pages

1. Create a new GitHub repo (public): e.g. `tally-shea-portfolio` or just `<your-username>.github.io` for a root domain.
2. Upload the **contents** of this `site/` folder (not the folder itself) to the repo root. The `index.html` must sit at the repo root, with `assets/` alongside it.
3. In the repo: **Settings → Pages → Source → Deploy from branch → main / root**.
4. Wait ~1 minute. Your site will be live at `https://<username>.github.io/<repo-name>/` (or just `https://<username>.github.io/` if you named the repo `<username>.github.io`).

### Note about the demo video

The bundled `.mp4` is about 100 MB. GitHub allows files up to 100 MB and will warn over 50 MB, but it will work. If you'd rather not host the video in the repo, two easy alternatives:

- **Host on YouTube** (unlisted is fine) and swap the `<video>` tag in `index.html` for a YouTube `<iframe>` like the other two demos. Look for the comment around line ~400 — the pattern is already there.
- **Upload to a cloud bucket** (S3, Cloudflare R2, etc.) and point the `src=` attribute at the hosted URL.

## Editing the site

Everything lives in one file: `index.html`. Open it in any text editor. Content is organized by section, each clearly commented (`<!-- HERO -->`, `<!-- ABOUT -->`, etc.). The CSS is inline in the `<head>` for easy tweaking.

Common edits:
- **Change text**: find the section, edit the copy.
- **Add a blog or case study**: copy one of the existing `<a class="tile">` or `<a class="writing-item">` blocks and update.
- **Change colors**: the CSS custom properties at the top of `<style>` (`--accent`, `--bg`, etc.) control the palette globally.
- **Swap the résumé**: replace `assets/tally-shea-resume.pdf` with your updated file (keep the same filename, or update the `href` links in index.html).

## Local preview

Open `index.html` directly in a browser — it works offline. For a fully-accurate preview (so the sticky nav and video embeds behave normally), run a tiny local server:

```bash
# from inside the site/ folder
python3 -m http.server 8000
# then open http://localhost:8000 in your browser
```

## What's NOT in the site (but could be added later)

- A `/datadog` POV page (unlinked from nav) — a Datadog-specific pitch/teardown to share with the hiring manager.
- Customer testimonials (from the Sonrai landing page — pending your approval to pull them in).
- Additional writing — this has 5 curated posts; easy to expand if you want a full archive.
