# Adam Weir Research: site

Static site, no build step. Open `index.html` in a browser to preview.

## Publishing schedule

- Every Monday, 7:00 AM ET (written Sunday). First Monday of the month = full thesis.
- Event-driven scorecards (earnings, rulings) post the same day, outside the schedule.
- Commit on the day you publish: the commit timestamp is the pre-registration proof.
  Never backfill, never amend published posts; post corrections as new text.

## Structure

```
index.html              Landing: the ledger + all writing, newest first
track-record.html       Open and closed positions; scoring rules
research.html           Macro/thematic reports and dissertation working papers
about.html              Schedule, method, contact, disclaimer
pitches/                One HTML file per full thesis
updates/                Scorecards, kill-switch checks, short notes
assets/style.css        The whole design system (colors/type at the top)
assets/*.pdf, *.png     Original notes and exhibit images
```

## Deploy on GitHub Pages (free)

1. Create a repo (e.g. `research`) on GitHub.
2. Put these files at the repo root and push:
   ```
   git init && git add -A && git commit -m "Launch: FDS thesis + Q4 scorecard"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
   (Or upload via the GitHub website: repo page -> "uploading an existing file".)
3. Repo -> Settings -> Pages -> Source: Deploy from a branch -> `main` / root -> Save.
4. Site appears at `https://<you>.github.io/<repo>/` in about a minute.
5. Custom domain (optional): buy one (~$10/yr), add it under Settings -> Pages,
   point its DNS (CNAME -> `<you>.github.io`), tick Enforce HTTPS.

Fill in the GitHub link in the index.html footer once the repo exists.

## Weekly workflow

- New thesis: copy `pitches/fds-2026-10.html` as the template, drop the PDF and any
  exhibit images in `assets/`, add a ledger row on `index.html` and
  `track-record.html`, add a Writing entry on `index.html`.
- New update or macro note: copy `updates/fds-q4-scorecard.html`, add a Writing entry
  (macro pieces also get listed on `research.html`).
- Exit: move the row from Open to Closed on `track-record.html`, write the exit post.

## Style rules

- First person; short headlines; no em dashes in site copy (reports keep their own
  punctuation verbatim).
- All colors and fonts are CSS variables at the top of `assets/style.css`.
  Type: Spectral (prose) + Archivo (data). Status chips: `chip long`, `chip watch`,
  `chip exited`, `chip note`.
