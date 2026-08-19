# The Shelf

Self-contained interactive HTML documents. No build step, no dependencies, no server-side anything. Every file runs entirely in the browser.

## Live site

Once GitHub Pages is on, the site is at:

```
https://<your-username>.github.io/<repo-name>/
```

## Turning on GitHub Pages

1. Push this folder to a GitHub repo.
2. Repo → **Settings** → **Pages**.
3. Under **Source**, pick **Deploy from a branch**.
4. Branch: `main`, folder: `/ (root)`. Save.
5. Wait a minute or two, then load the URL above.

That is the whole setup. `index.html` in the repo root is what Pages serves by default.

## Adding a document

1. Drop the `.html` file in the repo root, next to `index.html`.
2. Open `index.html` and find the `DOCS` array near the top of the `<script>` block. There is a commented-out template right below the first entry.
3. Add one object. Newest first.

```js
{
  title: 'Next Thing',
  file: 'next-thing.html',
  desc: 'One or two sentences on what it is and who it is for.',
  tags: ['tag', 'tag'],
  date: '2026',
  channel: 'C'
}
```

`tags` build the filter chips automatically. `channel` sets the dot colour: `M` magenta, `C` cyan, `Y` yellow, `K` grey.

Site title, tagline and footer line live in the `SITE` object directly above `DOCS`.

## Notes

- Filenames are case-sensitive on GitHub Pages even though they are not on Windows. If a link 404s, check the capitalisation first.
- Avoid spaces in filenames. Use hyphens.
- Each document loads its own webfonts from Google Fonts, so a first visit needs a connection. Everything else works offline.
- To keep a file in the repo but off the index, just leave it out of `DOCS`. It stays reachable by direct URL.

## Contents

| File | What it is |
| --- | --- |
| `index.html` | This index |
| `sonic-youth-tuning-arsenal.html` | Sonic Youth guitar tunings, EVOL 1986 to The Eternal 2009. Playable fretboard shapes, synthesised audio per tuning, and a live string-tension calculator. |
