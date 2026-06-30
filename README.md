# Course website: AI-Native Bioinformatics FDP

A small static site for the Faculty Development Programme. No build step, no dependencies, just
HTML and one stylesheet. Built to live at `https://bpanda-dev.github.io/tot2`.

## Files

```
website/
├── index.html     # home: overview, pipeline, schedule, day cards, setup, capstone
├── day1.html      # Foundations & Target Framing
├── day2.html      # Build the Data Layer
├── day3.html      # Knowledge Engine
├── day4.html      # Characterize the Target
├── day5.html      # Generate, Dock, Rank + Capstone
├── styles.css     # shared theme (minimal academic serif)
└── README.md      # this file
```

All internal links are relative, so the site works under the `/tot2/` sub-path of a project site.
The footer source link already points to `github.com/bpanda-dev/tot2`.

## Deploy to github.com/bpanda-dev/tot2

1. Create a repo named **`tot2`**.
2. Put the **contents of this `website/` folder at the repo root** (so `index.html` sits at the top
   level, not inside a `website/` subfolder).
3. Push to `main`:
   ```bash
   git init
   git add .
   git commit -m "course site"
   git branch -M main
   git remote add origin https://github.com/bpanda-dev/tot2.git
   git push -u origin main
   ```
4. In the repo: **Settings → Pages → Source: Deploy from a branch**, pick **`main`** / **`/ (root)`**, Save.
5. The site goes live at `https://bpanda-dev.github.io/tot2/`.

Prefer to keep the files in a `website/` folder? Rename it `docs/`, push the whole project, and in
**Settings → Pages** choose the **`/docs`** folder instead.

## Local preview

```bash
cd website
python3 -m http.server 8000   # open http://localhost:8000
```

## Editing

The whole theme lives in `styles.css`. Change `--accent`, `--paper`, or the fonts in the variables
at the top to restyle every page at once. Each day page shares the same structure, so copy one to
add or revise a day.
